# Ex 4E AVL Tree - Deletion
## DATE: 26.04.2025
## AIM:
To write a C function to delete an element from an AVL Tree.

## Algorithm
1. Start the program.
2. Include required libraries.
3. Create a structure to store the nodes of the tree.
4. Define a function to delete elements from an AVL tree.
5. End the program.

## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: Cynthia Mehul
RegisterNumber: 212223240020 
*/

#include <stdio.h>
#include <stdlib.h>
typedef struct node {
    int data;
    struct node *left, *right;
    int ht;
} node;
node *Delete(node *, int);
node *Delete(node *T, int x) {
    node *p;
    if (T == NULL) {
        return NULL;
    } else if (x > T->data) {
        T->right = Delete(T->right, x);
        if (BF(T) == 2)
            T = (BF(T->left) >= 0) ? LL(T) : LR(T);
    } else if (x < T->data) {
        T->left = Delete(T->left, x);
        if (BF(T) == -2)
            T = (BF(T->right) <= 0) ? RR(T) : RL(T);
    } else {
        if (T->right == NULL) {
            return T->left;
        } else {
            p = T->right;
            while (p->left != NULL)
                p = p->left;
            T->data = p->data;
            T->right = Delete(T->right, p->data);
            if (BF(T) == 2)
                T = (BF(T->left) >= 0) ? LL(T) : LR(T);
        }
    }

    T->ht = height(T);
    return T;
}

```

## Output:

![image](https://github.com/user-attachments/assets/a385ae71-30f8-448f-b2ae-3d1fbaf79a1c)

## Result:
Thus, the C program to delete an element from an AVL Tree is implemented successfully.
