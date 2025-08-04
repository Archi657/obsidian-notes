Determiate version of the glibc on a system
`/lib/libc.so.6` .

### Find libraries linked to a executable

`ldd executable | grep libc`

This might execute the program so do not use in random/sus programs.

Safer alternative is 
`objdump -p /path/to/program | grep NEEDED` https://man7.org/linux/man-pages/man1/ldd.1.html

### Access local variables
`char **environ`

## IPC
Interprocess communication (IPC), including the following:
- signals, which are used to indicate that an event has occurred;
- pipes (familiar to shell users as the | operator) and FIFOs, which can be used to
transfer data between processes;
- sockets, which can be used to transfer data from one process to another, either
on the same host computer or on different hosts connected by a network;
- file locking, which allows a process to lock regions of a file in order to prevent
other processes from reading or updating the file contents;
- message queues, which are used to exchange messages (packets of data) between
processes;
- semaphores, which are used to synchronize the actions of processes; and
- shared memory, which allows two or more processes to share a piece of memory.
When one process changes the contents of the shared memory, all of the other
processes can immediately see the changes.
# Process
Created via fork() and exec().
setrlimit(), each resource has a soft limit/hard limit.
# Memory

## Mapping
mmap() system call creates a new memory mapping in the calling process's virtual address space.

When a mapping is private,
modifications to the contents of the mapping are not visible to other processes and
are not carried through to the underlying file. When a mapping is shared, modifica-
tions to the contents of the mapping are visible to other processes sharing the same
mapping and are carried through to the underlying file.

# Signals
# Threads
Each process can have multiple threads of exe-
cution. One way of envisaging threads is as a set of processes that share the same
virtual memory, as well as a range of other attributes. Each thread is executing the
same program code and shares the same data area and heap. However, each thread
has it own stack containing local variables and function call linkage information
