EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:
~~~
#include <stdio.h>
#define MAX 5
int stack[MAX];
int top = -1;
void display() {
    if (top == -1) {
        printf("Stack is empty.\n");
        return;
    }
    printf("Stack elements:\n");
    for (int i = top; i >= 0; i--) {
        printf("%d ", stack[i]);
    }
    printf("\n");
}
void push(int value) {
    if (top == MAX - 1) {
        printf("Stack Overflow! Cannot push %d\n", value);
        return;
    }
    top++;
    stack[top] = value;
    printf("%d pushed to stack.\n", value);
}
int pop() {
    if (top == -1) {
        printf("Stack Underflow! Cannot pop.\n");
        return -1;
    }
    int val = stack[top];
    top--;
    printf("%d popped from stack.\n", val);
    return val;
}
int main() {
    push(10);
    push(20);
    push(30);
    display();
    pop();
    display();
    return 0;
}
~~~
Output:<br>
<img width="678" height="284" alt="image" src="https://github.com/user-attachments/assets/ad97919c-a273-4f5c-9805-431b50fc721a" />

Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:
~~~
#include <stdio.h>
#define MAX 5    
float stack[MAX];
int top = -1; 
void push(float value) {
    if (top == MAX - 1) {
        printf("Stack Overflow! Cannot push %.2f\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("%.2f pushed to stack.\n", value);
    }
}
int main() {
    push(10.5);
    push(20.75);
    push(30.25);
    push(40.00);
    push(50.50);
    push(60.20);
    return 0;
}
~~~
Output:<br>
<img width="757" height="262" alt="image" src="https://github.com/user-attachments/assets/1959d109-3ce1-40e2-a734-838eedfac838" />


Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:
~~~
#include <stdio.h>
#define MAX 5
int queue[MAX];
int front = -1, rear = -1;
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
        return;
    }
    printf("Queue elements: ");
    for (int i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }
    printf("\n");
}
void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow! Cannot insert %d\n", value);
        return;
    }

    if (front == -1) {
        front = 0; // first element
    }

    rear++;
    queue[rear] = value;
    printf("%d inserted into queue.\n", value);
}
int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();
    return 0;
}
~~~
Output:<br>
<img width="601" height="166" alt="image" src="https://github.com/user-attachments/assets/187d08ba-23a9-4bbe-9a6c-0fdf4307c233" />


Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:
~~~
#include <stdio.h>
#define MAX 5
float queue[MAX];
int front = -1, rear = -1;
void enqueue(float value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow! Cannot insert %.2f\n", value);
        return;
    }
    if (front == -1) {
        front = 0;  
    }
    rear++;
    queue[rear] = value;
    printf("%.2f inserted into the queue.\n", value);
}
int main() {
    enqueue(10.5);
    enqueue(20.75);
    enqueue(30.10);
    enqueue(40.00);
    enqueue(50.55);
    enqueue(60.20);
    return 0;
}
~~~
Output:<br>
<img width="635" height="223" alt="image" src="https://github.com/user-attachments/assets/012c1d0a-77c6-4f1d-94f6-3f151cc975dc" />


Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:
~~~
#include <stdio.h>
#define MAX 5
float queue[MAX];
int front = -1, rear = -1;
void dequeue() {
    if (front == -1) {
        printf("Queue Underflow! Queue is empty.\n");
        return;
    }
    printf("%.2f deleted from the queue.\n", queue[front]);
    front++;
    if (front > rear) {
        front = rear = -1;
    }
}

int main() {
    rear = 2;
    front = 0;
    queue[0] = 10.5;
    queue[1] = 20.75;
    queue[2] = 30.25;
    dequeue();
    dequeue();
    dequeue();
    dequeue();
    return 0;
}
~~~
Output:<br>
<img width="569" height="174" alt="image" src="https://github.com/user-attachments/assets/ef7c0a97-a186-4bee-87c9-c0a00c7677fb" />


Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
