# binary_search_in_tree
There is a code of binary search
#include<stdio.h>
#include<stdlib.h>

struct vertex{
    int data;
    struct vertex* left;
    struct vertex* right;
};

struct vertex* newvertex(int data){
    struct vertex* newvertex=(struct vertex*)malloc(sizeof(struct vertex));
    newvertex->data=data;
    newvertex->left=NULL;
    newvertex->right=NULL;
    return newvertex;
}

 
void main(){
    struct vertex* root=newvertex(5);
    root->left=newvertex(3);
    root->right=newvertex(7);
    root->left->left=newvertex(2);
    root->left->right=newvertex(4);
    

    root->right->left=newvertex(6);
    root->right->right=newvertex(8);
    int search=4;
    struct vertex* current=root;
    while(current!=NULL){
        if(current->data==search){
            printf("Found %d\n",search);
            break;
        }
        else if(current->data>search){
            current=current->left;
        }
        else{
            current=current->right;
        }
    }
    if(current==NULL){
        printf("%d not found\n",search);
    }
}


