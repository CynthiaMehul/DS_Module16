# Ex 4C B-Tree
## DATE: 07/04/2025
## AIM:
To write a C function to delete an element in a B Tree.

## Algorithm
1. Start the program.
2. Include required libraries.
3. Create a structure to store the nodes.
4. Define the function to delete an element of a B tree.
5. End the program.

## Program:
```
/*
Program to write a C function to delete an element in a B Tree
Developed by: Cynthia Mehul
RegisterNumber: 212223240020
*/

#include<stdio.h>
struct BTreeNode {
  int item[MAX + 1], count;
  struct BTreeNode *linker[MAX + 1];
};

struct BTreeNode *root;
void delete (int item, struct BTreeNode *myNode) {
    struct BTreeNode *tmp;
    if(!delValFromNode (item,myNode))
    {
        printf("Not present\n");
        return;
    }
    else
    {
        if(myNode->count == 0)
        {
            tmp= myNode;
            myNode = myNode->linker[0];
            free(tmp);
        }
    }
    root=myNode;
    return;
}
```

## Output:

![image](https://github.com/user-attachments/assets/af7c94cf-62a1-4cb9-ba1f-b3b0c4ef738a)

## Result:
Thus, the C function to delete an element in a B Tree is implemented successfully.
