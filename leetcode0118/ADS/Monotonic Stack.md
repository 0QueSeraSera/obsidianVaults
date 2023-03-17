## Defination
It is a stack in which the elements are in increasing/decreasing order from the bottom to the top of the stack.
example: 1, 3, 10, 15, 17
If we pop larger elements from the stack before pushing a new element, the stack is increasing from bottom to top.
## Implementation
-   As we need monotonically increasing stack, we should not have a smaller element at top of a bigger element.
-   So Iterate the given list of elements one by one :
    -   Before pushing into the stack, **POP** all the elements till either of one condition fails:
        -   Stack is not empty
        -   Stack’s top is bigger than the element to be inserted.
    -   Then push the element into the stack.
![[Pasted image 20230124215441.png]]
Complexity: O(n) for both time and auxilary
## Applications
-   Monotonic stack is generally used to deal with a typical problem like [**Next Greater Element**](https://www.geeksforgeeks.org/next-greater-element/). NGE (Find the first value on the right that is greater than the element.
-   Also can be used for its varieties.
    -   Next/previous Smaller/Greater Element
-   Also, we use it to get the greatest or smallest array or string by the given conditions (remaining size k/ no duplicate).
-   To understand the optimization power of monotonic stacks, let’s take this example problem: [Minimum Cost Tree From Leaf Values](https://leetcode.com/problems/minimum-cost-tree-from-leaf-values/description/). This problem can be solved in 3 different algorithm ways, out of which the monotonic stack is the most optimized approach.
    -   Dynamic Programming Algorithmic Approach: O(N^3) Time O(N^2) Space
    -   Greedy Algorithmic Approach: O(N^2) Time O(1) Space
    -   Monotonic Stack Algorithmic Approach: O(N) Time O(N) Space