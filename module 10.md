EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>
struct node {
    int data;
    struct node *next;
};
int search(struct node *head, int key) {
    struct node *temp = head;

    while (temp != NULL) {
        if (temp->data == key)
            return 1;  // Found
        temp = temp->next;
    }
    return 0; 
}
int main() {
    struct node *head = NULL, *second = NULL, *third = NULL;
    int key;
    head = (struct node*)malloc(sizeof(struct node));
    second = (struct node*)malloc(sizeof(struct node));
    third = (struct node*)malloc(sizeof(struct node));
    head->data = 10;
    head->next = second;
    second->data = 20;
    second->next = third;
    third->data = 30;
    third->next = NULL;
    printf("Enter element to search: ");
    scanf("%d", &key);
    if (search(head, key))
        printf("Element found in the linked list.\n");
    else
        printf("Element not found in the linked list.\n");

    return 0;
}
~~~
Output:<br>
<img width="527" height="151" alt="image" src="https://github.com/user-attachments/assets/b3755cfe-2e0a-415d-992c-9c57f5360c2e" />



Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>
struct node {
    char data;
    struct node *next;
};
void insert(struct node **head, char value) {
    struct node *newNode = (struct node*)malloc(sizeof(struct node));
    struct node *temp;
    newNode->data = value;
    newNode->next = NULL;
    if (*head == NULL) {
        *head = newNode;
    } else {
        temp = *head;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
    }
}
void display(struct node *head) {
    struct node *temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%c -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}
int main() {
    struct node *head = NULL;
    char ch;
    insert(&head, 'A');
    insert(&head, 'B');
    insert(&head, 'C');
    display(head);
    printf("Enter a character to insert: ");
    scanf(" %c", &ch);
    insert(&head, ch);
    display(head);
    return 0;
}
~~~
Output:<br>
<img width="699" height="185" alt="image" src="https://github.com/user-attachments/assets/4c8dcb96-3e1f-4c43-ab32-04f9300c0310" />

Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>
struct node {
    int data;
    struct node *prev;
    struct node *next;
};
void traverse(struct node *head) {
    struct node *temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}
int main() {
    struct node *head = NULL, *second = NULL, *third = NULL;
    head = (struct node*)malloc(sizeof(struct node));
    second = (struct node*)malloc(sizeof(struct node));
    third = (struct node*)malloc(sizeof(struct node));
    head->data = 10;
    head->prev = NULL;
    head->next = second;
    second->data = 20;
    second->prev = head;
    second->next = third;
    third->data = 30;
    third->prev = second;
    third->next = NULL;
    traverse(head);
    return 0;
}
~~~
Output:<br>
<img width="702" height="140" alt="image" src="https://github.com/user-attachments/assets/3f736340-0cae-48e5-a21b-f538622c2267" />

Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>
struct node {
    int data;
    struct node *prev;
    struct node *next;
};
void insert(struct node **head, int value) {
    struct node *newNode = (struct node*)malloc(sizeof(struct node));
    struct node *temp;
    newNode->data = value;
    newNode->next = NULL;
    if (*head == NULL) {   
        newNode->prev = NULL;
        *head = newNode;
    } else {
        temp = *head;
        while (temp->next != NULL) {  
            temp = temp->next;
        }
        temp->next = newNode;
        newNode->prev = temp;
    }
}
void display(struct node *head) {
    struct node *temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}
int main() {
    struct node *head = NULL;
    int value;
    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    display(head);
    printf("Enter element to insert: ");
    scanf("%d", &value);
    insert(&head, value);
    display(head);
    return 0;
}
~~~
Output:<br>
<img width="684" height="197" alt="image" src="https://github.com/user-attachments/assets/2d31f416-8ab5-4030-bf41-d0d577aca015" />

Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:
~~~
#include <stdio.h>
#include <stdlib.h>
struct node {
    int data;
    struct node *next;
};
void deleteNode(struct node **head, int key) {
    if (*head == NULL) {
        printf("List is empty.\n");
        return;
    }
    struct node *temp = *head;
    struct node *prev = NULL;
    if (temp->data == key) {
        *head = temp->next;
        free(temp);
        printf("Element %d deleted from the list.\n", key);
        return;
    }
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Element %d not found in the list.\n", key);
        return;
    }
    prev->next = temp->next;
    free(temp);
    printf("Element %d deleted from the list.\n", key);
}
void display(struct node *head) {
    struct node *temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}
void insert(struct node **head, int value) {
    struct node *newNode = (struct node*)malloc(sizeof(struct node));
    newNode->data = value;
    newNode->next = NULL;
    if (*head == NULL) {
        *head = newNode;
        return;
    }
    struct node *temp = *head;
    while (temp->next != NULL)
        temp = temp->next;
    temp->next = newNode;
}
int main() {
    struct node *head = NULL;
    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    insert(&head, 40);
    display(head);
    int key;
    printf("Enter element to delete: ");
    scanf("%d", &key);
    deleteNode(&head, key);
    display(head);
    return 0;
}
~~~
Output:<br>
<img width="666" height="220" alt="image" src="https://github.com/user-attachments/assets/fe77b585-c7d6-4fd2-893c-7c8ac812b772" />


Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





