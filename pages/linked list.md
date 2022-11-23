
# 📈Diagram
## Understand Linked List from diagrams
Suppose you have a simple linked list like so.
```cpp
struct ListNode
{
	int data;
    ListNode *next;
};
```

**📌Initialization of pointers**
⌨code
```cpp
ListNode *front = new ListNode();
front->data = 42;
front->next = new ListNode();
front->next->data = -3;
front->next->next = new ListNode();
front->next->next->data = 17;
front->next->next->next = new ListNode();
front->next->next->next->data = 9;
front->next->next->next->next = nullptr;
```
📈diagram
![name|400](../assets/linkedlist_init.svg)

**📌Reassigning Pointers**
Suppose you already have the following setup.
![name|300](../assets/linkedlist_diagram_setup.svg)
What should the following operations look like?
1️⃣
```cpp
a->next = b->next;
```
![name|300](../assets/linkedlist_diagram_1.svg)
2️⃣
```cpp
a = b->next;
```
![name|300](../assets/linkedlist_diagram_2.svg)
3️⃣
```cpp
a = b;
```
![name|300](../assets/linkedlist_diagram_3.svg)
4️⃣
```cpp
a->next->next = b;
```
![name|300](../assets/linkedlist_diagram_4.svg)


**📌Wrong `addFront` function**
```cpp
void addFront(ListNode* front, int value)
{
    ListNode* temp = new ListNode(value);
    temp->next = front;
    front = temp;
}

// the client code
int main()
{
    ListNode* list = ...;
    addFront(list, 10);
}
```
The preceding code looks good but actually it is wrong! What it does is the following.
![name|500](../assets/wrong_addFront_linkedlist.svg)

**📌Correct `addFront` function**
It can be easily fixed by [[pass-by-reference]].
```cpp
void addFront(ListNode*& front, int value)
{
    //...
}
```
It looks weird😲 but that is how it is.
![name|500](../assets/correct_addFront_linkedlist.svg)
