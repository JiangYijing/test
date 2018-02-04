## 问题分析：
#### 链表有序合并
分别扫描两个链表,比较两个节点的大小值,把较小的节点值尾插到结果链表屁股后边,
然后再次扫描两个链表，直到其中某一个链表或者两条链表同时结束，
如果是某条链表提前结束则应将另一条链表的其余节点都接到结果链表上。
## 编程实现：
```C++
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        if(l1==NULL)
        {
            return l2;
        }
        if(l2==NULL)
        {
            return l1;
        }
        if(l1->val<=l2->val)
        {
            l1->next=mergeTwoLists(l1->next,l2);
            return l1;
        }
        if(l1->val>l2->val)
        {
            l2->next=mergeTwoLists(l1,l2->next);
                return l2;
        }
    }
};
```
## 总结分析：
1. 链表的基本用法
* VAL:在编程语言中Val是一个把字符串转为数值的函数，它返回包含于字符串内的数字，字符串中是一个适当类型的数值。
2. 递归优化,减少新增结果链表,比较数值大小进行链表的插入。
3. 讨论空链表的情况。
