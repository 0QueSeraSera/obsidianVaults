# ifndef
`#ifndef` stands for "if not defined," and it is a preprocessor directive used in C and C++ programming languages. It is used to **prevent multiple inclusions of the same header file** or macro definition.

When you include a header file in a C or C++ program, the contents of that file are copied into the program at the point of the `#include` directive. If the same header file is included multiple times, either directly or indirectly, it can cause compilation errors or unexpected behavior.

To prevent this, programmers typically use `#ifndef` to include header files only once. **The `#ifndef` directive checks if a certain macro has been defined, and if it hasn't, it defines the macro and includes the header file. If the macro has already been defined, the `#ifndef` block is skipped, and the header file is not included again**.

# using namespace std;
Declaring `using namespace std;` is **not recommended** in general, especially in large projects or when collaborating with other programmers.

When you declare `using namespace std;`, you are telling the compiler to _bring all the symbols from the `std` namespace into the current scope_. This can lead to naming conflicts if different namespaces have identically named functions or classes. For example, if you have a function named `count` in your own namespace and you declare `using namespace std;`, you may get a compilation error because the `std::count` function will now conflict with your own function.

To avoid these conflicts, it is better to qualify the symbols from the `std` namespace with the `std::` prefix. For example, instead of `cout << "Hello, world!";`, you could write `std::cout << "Hello, world!";`. This way, you explicitly state which namespace you are using for a particular symbol.

However, in small programs or when writing code for personal use, declaring `using namespace std;` may be more convenient and save typing. It is a matter of personal preference, but keep in mind that it may cause issues in more complex codebases or projects.
# declaring namespace
The purpose of _declaring a namespace in a header file_ is to make sure that the **symbols declared in the header file are enclosed in the specified namespace**. This is particularly important when you have multiple header files that declare functions or classes with the same name.

When you define a function or class in a header file without enclosing it in a namespace, the symbols declared in that header file are _part of the global namespace_. This can lead to **naming conflicts when you include multiple header files that define symbols with the same name**.

To avoid naming conflicts, you can declare a namespace in the header file and enclose the symbols declared in the file within that namespace. This ensures that the symbols in the header file are uniquely identified by their namespace-qualified name, even if the same names are used in other header files or in the global namespace.
# Why Use `new` in the main function
`new rrt_planner::RRTPlanner(&node);`
In the main function, `new` is used to _dynamically allocate memory for an instance of the `RRTPlanner` class on the heap_.

The `new` operator **returns a pointer to the newly allocated object**, and this pointer is assigned to a local variable. The reason for using dynamic memory allocation in this case is that the `RRTPlanner` object needs to persist throughout the entire lifetime of the node, and **stack-allocated** objects in C++ are destroyed automatically when they go out of scope.

By allocating the `RRTPlanner` object on the heap using `new`, we can ensure that the object remains in memory until we explicitly delete it with the `delete` operator.

## Use a variable
If you use a variable to create an instance of the `RRTPlanner` class, like `node = rrt_planner::RRTPlanner(&node);`, then you would **have to declare `node` before calling the constructor**. However, in C++, the order of object construction and destruction is determined by the order of the objects in the code, not the order in which they are declared.

In this case, if you declare `node` before calling the constructor, then the `ros::NodeHandle` object would be constructed before the `RRTPlanner` object, but the `RRTPlanner` constructor requires a reference to the `NodeHandle` object. This would result in undefined behavior, because the `NodeHandle` object would not be fully constructed yet and it would not be safe to pass a reference to it.

Using `new` to _dynamically allocate memory_ for the `RRTPlanner` object ensures that the **`NodeHandle` object is fully constructed before the `RRTPlanner` constructor is called**, because the `new` operator _guarantees that the memory allocation is performed before the constructor is called_.

## difference
it's common to create an instance of a class and assign it to a variable in one line. The difference between this and using `new` is that in the latter case, **memory is allocated dynamically on the heap**, whereas in the former case, the object is **allocated on the stack**.

Allocating objects on the **stack** has the advantage of being _faster_ than **dynamic memory allocation**, and also takes care of memory management _automatically_, since the object is automatically destroyed when it goes out of scope. However, stack memory is limited, so creating large objects or many objects can cause a stack overflow.

Dynamic memory allocation with `new` has the advantage of being able to _allocate large objects or many objects without risking a stack overflow_, but it's slower than stack allocation, and it requires manual memory management, which can be error-prone if not done correctly (e.g., forgetting to free the memory with `delete`, or deleting the memory twice).

## `new` and `delete`
the code you posted doesn't include a `delete` command. However, in this case, it's not strictly necessary to include one because `RRTPlanner` is a **node object that runs indefinitely** and is **never explicitly destroyed**.

In general, it's good practice to include a `delete` command when you are finished using an object that you created with `new`. However, in the case of ROS nodes, they _typically run until the ROS node itself is shut down, at which point all memory is deallocated automatically_. In some cases, it may be necessary to manually deallocate memory using `delete` or similar commands, but for the most part, ROS takes care of this for you.
# Stack Overflow
Stack overflow is a situation when a program **runs out of the memory allocated to its stack**. The stack is a memory region allocated to a program for _storing local variables_, _function calls_, and other _runtime data_. When a function is called, its local variables and arguments are pushed onto the stack, and when it returns, they are popped off the stack. If a program *calls too many nested functions or allocates too many large objects on the stack, it can cause the stack to grow beyond the available memory, leading to a stack overflow*.
## example
```
void recursive_function(int i) {
    char buffer[1024];
    sprintf(buffer, "Recursion depth: %d", i);
    printf("%s\n", buffer);
    recursive_function(i+1);
}

int main() {
    recursive_function(0);
    return 0;
}
```
In this example, `recursive_function` calls itself recursively, passing an incremented value of `i` each time. The function also _allocates a large character buffer on the stack and writes to it using `sprintf()`_. As the recursion depth increases, more and more instances of the buffer are pushed onto the stack, eventually causing a stack overflow.

To avoid stack overflow, it's important to be mindful of the amount of memory being allocated on the stack, especially in recursive functions or functions with large local variables. **Large objects or arrays should be allocated on the heap using `new` or `malloc()`**. In addition, tail recursion can be used to avoid excessive stack usage in recursive functions. Finally, increasing the stack size of a program's thread can also help prevent stack overflow.

## `malloc` and `new`
`malloc` and `new` are both used for dynamic memory allocation, but they are fundamentally different.

`malloc` is a C function that allocates a block of memory of a specified size in bytes and returns a void pointer to the start of that block. The memory allocated by `malloc` is uninitialized, which means that the content of the memory block is undefined and may contain garbage values.

On the other hand, `new` is a C++ operator that does two things: it allocates memory for an object of a specified type, and then it constructs that object. The `new` operator returns a pointer to the object that was constructed. When a new object is created with `new`, its constructor is automatically called to initialize the object.

Another important difference is that `new` can throw an exception if it fails to allocate memory, while `malloc` returns a null pointer if it fails to allocate memory.

In general, it is recommended to use `new` and `delete` in C++ code, as they provide more type safety and are easier to use with objects that have constructors and destructors. However, it is also important to use them correctly to avoid memory leaks or other memory-related issues.