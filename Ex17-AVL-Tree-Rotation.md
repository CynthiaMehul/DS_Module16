# Ex 4B AVL Tree – Rotation
## DATE: 29/03/2025
## AIM:
To write a C function to perform right rotation in an AVL Tree.

## Algorithm
1. Start the program.
2. Include required libraries.
3. Create a structure to store the nodes of the tree.
4. Define a function to perform right rotation.
5. End the program.

## Program:
```
/*
Program to perform right rotation in AVL Tree
Developed by: Cynthia Mehul
RegisterNumber: 212223240020
*/

#include <stdio.h>
#include <stdlib.h>
node *rotateright(node *);  
typedef struct node {
    int data;
    struct node *left, *right;
    int ht;
} node;

node *rotateright(node *x) {
    node *y = x->left;
    x->left = y->right;
    y->right = x;

    x->ht = height(x);
    y->ht = height(y);

    return y;
}

```

## Output:

![image](https://github.com/user-attachments/assets/534ee8cf-1ce1-41a0-8f2c-e92be91d9f25)

## Result:
Thus, the function to perform right rotation in an AVL Tree is implemented successfully.
