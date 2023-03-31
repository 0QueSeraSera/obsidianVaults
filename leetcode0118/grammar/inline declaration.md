In C++, the `inline` keyword is used to suggest to the compiler that a function should be **expanded in-line at the point where it is called**, instead of being called as a separate function. This can improve the performance of the program by reducing the overhead of function calls.

In general, it is a good idea to declare a function as `inline` if it meets the following criteria:
1.  The function is small and simple, consisting of only a few lines of code.
2.  The function is called frequently throughout the program.
3.  The function is not recursive.
By declaring a function as `inline`, you are telling the compiler to make a trade-off between code size and execution speed. In general, functions that are declared as `inline` will result in larger code size, but faster execution.

``` Example
inline int add(int x, int y) {
  return x + y;
}

int main() {
  int a = 3;
  int b = 4;
  int sum = add(a, b);
  return 0;
}

```
In this example, the `add` function is declared with the `inline` keyword. When the `add` function is called in the `main` function, the **compiler will substitute the code for the `add` function directly into the calling code**, rather than generating a separate function call. The resulting code might look something like this:
```
int main() {
  int a = 3;
  int b = 4;
  int sum = a + b;
  return 0;
}
```
However, it's important to note that the decision to make a function inline is ultimately up to the compiler. Even if you declare a function as `inline`, the compiler may choose not to inline it if it determines that doing so would not result in a performance improvement.

In modern C++, the `inline` keyword is generally not necessary, as the compiler can automatically determine when to inline functions based on its own optimization algorithms. Therefore, it's recommended to use `inline` sparingly and only when you have a strong reason to do so, such as improving performance in a critical section of code.