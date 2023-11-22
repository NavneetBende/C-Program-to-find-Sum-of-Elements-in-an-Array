# C-Program-to-find-Sum-of-Elements-in-an-Array

Sum of Elements in an Array in C
Today we will learn how to find sum of elements in an array is easy task when you know how to iterate through array elements. In this problem we will explain you C approach to find sum of array elements inputted by the user.
Here is the solution of this query in C Language.

C-program-to-find-largest-element
Methods discussed in the post
Method 1: Linear Iterative Solution
Method 2: Recursive approach starting from 0th array index
Method 3: Recursive approach starting from last array index
Method 1
For an array arr[]

Initialize sum = 0
Run an iterative loop in iteration of (i)
For each i do – sum = sum + arr[i]
Print sum
Sum of elements in an array in C
Method 1 : Code in C
Run
#include <stdio.h>

int calcSum(int arr[], int len){
    int sum = 0;
    
    for(int i = 0; i < len; i++)
        sum = sum + arr[i];
        
    return sum;
}
int main()
{
    int arr[] = {1, 5, 2, 10, 4, 8};
    
    // get the length of the array
    int len = sizeof(arr)/sizeof(arr[0]);    
    
    printf("Sum: %d",calcSum(arr, len));
}
// Time Complexity : O(N)
// Space Complexity : O(N)
Output
Sum: 30
While loop in C
Related Pages
Find the Smallest and largest element in an array

Find Second Smallest Element in an Array

Reverse an Array

Sort first half in ascending order and second half in descending 

Sort the elements of an array

Method 2 (using Recursion)
For an array arr[] call a function calcSum()

When reading last index if(index == len-1) return arr[index]
In all other cases return arr[index] + calcSum(arr, index+1, len);
Print the return value
Method 2 : Code in C
Run
#include <stdio.h>

// recursion starts from a[0] goes to a[len-1]
int calcSum(int arr[], int index, int len)
{
    if(index == len-1)
        return arr[index];
        
    return arr[index] + calcSum(arr, index+1, len);
}

int main()
{
    int arr[] = {1, 5, 2, 10, 4, 8};
    
    // get the length of the array
    int len = sizeof(arr)/sizeof(arr[0]);    
    
    printf("Sum: %d",calcSum(arr, 0, len));
}
// Time Complexity : O(N)
// Space Complexity : O(N)
// Auxiliary Space Complexity : (N) due to function call stack
Output
Sum: 30
While loop in C
Method 3 (using Recursion)
For an array arr[] call a function calcSum(). But start the recursion from the last index this time

When reading first index if(index == 0) return arr[index].
In all other cases return arr[index] + calcSum(arr, index-1);
Print the return value
Method 3 : Code in C
Run
#include <stdio.h>

// Recursion starts from a[len-1] goes till a[0]
int calcSum(int arr[], int index)
{
    if(index == 0)
        return arr[index];
        
    return arr[index] + calcSum(arr, index-1);
}
int main()
{
    int arr[] = {1, 5, 2, 10, 4, 8};
    
    // get the length of the array
    int len = sizeof(arr)/sizeof(arr[0]);    
    
    printf("Sum: %d",calcSum(arr, len-1));
}
// Time Complexity : O(N)
// Space Complexity : O(N)
// Auxiliary Space Complexity : (N) due to function call stack
Output
Sum: 30
