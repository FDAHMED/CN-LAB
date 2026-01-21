#Program 6
IMPLEMENTATION OF TIME OF DAY SERVICE AS CONNECTION ORIENTED 
CONCURRENT SERVER USING SOCKET SYSTEM CALLS. 
--- 
 
 
Program Description: The Standard port numbers are the port numbers that are reserved 
forassignment for use by the application end points that communicate using the Internet's 
Transmission Control Protocol (TCP) or the User Datagram Protocol (UDP). Each kind of 
application has a designated (and thus "well-known") port number. 
In order to implement the standard ports we need to create an application for instance say client, 
which is going to invoke service which is established on the standard ports. The Client will be 
creating its socket endpoint and establish a connection with the standard server by specifiying the 
port number which has the defined service, for instance 7 for echo service. 
Algorithm: 
Client 

---
Algorithm for Concurrent Time of Day Server
### Phase 1: Setup and Initialization
- Start.

- Create a Socket: Call socket() with AF_INET (IPv4) and SOCK_STREAM (TCP) to create a connection-oriented endpoint.

- Define Server Address: Initialize a sockaddr_in structure with:

- The Protocol Family (AF_INET).

- The IP Address (192.168.0.5).

- The Port Number (3214) converted to network byte order using htons().

- Bind: Associate the socket with the defined IP and Port using the bind() system call.

### Phase 2: Connection Management
- Listen: Use listen() to put the server in passive mode, waiting for a client to request a connection.

- Accept: Use accept() to extract the first connection request from the queue. This creates a new socket (new_sockfd) specifically for this client.

### Phase 3: Concurrency (Handling the Request)
- Fork: Create a child process using fork().

- If Child Process (pid == 0):

- Receive a message from the client using recv().

- Echo (send) the received message back to the client using send().

- Get Time: Call gettimeofday() to retrieve the current system time.

- Send Time: Send the seconds component (tv_sec) of the time to the client.

- Terminate child process.

- If Parent Process:

- Print the Parent PID.

- Exit/Terminate (Note: In a standard production server, the parent would loop back to accept more clients).

### Phase 4: Termination
- Close: Close the socket descriptors to release resources.

- Stop.
 
 
## Client: 
 
- Include appropriate header files. 
 
- Create a TCP Socket. 
 
- Fill in the socket address structure (with server information) 
 
- Specify the port of the Server, where it is providing service 
 
- Establish connection to the Server using connect() system call. 
 
- For echo server, send a message to the server to be echoed using send() system call. 
 
- Receive the result of the request made to the server using recv() system call. 
 
- Write the result thus obtained on the standard output. 
