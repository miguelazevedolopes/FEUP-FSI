## Task 1

## Task 2

The first program that is given prints a list of environment variables. 

After commenting the printenv() line on the child process case and uncommenting the same line in the parent process case, the program also printed a list of environment variables.

After using the diff command to compare both output files we arrived at the conclusion that child and parent processes share the same environment variables.

## Task 3

The first program program that is given doesn't print out anything.

After making the changes that are sugested the program prints out a list of environment variables.

After analysing the different outputs, as well as the functioning of the execve() system call function we realized that the reason that in the first step there was no output was because the last argument of the execve function is an array of pointers to strings which are passed as the environment of the new program.

Since in the first step no array was passed, the environment wasn't conserved and therefore there was nothing for the /urs/bin/env program to print. When we changed the last argument from NULL to environ (an array of strings) we passed the environment to the new execution which explains the change observed.

## Task 4

As expected the system() function passed the environment variables therefore when we ran it, a list of environment variables was printed.

## Task 5

After checking all the environment variables we observed that both the PATH and arbitrary environment variables we had set had been passed down to the Set-UID child process, however the LD_LIBRARY_PATH wasn't set in the Set-UID child process.

## Task 6

We were able to run a program (not a malicious one ? i don't know how to write one :D). I think it was running with root privileges, but I'm not sure. 

