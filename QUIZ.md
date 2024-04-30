### How does the DevBoard handle received serial messages? How does this differ from the naïve approach?
The DevBoard handles serial messages by using interrupts and interrupt handlers, which is event driven. This is different fron the naive approach which involves using the `loop()` and repeatedly running `read()` if serial data is available, which isn't event driven. 
### What does `detached_callback` do? What would happen if it wasn't used?
`detached_callback` spawns a deatached thread. If we do not use it, the program will halt every time the user interacts with the GUI. 
### What does `LockedSerial` do? Why is it _necessary_?
`LockedSerial` atomizes function calls by overriding their inherited function but with with a lock acquisition before their call. This is necessary as it prevents undefined behavior due to race conditions. 
