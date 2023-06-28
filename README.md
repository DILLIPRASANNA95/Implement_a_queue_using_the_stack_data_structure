# Implement_a_queue_using_the_stack_data_structure
class Queue:
    def __init__(self):
        self.enqueue_stack = []
        self.dequeue_stack = []

    def enqueue(self, item):
        self.enqueue_stack.append(item)

    def dequeue(self):
        if not self.dequeue_stack:
            if not self.enqueue_stack:
                raise IndexError("Queue is empty")
                
            while self.enqueue_stack:
                self.dequeue_stack.append(self.enqueue_stack.pop())
        return self.dequeue_stack.pop()

    def is_empty(self):
        return not self.enqueue_stack and not self.dequeue_stack

queue = Queue()

queue.enqueue(1)
queue.enqueue(2)
queue.enqueue(3)

print(queue.dequeue())  
print(queue.dequeue())  

queue.enqueue(4)
queue.enqueue(5)

print(queue.dequeue())  
print(queue.dequeue())  
print(queue.dequeue())  

print(queue.is_empty()) 
