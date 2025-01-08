## Implemented Linked_list.......
```
class Node:
    def __init__(self,data):
        self.data=data
        self.next=None

class Linked_list:
    def __init__(self):
        self.head=None
        self.tail=None
    
    def append(self,data):
        new_node=Node(data)
        if self.tail:
            self.tail.next=new_node
        else:
            self.head=new_node
    
    def preppend(self,data):
        new_node=Node(data)
        if self.head:
            new_node.next=self.head
            self.head=new_node
        else:
            self.head=new_node
        self.tail=new_node

    def delete(self,data):
        if self.head is None:
            return "Linked list is empty"
        else:
            current=self.head
            previous=None
            while current:
                if current.data==data:
                    if previous:
                        previous.next=current.next
                    else:
                        self.head=current.next
                    if current==self.tail:
                        self.tail=previous
                    return 
                previous=current
                current=current.next
    
    def search(self,data):
        current=self.head
        while current:
            if current.data==data:
                return current
            current=current.next
        return None
    
    def display(self):
        elements=[]
        current=self.head
        while current:
            elements.append(current.data)
            current=current.next
        return elements
    

ll=Linked_list()

ll.append(1)
ll.append(2)
ll.append(3)
ll.append(4)
ll.append(5)
ll.append(6)
# print(ll.display())
print(ll())  

```