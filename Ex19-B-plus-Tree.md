# Ex19 B+ Tree
## DATE: 26.04.2025
## AIM:
To write a C function to traverse the elements in a B+ Tree.

## Algorithm
1. Start the program.
2. Include required libraries.
3. Create a structure to store the nodes of the tree.
4. Define a function to traverse the elements in a B+ tree.
5. End the program.  

## Program:
```
/*
Program to traverse the elements in a B+ Tree.
Developed by: Cynthia Mehul
RegisterNumber: 212223240020
*/

#include<stdio.h>
#include<stdlib.h>

struct B_TreeNode
{
    int *data;
    struct B_TreeNode **child_ptr;
    int leaf;
    int n;
};
struct B_TreeNode *root = NULL, *np = NULL, *x = NULL;
void traverse(struct B_TreeNode *p)
{
  int i;
    for (i = 0; i < p->n; i++)
    {
        if (p->leaf == 0)
        {
            traverse(p->child_ptr[i]);
        }
        printf("%d ",p->data[i]);
    }
    if (p->leaf == 0)
    {
        traverse(p->child_ptr[i]);
    }
}

```

## Output:

![image](https://github.com/user-attachments/assets/af30f4cb-c3f0-486c-b859-71881524a8f7)

## Result:
Thus, the function to traverse the elements in a B+ Tree is implemented successfully.
