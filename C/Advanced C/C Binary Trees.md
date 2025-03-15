## Node Structure
```C
typedef struct node{
    struct node* left;
    struct node* right;
    int data;
}node;
```
*Note: Variable "data" can have any type*
## Creating the Tree
### Creating a new node
```C
node* __NewNode__(const int inp_data){
    node* newtree = (node*)malloc(sizeof(node));
    if(newtree == NULL){
        perror("Fatal Error: ");
  
        #ifdef EXIT_ON_BAD_ALLOC
        exit(EXIT_FAILURE);
        #endif
    }
    newtree->left = NULL;
    newtree->right = NULL;
    newtree->data = inp_data;

    return newtree;
}
```
*Note: it should be checked if the dynamic allocation (malloc) fails in order to avoid segmentation faults*
### Adding a new node to a tree
```C
node* Insert(node* restrict root, const int inp_data){
    if(root == NULL){
        return __NewNode__(inp_data);
    }

    // Condition to check a node
    // Example: if(inp_data < root->data){
    //     root->left = Insert(root->left, inp_data);
    // }else if(inp_data > root->data){
    //    root->right = Insert(root->right, inp_data);
    // }
  
    return root;
}
```
The function will loop recursively (using a given a condition) until it finds an uninitialized node where it will insert the new node. 
## Freeing the Tree
```C
void FreeTree(node* restrict root){
    if(root != NULL){
        FreeTree(root->left);
        FreeTree(root->right);
  
        free(root);
    }
}
```
Using postorder traversal ensures that the children are freed before the parents, preventing possible segmentation faults
## Traversal
### Inorder (left-root-right)
```C
void InorderTraversal(const node* restrict root){
    if(root != NULL){
        InorderTraversal(root->left);
        // Do something with root->data
        // Example: printf("%d ", root->data); 
        InorderTraversal(root->right);
    }
}
```
*The function type should be changed according to the returned value*
### Preorder (root-left-right)
```C
void PreorderTraversal(const node* restrict root){
    if(root != NULL){
        // Do something with root->data
        // Example: printf("%d ", root->data); 
        PreorderTraversal(root->left);
        PreorderTraversal(root->right);
    }
}
```
*The function type should be changed according to the returned value*
### Postorder (left-right-root)
```C
void PostorderTraversal(const node* restrict root){
    if(root != NULL){
        PostorderTraversal(root->left);
        PostorderTraversal(root->right);
        // Do something with root->data
        // Example: printf("%d ", root->data); 
    }
}
```
*The function type should be changed according to the returned value*
# Binary Search Trees
Binary Search Trees are Binary Trees that have ordered nodes to make searching elements quick.

When inserting new nodes, the elements should be arranged from lower (left) to higher (right).

Inorder Traversal is usually recomended for traversing these types of trees.
## Searching
```C
node* Search(node* restrict root, const int inp_data){
    if(root == NULL){
        return NULL;
    }
    if(root->data == inp_data){
        return root;
    }
  
    if(inp_data < root->data){
        return Search(root->left, inp_data);
    }else{
        return Search(root->right, inp_data);
    }
}
```
The function will return a pointer to the node with the same data as the searched one
# Visualization
![Binary tree - Wikipedia](https://upload.wikimedia.org/wikipedia/commons/5/5e/Binary_tree_v2.svg)#C #DataStructures #Trees #ComplexDataStructures#Programming