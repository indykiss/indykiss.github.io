---
layout: post
title:      "JavaScript Algos Pt. 4"
date:       2019-11-29 17:14:57 +0000
permalink:  javascript_algos_pt_4
---


> "I have never been asked about this in an interview or used one in the past 10+ years of programming, but you have to know what a **linked list** is." <br><br>
> Programmer friend after hearing me complain about why this is a paradigm when we have arrays. 

Fast forward a couple days of studying linked lists, and... eureka! 

A linked list is a collection of data broken down by nodes, in which each node contains two main things- data and a reference to the next node. A linked list will always (unless number of nodes is less than 2), have a head and a tail node. 

Linked lists can be useful data structures in that they allow run-time efficient data manipulation. If the data set in the structure is quite large, when we insert or remove a new node, there's no need to reorganize the entire structure like what happens when you add/remove an element to an array.  

With that, let's get into it! 

For this blog article, I'm going to work through a simple linked list setup. We are going to create a linked list where we can do the following: 
- Make the list itself
- Add a head node
- Add a tail node
- Count how many total nodes exist
- Return the head node
- Return the tail node
- Remove all the nodes
- Remove the head node
- Remove the tail node 

There's a bit of pseudocode intertwined with the code itself to help explain my thinking for the more complicated functions. 

In next week's blog, I'm going to flesh this out to become a more fully executed algo with an input/ expected output and a few more diffcult functions (accessing a node at an index, inserting a node at any index, etc). 

```

// Make a node class
class Node {
    constructor(data, next = null) {
        this.data = data;
        this.next = next;
    }
}

// Make the linked list class and initialize
class LinkedList {
    constructor() {
        this.head = null;
    }

    // Add a new head
    insertFirst(data) {
        // Make a new node thats connected to the head node/ previous node
        const node = new Node(data, this.head);
        // Make this node the new head node
        this.head = node;
    }
		
    // Add a new tail
    insertLast(data) {
        // Let's find the last node 
        const last = this.getLast();
        // If there is a last node, let's make a new node and push it to the end
        if (last) {
            last.next = new Node(data); 
        } else {
            this.head = new Node(data)
        }
    }

    // Count the total number of nodes
    size(nodes) {
        let counter = 0;
        let node = this.head 

        // If there is a head node, then it will counter++ then continue to next node
        while(node) {
            counter++;
            node = node.next;
        }
        return counter;
    }

    // Return the head
    getFirst() {
        return this.head;
    }

    // Return the tail
    getLast() {
        let node = this.head

        if(!node) {
            return null;
        }

        while(node) {
            if(!node.next) {
                return node;
            }
            node = node.next; 
        }
    }

    // Remove all the nodes
    clear() {
        this.head = null;
    }

    // Remove the head
    removeFirst() {
        if(!this.head) {
            return null;
        }
        this.head = this.head.next;
    }
 
    // Remove the tail
    removeLast() {
        let previous = this.head;
        let node = this.head.next;
        // edge cases; if is empty or if theres only 1 node

        if(!this.head) {
            return null;
        }

        if(this.head.next = null) {
            this.head = null;
        }

        while(node.next) {
            previous = node; 
            node = node.next;
        }
        previous.next = null;
    }

}
```


Thanks for reading!<br>
Indy
