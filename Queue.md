## Implemented Queue using an Array

```
class Queue:
    def __init__(self):
        self.queue=[]

    def is_empty(self):
        return self.queue==0
    
    def Enqueue(self,value):
        self.queue.append(value)

    def Dequeue(self):
        if not self.is_empty():
            return self.queue.pop(0)
        else:
            return "Queue is empty"

    def front(self):
        if not self.is_empty():
            return self.queue[0]
        else:
            return "Queue is empty"

    def rear(self):
        if not self.is_empty():
            return self.queue[-1]
        else:
            return "Queue is empty"

    def size(self):
        return len(self.queue)
    
q = Queue()
q.Enqueue(1)
q.Enqueue(2)
q.Enqueue(3)
q.Enqueue(4)
print("Queue:",q.queue)
print("Dequeue:",q.Dequeue())
print("Queue:",q.queue)
print("Front:",q.front())
print("Rear:",q.rear())
print("Size:",q.size())
print("Is Empty:",q.is_empty())

```