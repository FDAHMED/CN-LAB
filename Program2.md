## Program 2 
---
### IMPLEMENTATION OF ITERATIVE ECHO SERVER USING CONNECTION-ORIENTED (TCP). 
 
Description:  This program implements a server as an iterative server, which receives the messages from the client and sends the same message as an echo to the client. This uses the TCP connection for communication and closes it after the communication is ended. 
---
### Algorithm 
---
#### Server side : 
- First, it need to create the socket using the socket system call. 
- Binds the name (i.e., IP address, port number, and family) of the server to the socket. 
- Makes the socket ready in passive state by creating queues for storing the client requests using the listen system call. This server is listening for the clients. 
- Once the connect request comes from the client, it is stored in the queue, and the accept system call is made for establishing the connection. This returns the new connection ID, which is used while sending and receiving the messages. 
- It receives the message from the client and echoes it back to the client. 
- Now close the system call after completing the communication. 

---
### Client side: 
- First, we need to create the socket. 
- Initializes the server address to the sockaddress_in structure to which the connect request has to be sent. 
- Makes a connection request to the server using the connection system call. If the connection is established at the server, it gets the connection ID, which is used for the communication. Otherwise, it returns a negative number as an error. 
- If the connection is established, it sends and receives the messages using send and recv system calls.
