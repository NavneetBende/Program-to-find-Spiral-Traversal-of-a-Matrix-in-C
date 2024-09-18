Spiral Traversal of a Matrix in C
 

Here, in this page we will discuss the program to print the spiral traversal of a matrix in C programming language. We are given with the elements of the array in two-dimensional form and we need to traverse the entire matrix in spiral form and print the corresponding element.

While loop in C
Algorithm :
Create a 2-d array of size rXc and then take (r*c) elements from the user and store them in declared array.
Now, create variable top and initialize it with 0 denotes starting of row, and variable bottom initialized it with (r-1) denotes the end of row, another variable say left set it to 0, it indicate the starting of the column and last variable is right that will be declared with value c-1 which indicate the end of the column.
Run a loop until all the squares of loops are printed.
Print the top row, i.e. Print the elements of the top-th row from column index left to right, and increase the count of top.
Print the right column, i.e. Print the last column or right-th column from row index top to bottom and decrease the count of right.
Print the bottom row, i.e. if top < bottom, then print the elements of bottom-th row from column right to left and decrease the count of bottom
Print the left column, i.e. if left < right, then print the elements of left-th column from bottom-th row to top-th row and increase the count of left.
The above printing will continue till top<bottom and left<right.
Time and Space Complexities :
Time-Complexity :O(r*c)
Space-Complexity : O(1)
Code in C
Run
#include <stdio.h>
#define r 4
#define c 4

int main()
{   
    int a[4][4] = { { 1, 2, 3, 4 },

                    { 5, 6, 7, 8 },

                    { 9, 10, 11, 12 },

                    { 13, 14, 15, 16 } };

    int i, left = 0, right = c-1, top = 0, bottom = r-1;

    while (left <= right && top <= bottom) {

        /* Print the first row
        from the remaining rows */
        for (i = left; i <= right; ++i) {
            printf("%d ", a[top][i]);
        }
        top++;

        /* Print the last column
        from the remaining columns */
        for (i = top; i <= bottom; ++i) {
         printf("%d ", a[i][right]);
        }
        right--;
    
        /* Print the last row from
        the remaining rows */
        if (top <= bottom) { for (i = right; i >= left; --i) {
            printf("%d ", a[bottom][i]);
          }
          bottom--;
        }
    
        /* Print the first column from
        the remaining columns */
        if (left <= right) { for (i = bottom; i >= top; --i) {
            printf("%d ", a[i][left]);
        }
        left++;
        }
    }
    
    return 0;
}
Output
1 2 3 4 8 12 16 15 14 13 9 5 6 7 11 10
