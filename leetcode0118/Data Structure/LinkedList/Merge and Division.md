[[root_linkedList]]
#### [21. Merge Two Sorted Lists](https://leetcode.cn/problems/merge-two-sorted-lists/)
#### [86. Partition List](https://leetcode.cn/problems/partition-list/)
#### [23. Merge k Sorted Lists](https://leetcode.cn/problems/merge-k-sorted-lists/)


# 21
#classic 
The idea is quite simple. Focus on the implementation
![[1.gif]]
## Iteration
#note it is **not** about taking a node away from the linked list, but to **link to it** directly 
![[Pasted image 20230206114019.png]]
## Recursion
Essentially the same with the iteration solution. Try adapting it to recursion solution
![[Pasted image 20230206120347.png]]
# 86
# 23
#sorting #binary_search 
The thought is straightforward enough, but chanllenges implementations.
## My Solution
```
class Solution:

    def mergeKLists(self, lists: List[Optional[ListNode]]) -> Optional[ListNode]:

        def printF(lists):

            arr = []

            for l in lists:

                arr.append(l.val)

            print(arr)

        k = len(lists)

        if k == 1:

            return lists[0]

        if k == 0:

            return None

        front = []

        dh = ListNode(0)

        p = dh

        for l in lists:

            if not l:

                continue

            front.append(l)

        if not front:

            return None

        front = sorted(front, key=lambda x:x.val)

        # print(len(front))

        while len(front) > 1:

            # printF(front)

            tar = front.pop(0)

            p.next = tar

            tar = tar.next

            p = p.next

            p.next = None

            if not tar:

                continue

            # binary search

            l, r = 0, len(front) - 1

            # print("tar: ", tar.val)

            # print("to be inserted: ")

            # printF(front)

            while l <= r:

                mid = int((l + r) / 2)

                # if tar.val == 5:

                #     print(l, r, mid)

                if l == r:

                    # print("**", mid, tar.val)

                    if front[l].val > tar.val:

                        front.insert(l, tar)

                    else:

                        front.insert(l + 1, tar)

                    break

                if front[mid].val > tar.val:

                    r = mid

                elif front[mid].val < tar.val:

                    l = mid + 1

                else:

                    # print("--", mid, tar.val)

                    front.insert(mid, tar)

                    break

        # print(front)

        if len(front) != 0:

            p.next = front[0]

        return dh.next
```
#recite the usage of python `list.insert(index, item)`. index is the position of item **after** insertion

## Improved Soring and Insertion
### Divide & Conquer
#Divide-and-Conquer
![[Pasted image 20230206165258.png]]
两两合并
#todo study this divide-and-conquer method
![[Pasted image 20230206165936.png]]
### Priority Queue

