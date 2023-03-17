# 剑指 Offer 06. 从尾到头打印链表
## recursion
post-order traverse
first passing to the next node, 
then printing out
## Iteration
traverse from head to tail and record the value
use a **stack** to do so
# 剑指 Offer 24. 反转链表
## recursion
Think about the operation on each node
requires a reversed head node
My solution
![[Pasted image 20230214152452.png]]
## Iteration
Is there a O(1) space iteration solution?
![[Pasted image 20230214153327.png]]

# 剑指 Offer 35. 复杂链表的复制
#chanlleging #hashing 
138. 复制带随机指针的链表
So called deep copying, by constructing new nodes. They cannot point to argument nodes.
## hashing
Hard to figure out why use hashing. Use hash table as an middleware.
By storing new nodes in a hash table, it avoids pointing new nodes to arguments.

![[Pasted image 20230214163328.png]]
#recite python' s dict, `[]` cannot have none key or not existing key. .get() 's key can be arbitrary
![[Pasted image 20230214164547.png]]

## division
A smart solution, but also a special case
![[Pasted image 20230214171441.png]]