

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
~~~
#include <stdio.h>
int max_of_four(int a, int b, int c, int d) {
    int max = a;

    if (b > max)
        max = b;
    if (c > max)
        max = c;
    if (d > max)
        max = d;

    return max;
}
int main() {
    int n1, n2, n3, n4, greater;
    printf("Enter four integers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);
    greater = max_of_four(n1, n2, n3, n4);
    printf("The greatest number is: %d\n", greater);
    return 0;
}
~~~
Output:<br>
<img width="633" height="171" alt="image" src="https://github.com/user-attachments/assets/d4e1bed7-fee7-4c5f-8850-548c4c0cf432" />

Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:
~~~
#include <stdio.h>
void calculate_the_max(int n, int k) {
    int a = 0, o = 0, x = 0;
    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int and_val = i & j;
            int or_val = i | j;
            int xor_val = i ^ j;
            if (and_val < k && and_val > a)
                a = and_val;
            if (or_val < k && or_val > o)
                o = or_val;
            if (xor_val < k && xor_val > x)
                x = xor_val;
        }
    }
    printf("Maximum AND value < %d: %d\n", k, a);
    printf("Maximum OR value < %d: %d\n", k, o);
    printf("Maximum XOR value < %d: %d\n", k, x);
}
int main() {
    int n, k;
    printf("Enter n and k: ");
    scanf("%d %d", &n, &k);
    calculate_the_max(n, k);
    return 0;
}
~~~
Output:<br>
<img width="563" height="202" alt="image" src="https://github.com/user-attachments/assets/8a87e752-9533-4daa-a113-6ebda0fec225" />


Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23  C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
## Aim:
To write a C program to write the logic for the requests

## Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 

 
Program:
~~~
#include <stdio.h>
int main() {
    int noshel, noque;
    printf("Enter number of shelves and number of queries: ");
    scanf("%d %d", &noshel, &noque);
    int shelarr[noshel][100];   
    int nobookarr[noshel];       
    for (int i = 0; i < noshel; i++)
        nobookarr[i] = 0;
    for (int q = 0; q < noque; q++) {
        int type, x, y;
        printf("Enter query type: ");
        scanf("%d", &type);
        if (type == 1) { 
            printf("Enter shelf number and book value: ");
            scanf("%d %d", &x, &y);
            shelarr[x][nobookarr[x]] = y;
            nobookarr[x]++;
        } else if (type == 2) {  // Print number of books on shelf x
            printf("Enter shelf number: ");
            scanf("%d", &x);
            printf("Number of books on shelf %d: %d\n", x, nobookarr[x]);
        } else if (type == 3) {  // Print the value of book y on shelf x
            printf("Enter shelf number and book index: ");
            scanf("%d %d", &x, &y);
            if (y < nobookarr[x])
                printf("Value of book %d on shelf %d: %d\n", y, x, shelarr[x][y]);
            else
                printf("Book index out of range.\n");
        } else {
            printf("Invalid query type.\n");
        }
    }
    return 0;
}
~~~

Output:<br>
<img width="623" height="450" alt="image" src="https://github.com/user-attachments/assets/f46d46c8-aef1-4813-ada2-38b891aa66d4" />



Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:
~~~
#include <stdio.h>
int main() {
    int n, sum = 0;
    printf("Enter the number of elements: ");
    scanf("%d", &n);
    int a[n]; 
    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum += a[i];
    }
    printf("Sum of the integers: %d\n", sum);
    return 0;
}
~~~

Output:<br>
<img width="524" height="222" alt="image" src="https://github.com/user-attachments/assets/f9b28bed-def2-453a-aaa8-e2da452bc4e0" />


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE



Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:
~~~
#include <stdio.h>
#include <ctype.h>
int main() {
    char sentence[200];
    int count = 0, inWord = 0;
    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);  
    for (int i = 0; sentence[i] != '\0'; i++) {
        if (isalpha(sentence[i])) {  
            if (inWord == 0) {
                inWord = 1;
                count++;
            }
        } else {
            inWord = 0;  
        }
    }
    printf("Number of words: %d\n", count);
    return 0;
}
~~~

Output:<br>
<img width="720" height="151" alt="image" src="https://github.com/user-attachments/assets/74496313-9871-426e-814f-f9b4d5815345" />



Result:
Thus, the program that counts the number of words in a given sentence is verified successfully.

