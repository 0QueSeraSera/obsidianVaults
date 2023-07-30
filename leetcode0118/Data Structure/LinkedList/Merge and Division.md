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
#chanlleging 
### 0730
tried creating 2 sub-list. wrong way of node operation?
```
 //0730: try simply break down the nodes to 2 sub-lists 
class Solution {
public:
    ListNode* partition(ListNode* head, int x) {
        ListNode* p_small = new ListNode(-201);
        ListNode* p_large = new ListNode(-201);
        ListNode* dummy_small = new ListNode(-201);
        ListNode* dummy_large = new ListNode(-201);
        dummy_small->next = p_small;
        dummy_large->next = p_large;

        ListNode* p = head;
        if (!head or !head->next) {
            return head;
        }
        while (p) {
            std::cout << p->val << endl;
            if (p->val < x ) {
                if (dummy_small->next->val == -201) {
                    // dummy_small->next = p;
                    p_small = p;
                }
                else {
                    p_small->next = p;
                    p_small = p_small->next;
                }
            }
            else {
                if (dummy_large->next->val == -201) {
                    // dummy_large->next = p;
                    p_large = p;
                }
                else {
                    p_large->next = p;
                    p_large = p_large->next;
                }
            }
            p = p->next;
        }
        p_small->next = dummy_large->next;
        return dummy_small->next;
    }
};
```

correct ans: 
**When moving a node, remember to cut off its next**
```
class Solution {
public:
    ListNode* partition(ListNode* head, int x) {
        ListNode* dummy1 = new ListNode();
        ListNode* dummy2 = new ListNode();
        ListNode* p1 = dummy1;
        ListNode* p2 = dummy2;

        ListNode* p = head;

        if (!head || !head->next) {
            return head;
        }

        while (p!=nullptr) {
            if (p->val < x) {
                p1->next = p;
                // if(p1->next)
                p1 = p1->next;
            }
            else {
                p2->next = p;
                // if(p2->next)
                p2 = p2->next;
            }
            ListNode* tmp = p->next;
            p->next = nullptr;
            p = tmp;
        }
        p1->next = dummy2->next;
        // delete dummy2;
        return dummy1->next;
    }
};
```

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

