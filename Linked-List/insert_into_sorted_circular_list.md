# Q.37
[Question_Link](https://practice.geeksforgeeks.org/problems/sorted-insert-for-circular-linked-list/1)
```
class Solution
{
    public:
    Node *sortedInsert(Node* head, int data)
    {
       //Your code here
        Node* temp=new Node(data);
        Node* trav=head;
        Node* prev=head;
        do{
            prev=prev->next;
        }
        while(prev->next!=head);
        
        //printf("%d \n",prev->data);
        do{
            if(trav->data>=data)
                break;
            prev=trav;
            trav=trav->next;
        }
        while(trav!=head);
        //printf("%d \n",trav->data);
        prev->next=temp;
        temp->next=trav;
        if(head->data > temp->data)
            head=temp;
        return head;
    }
};

```
