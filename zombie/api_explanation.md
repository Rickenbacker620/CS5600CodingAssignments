# Linux APIs in Zombie Process Example

This document explains the key Linux/POSIX APIs used in the zombie process demonstration.

## fork()
- **Header**: `<unistd.h>`
- **Purpose**: Creates a new process by duplicating the calling process
- **Return Value**: 
  - Returns PID of child to parent
  - Returns 0 to child
  - Returns -1 on error
- **Usage**: Used to create the child process that will become a zombie

## getpid()
- **Header**: `<unistd.h>`
- **Purpose**: Gets the process ID of the calling process
- **Return Value**: Returns the process ID of the calling process
- **Usage**: Used to display the PIDs of both parent and child processes

## exit()
- **Header**: `<stdlib.h>`
- **Purpose**: Terminates the calling process
- **Arguments**: Takes an integer status value (0 typically indicates success)
- **Usage**: Used by both parent and child to terminate. When child exits while parent is still running, it becomes a zombie

## sleep()
- **Header**: `<unistd.h>`
- **Purpose**: Suspends execution of the calling thread for a specified number of seconds
- **Arguments**: Number of seconds to sleep
- **Usage**: Used in parent process to ensure the child becomes a zombie and remains visible

## fprintf()
- **Header**: `<stdio.h>`
- **Purpose**: Writes formatted output to a specified stream
- **Usage**: Used for error reporting to stderr in case fork() fails

## Note on Zombie Processes
A zombie process is created when a child process terminates but its parent hasn't yet called wait() or waitpid() to read its exit status. The process entry remains in the process table until the parent reads the exit status or terminates itself.

To observe the zombie process:
1. Run the program
2. Use `ps -l` in another terminal
3. Look for a process with 'Z' in the status column
