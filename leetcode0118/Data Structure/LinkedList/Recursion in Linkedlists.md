[[root_linkedList]]
# 206. 反转链表
#classic #chanlleging 
2 solutions, one is recursion, another is iteration. Iteration is relatively easier, but still easy to make mistakes. Recursion solution is rather abstract.
## Iteration
I have figured out the swaping order, iterating over `prev`, `cur`, and `tmp`. but One key here is init prev with None: `prev = None`. This avoids forming loops, very critical in 92.
## Recursion
```
# my solution on 3.9, failed
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        def recursion(prevHead, node):
            if not node:
                print("none node")
                return prevHead
            if not node.next:
                print("tail node")
                node.next = prevHead
                # prevHead.next = None
                return node
            # return recursion(node, node.next)
        return recursion(None, head)
```
![[Pasted image 20230309233511.png]]
Focus on its **_defination_**
![[Pasted image 20230309233540.png]]
![[Pasted image 20230309233603.png]]
![[Pasted image 20230309233615.png]]

# 92. 反转链表2
## Iteration
![[Pasted image 20230309233428.png]]

# 25. K 个一组翻转链表
