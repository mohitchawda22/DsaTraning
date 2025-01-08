
## Implemented Stack using an Array.

```
class Stack:
    def __init__(self):
        self.stack=[]
        self.length=0

    def push(self,value):
        self.stack.append(value)
        self.length+=1
    
    def pop(self):
        if(self.length>0):
            self.stack.pop()
            self.length-=1
    
    def top(self):
        return self.stack[self.length - 1]
    
    def lenght(self):
        return self.length
    
obj=Stack()
obj.push(1)
obj.push(2)
obj.push(3)
obj.pop()
obj.top()
obj.lenght()
```