## Task 1

We ran both binaries and as expected in both cases a shell was invoked.

![Logbook 5 - Task 1] (logbook5-task1.png)

## Task 2

We successfully compiled the file. First using the commands given and then using the makefile.

![Logbook 5 - Task 2] (logbook5-task2.png)

## Task 3

After debugging the program as suggested, we obtained the distance between the buffer's starting position and the position of the ebp (0xFFFFCA48-0xFFFFC9DC=0x6C=108).

![Logbook 5 - Task 3 - Part 1] (logbook5-task3-1.png)

We chose the last bytes to place the shell code (start=517-length of the shell code).

As suggested, to get the buffer address, we included a printf in the stack.c code.

The offset is 108+4 because the return address is always at ebp+4.

To get our new return address, we added our offset (108 + 4) to the address of the buffer, plus 4 bytes (the space needed to write our 32 bit address). We could've added more bytes, since our shell code is located at the end of the 517 bytes.

After running our exploit we ran the stack-L1 program and verified that the exploit had worked because the shell was invoked (see attached image).

![Logbook 5 - Task 3 - Part 2] (logbook5-task3-2.png)
