# DSA-LAB-TASK-
  ..................LAB#01......................
           <<<<<<< TASK 01 >>>>>>>

#include<iostream>
using namespace std;
int main() {
    int arr[8] = {10, 20, 30, 40, 50, 60, 70, 80};
    cout << "Original array: ";
    for (int i = 0; i < 8; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    for (int i = 0; i < 7; i++) {
        arr[i] = arr[i + 1];
    }
    arr[6] = 0;
    cout << "Array after deleting the first and last elements: ";
    for (int i = 0; i < 7; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    return 0;
}
          <<<<<<< TASK 02 >>>>>>>
#include <iostream>
using namespace std;
int main() {
    int arr[8] = {10, 20, 30, 40, 50, 60, 70, 80};
    int index, newValue;
    cout << "Original array: ";
    for (int i = 0; i < 8; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    cout << "Enter the index : ";
    cin >> index;
    if (index >= 0 || index < 8) {
        cout << "Enter the new value: ";
        cin >> newValue;
        arr[index] = newValue;
        cout << "Updated array: ";
        for (int i = 0; i < 8; i++) {
            cout << arr[i] << " ";
        }
        cout << endl;
    } else {
        cout << "Invalid index." << endl;
    }
    return 0;
}
            <<<<<<< TASK 03 >>>>>>>
#include <iostream>
using namespace std;
int main() {
    int arr[8] = {10, 20, 30, 40, 50, 60, 70, 80};
    cout << "Original array: ";
    for (int i = 0; i < 8; i++) {
        cout << arr[i] << " " << endl;
    }
    cout << "enter elements in reverse order:";
    for (int i = 7; i > 0; i--) {
        cout << arr[i] << " " << endl;
    }
    return 0;
}
            ..................LAB#02......................
                     <<<<<<< TASK 01 >>>>>>>
#include <iostream>
using namespace std;
int main() 
{
    int arr[5] = {10, 20, 30, 40, 50};
    int *ptr = arr;
    for (int i = 0; i < 5; ++i) 
	{
        cout << "Element" << i+1 <<" : " << *ptr << endl;
        ptr++;
    }
    return 0;
}
                       <<<<<<< TASK 02 >>>>>>>
#include <iostream>
using namespace std;
void change(int *a, int *b) {
    int temp = *a;  
    *a = *b;        
    *b = temp;      
}
int main() {
    int x = 5, y = 10;
    cout << "Before changing x: "<<endl;
	cout<<  x << " y = " << y << endl;
    change(&x, &y);
    cout << "After changing x:"<<endl;
	cout << x << " y = " << y << endl;
    return 0;
}
                    ..................LAB#03......................
                              <<<<<<< TASK 01 >>>>>>>
#include <iostream>
using namespace std;
int main() {
    int n;
    cout << "Enter the size of the array: ";
    cin >> n;
    int* arr = new int[n];
    cout << "Enter " << n << " elements: ";
    for (int i = 0; i < n ; i++) {
        cin >> arr[i];
}
 for (int i = 0; i < n ; i++)
 {
      int even=0, odd=0;
        if (arr[i] % 2 == 0)
            even++;
        else
            odd++;
        }
    }
    cout << "even numbers: " << even << endl;
    cout << "odd numbers: " << odd << endl;
    delete[] arr;
    return 0;
}
                       <<<<<<< TASK 02 >>>>>>>
#include <iostream>
using namespace std;
int main()
 {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;
    int* arr = new int[n]; 
    cout << "Enter numbers: ";
     for (int i = 0; i < n ; i++)
	 {
    cin >> arr[i];
	}
    int max = arr[0], min = arr[0];
    for (int i = 1; i < n; i++) {
        cin >> arr[i];
        if (arr[i] > max) max = arr[i];
        if (arr[i] < min) min = arr[i];
    }
    cout << "Maximum: " << max  << endl;
    cout << "Minimum: " << max  << endl;
    delete[] arr; 
    return 0;
}
                           ..................LAB#04......................
                                    <<<<<<< TASK 01 >>>>>>>
#include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
};

void insertEnd(Node*& head, int value)
 {
    Node* newNode = new Node;
    newNode->data = value;
    newNode->next = NULL;
    if (head == NULL) 
	{
        head = newNode;
        return;
    }
    Node* temp = head;
    while (temp->next != NULL)
	 {
        temp = temp->next;
    }
    temp->next = newNode;
}
void display(Node* head) 
{
    Node* temp = head;
    while (temp != NULL)
	 {
        cout << temp->data << " -> ";
        temp = temp->next;
    }
    cout << "NULL:"<<endl;
}
int main() 
{
    Node* head = NULL; 
    insertEnd(head, 10);
    insertEnd(head, 20);
    insertEnd(head, 30);
    insertEnd(head, 40);
    cout << "Linked List: ";
    display(head);
    return 0;
}
                            <<<<<<< TASK 02 >>>>>>>
#include <iostream>
using namespace std;
struct Node 
{
    int data;
    Node* next;
};

Node* head = NULL; 

void addNode(int value) 
{
    Node* newNode = new Node{value, NULL};
    if (!head) 
	{
        head = newNode;
        return;
    }
    Node* temp = head;
    while (temp->next) temp = temp->next;
    temp->next = newNode;
}
void deleteAtStart()
 {
    if (!head) return;
    Node* temp = head;
    head = head->next;
    delete temp;
}
void deleteAtPosition(int pos)
 {
    if (!head) return;
    if (pos == 1) { deleteAtStart(); 
	return; 
	}
    Node* temp = head;
    for (int i = 1; temp && i < pos - 1; i++)
        temp = temp->next;
    if (!temp || !temp->next)
	 return;
    Node* delNode = temp->next;
    temp->next = temp->next->next;
    delete delNode;
}
void deleteAtEnd()
 {
    if (!head) return;
    if (!head->next) 
	{ delete head; head = NULL;
	 return;
	  }
    Node* temp = head;
    while (temp->next->next) temp = temp->next;
    delete temp->next;
    temp->next = NULL;
}
void printList() {
    Node* temp = head;
    while (temp) 
	{
        cout << temp->data << " -> ";
        temp = temp->next;
    }
    cout << "NULL:"<<endl;
}
int main() {
    addNode(10);
    addNode(20);
    addNode(30);
    addNode(40);
    addNode(50);
    cout << "Original List: "; printList();
    deleteAtStart();
    cout << "After deleting first node: "; 
	printList();
    deleteAtPosition(4);
    cout << "After deleting node at position 4: "; 
	printList();
    deleteAtEnd();
    cout << "After deleting last node: "; 
	printList();
    return 0;
}
                          ..................LAB#05......................
                                    <<<<<<< TASK 01 >>>>>>>
#include <iostream>
using namespace std;
struct Node
 {
    int data;
    Node* next;
    Node* prev;
};
void insertEnd(Node*& head, int value) 
{
    Node* newNode = new Node{value, NULL, NULL};
    if (!head) 
	{ 
        head = newNode;
        return;
    }
    Node* temp = head;
    while (temp->next) 
	{ 
        temp = temp->next;
    }
    temp->next = newNode;
    newNode->prev = temp;
}
void deleteAtStart(Node*& head) {
    if (!head) {
        cout << "List is empty!:"<<endl;
        return;
    }
    Node* temp = head;
    head = head->next; 
    if (head) head->prev = NULL; 
    delete temp; 
}
void printList(Node* head) {
    while (head) {
        cout << head->data << " ";
        head = head->next;
    }
    cout << endl;
}
int main()
 {
    Node* head = NULL;
    insertEnd(head, 10);
    insertEnd(head, 20);
    insertEnd(head, 30);
    cout << "Original List: ";
    printList(head);
    deleteAtStart(head);
    cout << "After Deletion: ";
    printList(head);
    return 0;
}
                                <<<<<<< TASK 02 >>>>>>>
  #include <iostream>
using namespace std;
struct Node
 {
    int data;
    Node* next;
    Node* prev;
};
void insertEnd(Node*& head, int value) 
{
    Node* newNode = new Node{value, NULL, NULL}; 
    if (!head) 
	{ 
        head = newNode;
        return;
    }
    Node* temp = head;
    while (temp->next) temp = temp->next;
    temp->next = newNode;
    newNode->prev = temp;
}
void deleteAtPosition(Node*& head, int pos) 
{
    if (!head) {
        cout << "List is empty!:"<<endl;
        return;
    }
    Node* temp = head;
    for (int i = 1; temp && i < pos; i++) 
        temp = temp->next;
    if (!temp)
	 {
        cout << "Invalid position!";
        return;
    }
    if (temp->prev) temp->prev->next = temp->next;
    if (temp->next) temp->next->prev = temp->prev;
    if (pos == 1) head = temp->next;
    delete temp;
}
void printList(Node* head) 
{
    while (head) 
	{
        cout << head->data << " ";
        head = head->next;
    }
    cout << endl;
}

int main() 
{
    Node* head = NULL;
    insertEnd(head, 10);
    insertEnd(head, 20);
    insertEnd(head, 30);
    insertEnd(head, 40);
    cout << "Original List: ";
    printList(head);
    deleteAtPosition(head, 2); 
    cout << "After Deletion: ";
    printList(head);
    return 0;
}
                               <<<<<<< TASK 03 >>>>>>>
#include <iostream>
using namespace std;
struct Node
 {
    int data;
    Node* next;
    Node* prev;
};

void insert(Node*& head, int value)
 {
    Node* newNode = new Node{value, NULL, NULL};
    if (!head)
	 { 
        head = newNode;
        return;
    }
    Node* temp = head;
    while (temp->next) temp = temp->next; 
    temp->next = newNode;
    newNode->prev = temp;
}
void deleteLast(Node*& head) 
{
    if (!head) 
	{
        cout << "List is empty!";
        return;
    }
    if (!head->next) 
	{ 
        delete head;
        head = NULL;
        return;
    }
    Node* temp = head;
    while (temp->next) temp = temp->next; 
    temp->prev->next = NULL;
    delete temp;
}
void print(Node* head) {
    while (head) {
        cout << head->data << " ";
        head = head->next;
    }
    cout << endl;
}
int main() 
{
    Node* head = NULL;
    insert(head, 10);
    insert(head, 20);
    insert(head, 30);
    insert(head, 40);
    cout << "Original List: ";
    print(head);
    deleteLast(head); 
    cout << "After Deletion: ";
    print(head);
    return 0;
}

                                 
