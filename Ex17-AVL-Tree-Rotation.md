# Ex 4B AVL Tree – Rotation
## DATE: 26.04.2025
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

typedef struct node {
    int data;
    struct node *left, *right;
    int ht;
} node;

node *insert(node *, int);
void preorder(node *);
int height(node *);
node *rotateright(node *);
node *rotateleft(node *);
node *RR(node *);
node *LL(node *);
node *LR(node *);
node *RL(node *);
int BF(node *);

int main() {
    node *root = NULL;
    int x, n, i;

    scanf("%d", &n);
    for (i = 0; i < n; i++) {
        scanf("%d", &x);
        root = insert(root, x);
    }

    preorder(root);
    return 0;
}

node *insert(node *T, int x) {
    if (T == NULL) {
        T = (node *)malloc(sizeof(node));
        T->data = x;
        T->left = NULL;
        T->right = NULL;
    } else if (x > T->data) {
        T->right = insert(T->right, x);
        if (BF(T) == -2) {
            if (x > T->right->data)
                T = RR(T);
            else
                T = RL(T);
        }
    } else if (x < T->data) {
        T->left = insert(T->left, x);
        if (BF(T) == 2) {
            if (x < T->left->data)
                T = LL(T);
            else
                T = LR(T);
        }
    }

    T->ht = height(T);
    return T;
}

int height(node *T) {
    int lh, rh;
    if (T == NULL)
        return 0;

    lh = (T->left) ? 1 + T->left->ht : 0;
    rh = (T->right) ? 1 + T->right->ht : 0;

    return (lh > rh) ? lh : rh;
}

node *rotateright(node *x) {
    node *y = x->left;
    x->left = y->right;
    y->right = x;

    x->ht = height(x);
    y->ht = height(y);

    return y;
}

node *rotateleft(node *x) {
    node *y = x->right;
    x->right = y->left;
    y->left = x;

    x->ht = height(x);
    y->ht = height(y);

    return y;
}

node *RR(node *T) {
    return rotateleft(T);
}

node *LL(node *T) {
    return rotateright(T);
}

node *LR(node *T) {
    T->left = rotateleft(T->left);
    return rotateright(T);
}

node *RL(node *T) {
    T->right = rotateright(T->right);
    return rotateleft(T);
}

int BF(node *T) {
    int lh, rh;

    if (T == NULL)
        return 0;

    lh = (T->left) ? 1 + T->left->ht : 0;
    rh = (T->right) ? 1 + T->right->ht : 0;

    return lh - rh;
}

void preorder(node *T) {
    if (T != NULL) {
        printf("%d(Bf=%d) ", T->data, BF(T));
        preorder(T->left);
        preorder(T->right);
    }
}

```

## Output:

![image](https://github.com/user-attachments/assets/534ee8cf-1ce1-41a0-8f2c-e92be91d9f25)

## Result:
Thus, the function to perform right rotation in an AVL Tree is implemented successfully.
