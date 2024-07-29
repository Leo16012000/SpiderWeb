[[2024-07-23]]
# Process
fix memory, PID, at least 1 main thread
# Thread
1-2MB, sharing heap memory
many threads -> stack overflow
race condition risk in heap
core CPU * 2
1 core 1 thread, context switch
fix size causes: stack overflow with deep recursion, waste of memory with simple task
![[Pasted image 20240723084917.png]]

