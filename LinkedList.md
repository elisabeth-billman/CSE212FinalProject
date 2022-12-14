# Linked Lists

## Introduction
Linked Lists are a data structure that store data in a form of a chain. Each piece of data in a linked list has a connection to the next one. A linked list is a linear collection of data elements whose order is not given by their physical placement in memory. Each element points to the next. Linked Lists are super important because it is a way to collect similar data. Linked lists function as an array that can grow and shrink as needed, from any point in the array. 
A linked list can contain pretty much any type of data, strings, characters, numbers. The elements can be sorted or unsorted. They can contain duplicate elements or all unique elements

## Linked List Structure
Linked Lists are a collection of data stored in a random way within memory. Each element in a linked list is at some location in memory. Each element in a linked list is called a node. Each node has a value and is linked to the next node in the list. The first node is called the head. If you know where the head is you can go through the list one by one using each link. To loop forward through a linked list use the “next” link until you reach the end. If you are looping through a linked list from the end of the list use the “prev” links until you reach the head of the list. 

![Example of Linked List](Linkedlist.png)
 


## Inserting into a Linked List
### Insert to the beginning of the linked list
When you insert into a Linked list is only effects the neighboring elements. To insert at the head of a Linked List:
1. Create a new node (`new_node`)
2. Set the “next” of the new node to the current head (`new_node.next = self.head`)
3. Set the “prev” of the current head to the new node (`self.head.prev = new_node`)
4. Finally set the head equal to the new node (`self.head = new_node`)

If the linked list is empty then just set both the head and the tail to the new node created. 

### Insert to the end of a linked list
Inserting to the end of the linked list is similar to inserting to the beginning: 
1. Create a new node (`new_node`)
2. Set the “prev” of the new node to the current tail (`new_node.prev= self.tail`)
3. Set the “next” of the current tail to the new node (`self.tail.next = new_node`)
4. Finally set the tail equal to the new node (`self.tail = new_node`)

### Insert into the middle of a linked list
There are five steps to insert into the linked list:
1. Create a new node (`new_node`)
2. Set the "prev" of the new node to the current node (`new_node.prev = current`)
3. Set the "next" of the new node to the next node after current (`new_node.next = current.next`)
4. Set the "prev" of the "next" node after current to the new node (`current.next.prev = new_node`)
5. Set the next of the current node to the new node (`current.next = new_node`)


## Removing from a Linked List
It is very similar to remove from the head and the tail of a linked list. To remove the first node:
1. Set the "prev" of the second node (`self.head.next`) to nothing (`self.head.next.prev = None`)
2. Set the head to be the second node (`self.head = self.head.next`)

To remove the tail:
1. Set the "next" of the second to last node (`self.tail.prev`) to nothing (`self.tail.prev.next = None`)
2. Set the tail to be the second to last node (`self.tail = self.tail.prev`)

To remove from the middle:
1. Set the prev of the node after current to the node before current (`current.next.prev = current.prev`)
2. Set the next of the node before current to the node after current (`current.prev.next = current.next`)

## Advantages and Disadvantages of Linked List
One main thing that distinguishes a linked list from an array is that in an array the elements are indexed. However, in a linked list you have to start at the head and move through one by one until you reach the desired element. Linked lists are a bit slower in this way because it is done with linear time. In big O notation it is O(n). But it is faster to insert and delete an element into a linked list. Inserting an element right to the front of the Linked list can be done in constant time. 

## Example Problem
### create a linked list
Write a Python program to create a linked list.

``` python
class Node:
    # Singly linked node
    def __init__(self, data=None):
        self.data = data
        self.next = None
class linked_list:
    def __init__(self):
        # Createe an empty list
        self.head = None
        self.tail = None
        self.count = 0
    def iterate_item(self):
        # Iterate the list.
        current_item = self.head
        while current_item:
            val = current_item.data
            current_item = current_item.next
            yield val
    def append_item(self, data):
        #Append items on the list
        node = Node(data)
        if self.tail:
            self.tail.next = node
            self.tail = node
        else:
            self.head = node
            self.tail = node
        self.count += 1
items = singly_linked_list()
items.append_item('banana')
items.append_item('apple')
items.append_item('strawberry')
items.append_item('blueberry')
items.append_item('orange')
items.append_item('watermelon')
items.append_item('peach')
items.append_item('grape')
for val in items.iterate_item():
    print(val)
print("\nhead.data: ",items.head.data)
print("tail.data: ",items.tail.data)
```

#### Practice Problem: Write a Python program to delete the first item from a singly linked list.

[Welcome Page](Welcome.md)