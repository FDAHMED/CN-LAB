#Program 5 
IMPLEMENTATION OF CONCURRENT ECHO SERVER USING 
CONNECTIONLESS SOCKET SYSTEM CALLS. 
--- 
## Algorithm: 
 
- Include appropriate header files. 
- Create a UDP Socket. 
- Fill in the socket address structure (with server information) 
- Specify the port where the service will be defined to be used by client. 
- Bind the address and port using bind() system call. 
- Create a new process (child process) using fork(), to handle the client request. The parent 
process will be waiting for new incoming connections. 
- Receive a message from the Client using recvfrom() system call. 
- Send the result of the request made by the client using sendto() system call. 

## Client:

- Include appropriate header files. 
- Create a UDP Socket. 
- Fill in the socket address structure (with server information) 
- Specify the port of the Server, where it is providing service
- For echo server, send a message to the server to be echoed using sendto() system call. 
                   Receive the result of the request 
 
## Server: 
 
 
- made to the server using recvfrom() system call. 
- Write the result thus obtained on the standard output. 
