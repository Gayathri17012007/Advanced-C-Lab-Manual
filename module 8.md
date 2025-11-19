EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:
~~~
#include <stdio.h>
int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    switch (n) {
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 7:
            printf("seventy three\n");
            break;
        case 8:
            printf("seventy four\n");
            break;
        case 9:
            printf("seventy five\n");
            break;
        case 10:
            printf("seventy six\n");
            break;
        case 11:
            printf("seventy seven\n");
            break;
        case 12:
            printf("seventy eight\n");
            break;
        case 13:
            printf("seventy nine\n");
            break;
        default:
            printf("Greater than 13\n");
    }
    return 0;
}
~~~

Output:<br>
<img width="433" height="115" alt="image" src="https://github.com/user-attachments/assets/85d3de81-a467-4527-938c-0503a5f27daa" />


Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:
~~~
#include <stdio.h>
#include <string.h>
int main() {
    char a[50];
    int digit, i, c;
    printf("Enter the digits: ");
    scanf("%s", a);
    for (digit = 0; digit <= 3; digit++) {
        c = 0;  
        for (i = 0; i < strlen(a); i++) {
            if (a[i] == ('0' + digit)) {
                c++;
            }
        }
        printf("%d ", c);
    }
    return 0;
}
~~~
Output:<br>
<img width="475" height="193" alt="image" src="https://github.com/user-attachments/assets/22e1acb0-1c27-4ef5-be2f-35c0743b4f60" />

Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:
~~~
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
void swap(char *a, char *b) {
    char temp = *a;
    *a = *b;
    *b = temp;
}
void reverse(char s[], int l, int r) {
    while (l < r) {
        swap(&s[l], &s[r]);
        l++;
        r--;
    }
}
int next_permutation(char s[]) {
    int n = strlen(s);
    int i = n - 2;
    while (i >= 0 && s[i] >= s[i + 1])
        i--;
    if (i < 0)
        return 0; 
    int j = n - 1;
    while (s[j] <= s[i])
        j--;
    swap(&s[i], &s[j]);
    reverse(s, i + 1, n - 1);
    return 1;
}
int main() {
    char s[50];
    printf("Enter a string: ");
    scanf("%s", s);
    int n = strlen(s);
    for (int i = 0; i < n - 1; i++)
        for (int j = i + 1; j < n; j++)
            if (s[i] > s[j])
                swap(&s[i], &s[j]);
    printf("%s\n", s);
    while (next_permutation(s)) {
        printf("%s\n", s);
    }

    return 0;
}
~~~
Output:<br>
<img width="536" height="298" alt="image" src="https://github.com/user-attachments/assets/6bcb9aee-c4fb-4168-bf4d-c202c6a0dd0c" />


Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:
~~~
#include <stdio.h>
int main() {
    int n, i, j, min;
    printf("Enter n: ");
    scanf("%d", &n);
    int len = n * 2 - 1;
    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
            int top = i;
            int left = j;
            int bottom = len - 1 - i;
            int right = len - 1 - j;
            min = top;
            if (left < min) min = left;
            if (bottom < min) min = bottom;
            if (right < min) min = right;
            printf("%d ", n - min);
        }
        printf("\n");
    }
    return 0;
}
~~~

Output:<br>
<img width="559" height="290" alt="image" src="https://github.com/user-attachments/assets/24ad771b-b918-44b0-98f5-107429e77be7" />



Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:
~~~
#include <stdio.h>
int square()  
{
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    return n * n;  
}

int main()
{
    int result;
    result = square();  
    printf("Square = %d\n", result);
    return 0;
}
~~~
Output:<br>
<img width="478" height="153" alt="image" src="https://github.com/user-attachments/assets/2eaa6dc5-7f86-413a-8402-8beb4a43aad9" />



Result:
Thus, the program is verified successfully



























