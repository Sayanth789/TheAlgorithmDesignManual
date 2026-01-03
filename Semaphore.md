## Wait and Release 

#### To avoid concurrency 


`wait(asemaphore`) 
if `asemaphore's counter > 0` then
  decrement `asemaphore's counter 
else 
  put the counter in a `semaphore's queue` 
  attempt to transfer control to some ready task 
  (if the task-ready queue is empty, deadlock occours) 
end if 

`release(asemaphore)`

if `asemaphore's` queue is empty(no task is waiting) **then** 
  increment `asemaphore`'s counter 
else 
  put the calling task in the task-ready queue 
  transfer control to a task from `asemaphore`'s queue 
end 
