##Program 4 
 
###IMPLEMENTATION OF CONCURRENT ECHO SERVER USING CONNECTION- 
ORIENTED(TCP) 
**Description: 
This program implements server as a concurrent server, which receives the messages from the 
client and sends the same message as echo to the client. In this it creates a child process using fork 
system call for each client request. This child process service the client request. In this way it 
services multiple clients at the same time. This uses the connection oriented concept for 
implementing, which means first it establishes the connection, uses the connection for 
communication and closes it after the communication is ended. 

###Algorithm: 
####Server side : 
i. First creats the socket using socket system call. 
ii. Binds the name (i.e. IP address, port number and family) of the server to the socket. 
iii. Makes the socket to be ready in passive state by creating queues for storing the 
client requests using listen system call. In this server is listening for the clients. 
iv. Once the connect request comes from the client, it stores in the queue and calls 
accept system call for establishing the connection. This returnes the new connection 
id, which is used while sending and receiving the messages. 
v. Creates the child process using fork system call. 
vi. Receives and sends the messages from/to the client in the child process. 
vii. Parent process waits for the next client. 
viii. Close the system call after completing the communication. 
 
####Client side : 
v. First creates the socket. 
vi. Initializes the server address to sockaddress_in structure to which connect request 
has to send. 
vii. Makes a connection request to the server using connection system call. If the 
connection is established at the server it gets the connection id, which is used for 
the communication. Otherwise it returns negative number as an error. 
viii. If connection is established,sends and receives the messages using send and recv system calls. 

