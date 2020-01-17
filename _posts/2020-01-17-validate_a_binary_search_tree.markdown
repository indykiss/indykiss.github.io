---
layout: post
title:      "Validate a binary search tree"
date:       2020-01-17 19:22:11 +0000
permalink:  validate_a_binary_search_tree
---


Write a function to check that a binary tree is a valid binary search tree. 

To be clear about the expectations, we define a binary search tree as a tree where:
- The left node is always less than its parent && 
- The right node is always greater than the parent


Right off the bat, there's a few questions to be asked about:
- Can we assume that all values will be positive integers?  [Yes]
- Can we assume the binary tree is perfect, where there's always 2 leaves per parent node? [Sure]
- In the edge case where there is no treeRoot given, can we call that a BST? [Yes]

My general strategy is to set up some conditionals to test the node parent <--> node child relationships as we traverse through the tree. If the binary tree passes all the tests for BST, then we return true. 

Since we're looking at the relationship between parent to child, we should use a depth-first traversal. 

We can create some upper and lower bounds that each node needs to adhere to to help this relationship testing. 

I can think of two possible ways to do this:

**Recursively**; simpler to implement in code, but really not time efficient. This function would be susceptible to stack overflow. 

**Iteratively**; little more work to implement in code, but much more time efficient. O(n) time and O(n) space. 




```

// Let's start by making a binary node class:

class BinaryTreeNode {
  constructor(value) {
    this.value = value;
    this.left  = null;
    this.right = null;
  }

  insertLeft(value) {
    this.left = new BinaryTreeNode(value);
    return this.left;
  }

  insertRight(value) {
    this.right = new BinaryTreeNode(value);
    return this.right;
  }
}


// Iterative!
function isBinarySearchTree(treeRoot) {

  // S1: Start at root. Make fake lower and upper bounds
  const nodeAndBoundsStack = [];
  nodeAndBoundsStack.push({
    node: treeRoot,
    lowerBound: Number.NEGATIVE_INFINITY,
    upperBound: Number.POSITIVE_INFINITY    
  })

  // S2: Depth-first traversal 
  while(nodeAndBoundsStack.length) {
    const{ node, lowerBound, upperBound } = 
      nodeAndBoundsStack.pop();
      
      // Make sure node is valid to continue 
      if(node.value <= lowerBound || node.value >= upperBound) {
        return false;
      }
      
      // If it's a left child node, it has to be smaller than the 
        // current node (parent node)
      if(node.left) {
        nodeAndBoundsStack.push({
          node: node.left,
          lowerBound,
          upperBound: node.value
        });
      }
      
      // If it's a right child node, it must be bigger than parent
      if(node.right) {
        nodeAndBoundsStack.push({
          node: node.right, 
          lowerBound: node.value,
          upperBound
        })
      }
  }
  // S3: If all nodes passed the tests, then we have a BST
  return true;
}


// Recursive!
// S1: Add a second and third input parameter for lower/upper bounds
function isBinarySearchTree2(treeRoot, lowerBound, upperBound) {

  // S2: Start at root. Make fake lower and upper bounds
  lowerBound = Number.NEGATIVE_INFINITY;
  upperBound = Number.POSITIVE_INFINITY;

  // S3: If tree root doesn't exist, then yes BST
  if(!treeRoot) {
    return true;
  }
  
  // S4: If treeRoot is not within the bounds, not BST
  if(treeRoot.value >= upperBound || treeRoot.value <= lowerBound) {
    return false;
  }
  
  // S5: Let's check if the left and right node are in the bounds by recursing
  return isBinarySearchTree2(treeRoot.left, lowerBound, treeRoot.value)
    && isBinarySearchTree2(treeRoot.right,  treeRoot.value, upperBound);
}

```



Thanks for reading! <br>
Indy

