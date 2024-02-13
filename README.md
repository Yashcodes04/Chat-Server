# Chat-Server
A chat server using TCP protocols and socket program

1. Client-Server Architecture:
The chat system follows a client-server architecture where multiple clients connect to a central server to exchange messages.
Each client establishes a TCP connection with the server.

2. Client Side:
The client code prompts the user to choose a nickname.
It establishes a TCP connection with the server at the specified IP address (127.0.0.1) and port number (55555).
The client spawns two threads: one for receiving messages from the server (receive) and another for sending messages to the server (write).
The write thread allows the user to input messages in the console and sends them to the server.

3. Server Side:
The server code listens for incoming connections from clients on a specified IP address (127.0.0.1) and port number (55555).
When a client connects, the server creates a new thread to handle communication with that client.
Upon connection, the server prompts the client to choose a nickname by sending the message 'NICK'.
Once the client sends its chosen nickname, the server associates it with the client's connection.
The server continuously listens for incoming messages from clients and broadcasts them to all connected clients.
If a client disconnects or encounters an error, the server closes the connection and removes the client from its list of active connections.

