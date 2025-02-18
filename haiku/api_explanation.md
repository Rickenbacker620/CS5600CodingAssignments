# Linux APIs Used in Haiku Server/Client

## Socket APIs

### socket()
```c
int socket(int domain, int type, int protocol)
```
Creates a new socket descriptor for network communication.
- `domain`: Usually AF_INET for IPv4 internet protocols
- `type`: SOCK_STREAM for TCP connection
- `protocol`: Usually 0 for default protocol

### bind()
```c
int bind(int sockfd, const struct sockaddr *addr, socklen_t addrlen)
```
Assigns an address to a socket.
- `sockfd`: Socket file descriptor
- `addr`: Address structure containing IP and port
- `addrlen`: Size of address structure

### listen()
```c
int listen(int sockfd, int backlog)
```
Marks socket as passive for accepting incoming connections.
- `sockfd`: Socket file descriptor
- `backlog`: Maximum length of pending connections queue

### accept()
```c
int accept(int sockfd, struct sockaddr *addr, socklen_t *addrlen)
```
Accepts an incoming connection on a listening socket.
- Returns new socket descriptor for the accepted connection

### connect()
```c
int connect(int sockfd, const struct sockaddr *addr, socklen_t addrlen)
```
Initiates a connection on a socket to a specified address.
- Used by client to connect to server

## Data Transfer APIs

### send()
```c
ssize_t send(int sockfd, const void *buf, size_t len, int flags)
```
Transmits data on a connected socket.
- Returns number of bytes sent or -1 on error

### read()
```c
ssize_t read(int fd, void *buf, size_t count)
```
Reads data from a file descriptor (including sockets).
- Returns number of bytes read or -1 on error

## Socket Address APIs

### inet_pton()
```c
int inet_pton(int af, const char *src, void *dst)
```
Converts IP address from text to binary form.
- `af`: Address family (AF_INET for IPv4)
- `src`: Source address string
- `dst`: Destination binary address structure

## System Control APIs

### setsockopt()
```c
int setsockopt(int sockfd, int level, int optname, const void *optval, socklen_t optlen)
```
Sets options on a socket.
- Used to configure socket behavior (e.g., address reuse)

## Signal Handling

### signal()
```c
void (*signal(int signum, void (*handler)(int)))(int)
```
Sets up signal handlers for graceful program termination.
- `SIGINT`: Handle Ctrl+C
- `SIGTERM`: Handle termination request

## Resource Management

### close()
```c
int close(int fd)
```
Closes a file descriptor (including sockets).
- Important for cleaning up resources

## Data Structures

### struct sockaddr_in
```c
struct sockaddr_in {
    short            sin_family;   // AF_INET
    unsigned short   sin_port;     // Port number
    struct in_addr   sin_addr;     // Internet address
    char             sin_zero[8];  // Padding
};
```
Structure for IPv4 socket addressing.

### Here is a link to a tutorial on socket programming in C:
https://www.geeksforgeeks.org/socket-programming-cc/