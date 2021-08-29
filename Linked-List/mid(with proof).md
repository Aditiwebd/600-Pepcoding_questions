[Question-Link](https://leetcode.com/problems/middle-of-the-linked-list)
```
class Solution {
public:
    ListNode* middleNode(ListNode* head) {
        ListNode* slow=head;
        ListNode* fast=head;
        while(fast!=NULL and fast->next!=NULL){
            fast=fast->next->next;
            slow=slow->next;
        }
        
        return slow;
    }
};

```
