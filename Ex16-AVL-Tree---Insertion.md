# Ex 4A AVL Tree - Insertion
## DATE: 26.04.2025
## AIM:
To write a C function to insert the elements in an AVL Tree.

## Algorithm
1. Start the program.
2. Include required libraries.
3. Create a structure to store the nodes of the tree.
4. Define the insert function in an AVL tree.
5. End the program.

## Program:
```
/*
Program to insert the elements in an AVL Tree
Developed by: Cynthia Mehul
RegisterNumber: 212223240020
*/

typedef struct node
{
int data;
struct node *left,*right;
int ht;
}node;
node *insert(node *,int);
void preorder(node *);
void inorder(node *);
int height(node *);
node *rotateright(node *);
node *rotateleft(node *);
node *RR(node *);
node *LL(node *);
node *LR(node *);
node *RL(node *);
int BF(node *);

node * insert(node *T,int x)
{
   if(T==NULL)
   {
       T=(node *)malloc(sizeof(node));
       T->data=x;
       T->left=NULL;
   }
   else
   {
       if(x>T->data)
       {
           T->right=insert(T->right,x);
           if(BF(T)==-2)
           {
               if(x>T->right->data)
               T=RR(T);
               else
               T=RL(T);
           }
       }
       else
       {
           T->left=insert(T->left,x);
           if(BF(T)==2)
           {
               if(x<T->left->data)
               T=LL(T);
               else
               T=LR(T);
           }
       }
   }
   T->ht=height(T);
   return(T);
   }


```

## Output:

![image](https://github.com/user-attachments/assets/9a2b3f79-361f-4f0c-8f3d-09b14f5a0061)

## Result:
Thus, the function to insert the elements in an AVL Tree is implemented successfully in C programming language.
