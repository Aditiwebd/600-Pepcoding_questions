# Q.38
[Question_Link](https://leetcode.com/problems/remove-duplicates-from-sorted-list/)

```
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        ListNode* trav=head;
        ListNode* temp=NULL;
        while(trav!=NULL and trav->next!=NULL){
            if(trav->val == trav->next->val){
                if(temp==NULL)
                    temp=trav;
            }
            else if(temp!=NULL){
                temp->next=trav->next;
                trav=temp->next;
                temp=NULL;
                continue;
            }
            trav=trav->next;
        }
        if(temp!=NULL and trav!=NULL){
            temp->next=trav->next;
            trav=temp->next;
            temp=NULL;
        }
        return head;
    }
};
```
