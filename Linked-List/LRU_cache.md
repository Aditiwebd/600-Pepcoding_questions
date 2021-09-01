# Q.40
[Question_link](https://leetcode.com/problems/lru-cache/)

```
class LRUCache {
public:
    class ListNode{
        public:
            int data;
            int value;
            ListNode* next;
            ListNode* prev;
        
        ListNode(int x,int y){
            this->data=x;
            this->value=y;
        }
    };
    ListNode* head=new ListNode(-1,-1);
    ListNode* tail=new ListNode(-1,-1);
    void addFirst(ListNode* temp){
        ListNode* t=head->next;
        head->next=temp;
        temp->next=t;
        temp->prev=head;
        t->prev=temp;
    }
    void removeBack(ListNode* temp){
        temp->prev->next=temp->next;
        temp->next->prev=temp->prev;
    }
    map<int,ListNode*> m;
    int cap;
    LRUCache(int capacity) {
        cap=capacity;
        head->next=tail;
        tail->prev=head;
    }
    
    int get(int key) {
        if(m.find(key)==m.end())
            return -1;
        else{
            ListNode* v=m[key];
            int k=v->value;
            m.erase(key);
            removeBack(v);
            ListNode* temp=new ListNode(key,k);
            addFirst(temp);
            m[key]=head->next;
            return k;
        }
    }
    
    void put(int key, int value) {
        if(m.find(key)!=m.end()){
            ListNode* temp=m[key];
            m.erase(key);
            removeBack(temp);
        }
        if(m.size()==cap){
            m.erase(tail->prev->data);
            removeBack(tail->prev);
        }
        ListNode* newT=new ListNode(key,value);
        addFirst(newT);
        m[key]=head->next;
    }
};

```
I couldn't solve it, so I watched [Striver's Video](https://www.youtube.com/watch?v=xDEuM5qa0zg&t=373s)
