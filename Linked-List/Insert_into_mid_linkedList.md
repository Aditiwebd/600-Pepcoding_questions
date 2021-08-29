# Q 36.
[Question_Link](https://practice.geeksforgeeks.org/problems/insert-in-middle-of-linked-list/1#)

```
Node* middle(Node* head){
    Node* slow=head;
    Node* fast=head->next;
    
    while(fast!=NULL and fast->next!=NULL){
        fast=fast->next->next;
        slow=slow->next;
    }
    
    return slow;
}
Node* insertInMiddle(Node* head, int x)
{
	// Cpde here
	Node* temp=new Node(x);
	Node* midi=middle(head);
	if(midi==NULL)
	    return head;
	temp->next=midi->next;
	midi->next=temp;
	return head;
}
```
