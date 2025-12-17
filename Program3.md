#Program 3 

**IMPLEMENTATION OF ITERATIVE ECHO SERVER USING CONNECTION-LESS 
SERVICE(UDP) 
 
**Description: This program implements server as a iterative server, which receives the 
messages from the client and sends the same message as echo to the client. This uses the 
connection less concept for implementing, which means no connection establishes before 
the communication, in this each message is attached with the address of the server because 
there is no fixed path, each message uses its own path to reach to destination. This 
communication is not reliable and it delivers fast. 
 
##Algorithm: 
####Server side : 
i. **First creats the socket using socket system call. 
ii. **Binds the name (i.e. IP address, port number and family) of the server to the socket. 
iii. **Server blocks for receiving the message from the client by using recvfrom system 
call. 
iv. **Sends the message by echoing to client using sendto system call. 

####Client side : 
i. **First creates the socket. 
ii. **Initializes the server address to sockaddress_in structure to which connect request 
has to send. 
iii. **Sends the message to server using sendto system call byspecifying server address 
along with the message. 
iv. **Then waits for the echo message from the server with recvfrom system call. 