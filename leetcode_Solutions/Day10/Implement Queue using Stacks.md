# Implement Queue using Stacks
- ## Question:
>Implement a first in first out (FIFO) queue using only two stacks. The implemented queue should support all the functions of a normal queue (push, peek, pop, and >empty).
>
>Implement the MyQueue class:
>
- void push(int x) Pushes element x to the back of the queue.
- int pop() Removes the element from the front of the queue and returns it.
- int peek() Returns the element at the front of the queue.
- boolean empty() Returns true if the queue is empty, false otherwise.

- Example :

      Input
      ["MyQueue", "push", "push", "peek", "pop", "empty"]
      [[], [1], [2], [], [], []]
      Output
      [null, null, null, 1, 1, false]

      Explanation
      MyQueue myQueue = new MyQueue();
      myQueue.push(1); // queue is: [1]
      myQueue.push(2); // queue is: [1, 2] (leftmost is front of the queue)
      myQueue.peek(); // return 1
      myQueue.pop(); // return 1, queue is [2]
      myQueue.empty(); // return false
      
- ## Solution:
```cpp
class MyQueue {
public:
    stack<int> input;
    stack<int> output;
    MyQueue() {
        
    }
    
    void push(int x) {
      
        input.push(x);
        
    }
    
    int pop() {
        if(!output.empty())
        {
            int a=output.top();
            output.pop();
            return a;
        }
        else{
            while(!input.empty())
            {
                output.push(input.top());
                input.pop();
            }
            int a=output.top();
            output.pop();
            return a;
        }
    }
    
    int peek() {
        if(!output.empty())
        {
            int a=output.top();
            return a;
        }
        else{
            while(!input.empty())
            {
                output.push(input.top());
                input.pop();
            }
            int a=output.top();
            return a;
        }
    }
    
    bool empty() {
        if(input.empty() && output.empty())
            return true;
        else
            return false;
    }
};
```

## Tags
`Stack` `Design` `Queue`
