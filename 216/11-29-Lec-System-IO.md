# System IO

## Unix I/O

- Standard I/O generally uses buffers, Unix I/O doesn't
- Mixing the two can cause weird things to happen
- In Unix, a file is just a sequence of bytes
- All I/O devices are modelled as files, keyboard, screen, disks, etc.
- By using Unix I/O we can not only read/write from files but also send data between processes

## File descriptors

- Every process has a file descriptor table that keeps track of open files
- The file descriptor table lives in the kernel, specifically in the process control block
- A file descriptor is simply a nonnegative integer
- When you open a file a new entry is allocated in the file descriptor table.
  The file descriptor value represents an index in the file descriptor table

- Each process has three default files: stdin, stdout, stderr (file descriptors 0, 1, 2 respectively)
  - Use `STDIN_FILENO`, `STDOUT_FILENO`, `STDERR_FILENO` instead of 0, 1, 2
- Multiple processes can have the same file opened
- Closing a file in one process doesn't close it in other processes
- The kernel relies on an open file table to keep track of all open files in the system
  - Each entry in that table is called an open file descriptor
  - That table is shared by all processes

- A `fork` call copies the file descriptor table
  - So if you have a file with "abc" and parent reads "ab", child would then only read "c", not "abc"
- An `exec*` call doesn't overwrite the file descriptor table

An open file descriptor has the following:

- position: Where in the file you currently are
- ref count: How many times the file has been opened
- inode: For every file there's an inode, and there's an inode table containing
  information about that file

## File operations

- Use `open` to open file (using Unix I/O)
  - Returns file descriptor (`int`)
  - For standard I/O, we used `fopen`

Two overloads:

```c
int open(const char *filename, int flags);
int open(const char *filename, int flags, mode_t mode);
```
