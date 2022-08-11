#implementing a doubly linked list:

#Define a class that will create nodes and pointers

from curses import beep
from email.quoprimime import header_check
from re import I, L
from typing import ItemsView, Iterator


#Define a class that will create nodes with pointers and data inside.
class Doubly_Linked:
    def __init__(self,val):
        self.next= None
        self.prev= None
        self.data= val

# Class that defines the pointers    
class Create_List:
    def __init__(self):
        self.HeadPointer= None
        self.TailPointer= None
    #Adding nodes at the end of the list
    def add_nodes(self, val):
        if self.HeadPointer is None:
            newnode = Doubly_Linked(val)
            self.HeadPointer= newnode
        else:
            Iterator_head = self.HeadPointer
            while Iterator_head.next!=None:
                Iterator_head= Iterator_head.next
            
            #when you reach the last item of the list:
            if Iterator_head.next==None:
                newnode= Doubly_Linked(val)
                Iterator_head.next= newnode
                newnode.prev= Iterator_head
                self.TailPointer= newnode
    
    #Adding a new node after a certain node.
    def add_after_node(self, newval, node):
        head_iterator= self.HeadPointer
        #Mindful: don't use next pointer when try to look for data
        while head_iterator is not None:
            if head_iterator.data==node:
                if head_iterator.next==None:
                    newnode=Doubly_Linked(newval)
                    head_iterator.next=newnode
                    newnode.prev=head_iterator
                    self.TailPointer=newnode
                    break
                else:
                    newnode= Doubly_Linked(newval)
                    newnode.next=head_iterator.next
                    head_iterator.next.prev=newnode
                    head_iterator.next=newnode
                    newnode.prev=head_iterator
                    break    
            else:
                head_iterator= head_iterator.next
        if head_iterator==None:
            print ("The node does not exist.")

    #Adding a new node before a certain node.
    def add_before_node(self, newval, node):
        head_iterator= self.HeadPointer
        while head_iterator is not None:
            if head_iterator.next.data == node:
                newnode = Doubly_Linked(newval)
                newnode.next=head_iterator.next
                head_iterator.next.prev=newnode
                newnode.prev = head_iterator
                head_iterator.next=newnode
                break
            else:
                head_iterator= head_iterator.next
            
            if head_iterator==None:
                print("The  node doesn't exsit ")
    #Deleting nodes left to right
    def Del_left_To_Right(self):
        if self.HeadPointer==None:
            print("List contains no elements")
        else:
            #while loop will traverse all the nodes till the last one
            while self.HeadPointer.next!=None:
                self.HeadPointer= self.HeadPointer.next
                self.HeadPointer.prev=None
            if self.HeadPointer.next==None:
                self.HeadPointer=None
                self.TailPointer= None
            if self.HeadPointer==None and self.TailPointer==None:
                print("All the elements have been deleted. ")
    
    #Deleting nodes right to left
    def Del_Right_To_Left(self):
        if self.TailPointer is None:
            print("Nothig to delete from right to left")
        
        else:
            while self.TailPointer.prev !=None:
                self.TailPointer= self.TailPointer.prev
            if self.TailPointer.prev==None:
                self.TailPointer=None
                self.HeadPointer=None
            if self.TailPointer==None and self.HeadPointer==None:
                print(" All the elements has been deleted from right to left.")

    #Deleting any nodes.
    def del_node(self, node):
    
        #if the deleting element is the last node:
        if  self.TailPointer.data==node:
            self.TailPointer= self.TailPointer.prev
            self.TailPointer.next= None
                
        # if the deleting element is the firs node:
        elif self.HeadPointer.data==node:
             self.HeadPointer = self.HeadPointer.next
             self.HeadPointer.prev=None
        #if the deleting node is any nodes besided head or tail.
        else:
            Head_Iterator= self.HeadPointer
            Tail_Iterator= self.TailPointer

            while Head_Iterator.next is not None:
                if Head_Iterator.next.data == node:
                    #Caution: Always close links from left to right.
                    Head_Iterator.next.next.prev = Head_Iterator
                    Head_Iterator.next = Head_Iterator.next.next
                    break
                Head_Iterator= Head_Iterator.next
        
            
    #Tarversing nodes Left to right

    def traverse_left_To_right(self):
        if self.HeadPointer is None:
            print("List has been found empty while reading left to right")
        else:
            Iterator_head = self.HeadPointer
            while Iterator_head is not None:
                print(Iterator_head.data)
                Iterator_head = Iterator_head.next

    #Traversing nodes Right to left
    def traverse_right_To_left(self):
        if self.TailPointer is None:
            print(" List has been found empty while reading right to left ")
        else:
            Iterator_head= self.TailPointer
            while Iterator_head is not None:
                print(Iterator_head.data)
                Iterator_head= Iterator_head.prev

           
            
            
linkedlist= Create_List()

linkedlist.add_nodes(10)
linkedlist.add_nodes(11)
linkedlist.add_nodes(12)
linkedlist.add_nodes(13)
linkedlist.add_nodes(14)
linkedlist.add_before_node(200,12)
linkedlist.add_before_node(100,12)
linkedlist.add_after_node(500,12)
linkedlist.add_after_node(600,12)

print("**********")


linkedlist.traverse_left_To_right()
    

linkedlist.del_node(600)

print("**********")

linkedlist.traverse_right_To_left()

    
        


