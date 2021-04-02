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


## Problem 1

### Problem 1 Solution


## Example 2

This python code is an example of what the Web server from earlier might look like.

'''python

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
'''
