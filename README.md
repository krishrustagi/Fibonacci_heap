# Fibonacci_heap
## What Is Fibonacci Heap
1. A Fibonacci heap is a specific implementation of the heap data structure that makes use of Fibonacci numbers.  
2. A Fibonacci heap is a collection of trees satisfying the minimum-heap property, that is, the key of a child is always greater than or equal to the key of the parent. This implies that the minimum key is always at the root of one of the trees.  
3. A Fibonacci Heap maintains a pointer to a minimum value (which is the root of a tree). All tree roots are connected using a circular doubly linked list, so all of them can be accessed using a single ‘min’ pointer.  
4. Fibonacci heap are mainly called so because Fibonacci numbers are used in the running time analysis. Also, every node in Fibonacci Heap has degree at most O(log n) and the size of a subtree rooted in a node of degree k is at least Fk+2, where Fk is the kth Fibonacci number.  
5. In Fibonacci heap, a node can have more than two children.  
6. In Fibonacci Heap, trees can have any shape even if all trees can be single nodes.  
7. A Fibonacci heap is a type of heap that supports merging, insertion, decrease-key* and find-min in O(1) amortized time, and delete and delete-min in O(logn) amortized time.
8. An example of Fibonacci Heap consisting of five min-heap-ordered trees and 14 nodes.  
![download](https://user-images.githubusercontent.com/54409969/106282500-ac30d600-6266-11eb-9b6a-7066830fc937.png)


## Properties of Fibonacci Heap:
1. It is a set of min heap-ordered trees. (i.e. The parent is always smaller than the children.)  
2. A pointer is maintained at the minimum element node.  
3. It consists of a set of marked nodes. (Decrease key operation) i.e. Each node has a special Boolean value which determines whether a node has lost a child since it was made child of another node. We mark the node in illustration if it’s true.  
4. The trees within a Fibonacci heap are unordered but rooted.  
5. The root degrees are not unique.  
6. The trees are not necessarily Binomial trees.  
7. Siblings are bi-directionally linked and hence it is implemented using doubly linked lists.  
8. Each node in a Fibonacci heap stores:  
    ● A pointer to its parent.  
    ● A pointer to the next sibling.  
    ● A pointer to the previous sibling.  
     	● A pointer to an arbitrary child.  
    ● A bit for whether it's marked.  
    ● Its order.  
    ● Its key.  
    ● Its element. 
    
## Memory Representation of Fibonacci Heap  

The roots of all the trees are linked together for faster access. The child nodes of a parent node are connected to each other through a circular doubly linked list as shown below.  
There are two main advantages of using a circular doubly linked list.  
Deleting a node from the tree takes O(1) time.  
The concatenation of two such lists takes O(1) time.  


Data Structure:
```
struct node 
{ 
	node* parent; 	// Parent pointer 
	node* child; 	// Child pointer 
	node* left; 	// Pointer to the node on the left 
	node* right; 	// Pointer to the node on the right 
	int key; 		// Value of the node 
	int degree; 	// Degree of the node 
	char mark; 	// Black or white mark of the node 
	char c; 		// Flag for assisting in the Find node function 
};
```

