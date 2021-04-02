# Queues
{basic explaination of module}


## Basics of Queueing
Queuing is essentially setting up a list of items to address. Depending on the type of queue items will be processed in order. Each item will be QUEUED, and DEQUEUED

## Examples of Queue
There are 3 examples of queues we will be covering in this tutorial; Grocery store queue, web server queue, and the reader/writer queue.

### Grocery Store Queue
This is probrably what most people think of with queues. The first item in the queue will be the first one to be used, just like a grocery store. The first person in line is the first person served. One iteme will be QUEUED at a time and one will be DEQUEUED.

![](https://github.com/PainBro/Winter_2021_Data_Structure_Tutorial/blob/main/Grocery%20Queue.png)

### Web Server Queue
this queue is similar to grocery store queue in that the first item QUEUED, will be the first item DEQUEUED. Unlike a grocery store queue, this web server queue uses an intermediary to decide which items to queue first. like with a phone line, if you call you will be connected, but if someone calls 911, their call will take priority.

![](https://github.com/PainBro/Winter_2021_Data_Structure_Tutorial/blob/main/Web%20Server%20Queue.png)

### Reader/Writer Queue
Unlike a web server, or grocery store queues, this reader/writer queue is built to handle multiple items at the same time. By juggling the processes it seems like it is working on all of them at the same time

![](https://github.com/PainBro/Winter_2021_Data_Structure_Tutorial/blob/main/Reader_writer%20Queue.png)

## Queues With Python
In python queues are often done through a list.

to enqueue you might .apprnd to a list
to Dequeue you might .pop from the list

these are some examples to help you get used to queues with python

## Example 1 

This code is an example of a simple queue

```python
class Simple_Queue:

    def __init__(self):
        self.queue = []

    def enqueue(self, value):
        self.queue.append(value)

    def dequeue(self):
        if len(self.queue) <= 0:
            raise IndexError()
        value = self.queue[0]
        del self.queue[0]
        return value
```

## Problem 1

Using the code above there is some code to raise an error in the dequeue function.
What would you have do to make it raise the error?

### Problem 1 Solution

To raise the error you would have to dequeue when there is nothing left in the queue

## Example 2

This python code is an example of what the Web server from earlier might look like.

``` python

    class Priority_Queue:

    class Node:

        def __init__(self, value, priority):
            self.value = value
            self.priority = priority

        def __str__(self):
            return "{} (Pri:{})".format(self.value, self.priority)

    def __init__(self):
        self.queue = []

    def enqueue(self, value, priority):
        new_node = Priority_Queue.Node(value, priority)
        self.queue.append(new_node)

    def dequeue(self):
        if len(self.queue) == 0:  # Verify the queue is not empty
            print("The queue is empty.")
            return None
        # Find the index of the item with the highest priority to remove
        high_pri_index = 0
        for index in range(1, len(self.queue)):
            if self.queue[index].priority > self.queue[high_pri_index].priority:
                high_pri_index = index
        # Remove and return the item with the highest priority
        value = self.queue.pop(high_pri_index).value 
        return value
        
    def __len__(self):
        return len(self.queue)

    def __str__(self):
        result = "["
        for node in self.queue:
            result += str(node)  # This uses the __str__ from the Node class
            result += ", "
        result += "]"
        return result
```

## Problem 2

For this problem try using the example code above to make a queue that will put any value of 911 first
Use the test code below to test your work

``` python
# Test
# Scenario: 911 should be put first no matter its priority
# Expected Result: 911
print("Test 1")
pQue = Priority_Queue()
pQue.enqueue('333-1124', 1)
pQue.enqueue('911', 2)
pQue.enqueue('407-6322', 3)
print(pQue.dequeue())
```

### Problem 2 Solution
A possible solution to this problem would be to add this code into the enqueue function
``` python
if (value == '911'):
            priority = 10
```

## Problem 3

Write python code to make a queue for someting in your life.
Ex. A queue to keep trach of your homework assignments you need to do.

### Problem 3 Solution

Due to the nature of the problem there isn't one solution.
If your queue works as you indended then it is correct.


