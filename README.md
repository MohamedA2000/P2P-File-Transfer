# P2P-File-Transfer Application
A peer to peer file transferring application written in C using TCP and UCP sockets

# Client
A client can do any of the following:
* Connect to the server
* Register a file to be downloaded
  * A new port on the client's connection is opened
* Browse registered files
* Download a listed file
  * Makes a new connection to the client via UDP to facilitate file download
  * Registers file to server once downloaded
* Deregister a file
  * The listed port is closed on the client
* Disconnect from the server
  * All registered files will be automatically deregistered
  
# Server
The server facilitates client connections, file registrations, file download requests, and file deregistrations.

# Setup
```
$ gcc server.c -o server
$ gcc client.c -o client
```

## Server
```
$ ./server <SERVER_PORT>
```
## Client
```
$ ./client <SERVER_ADDRESS> <SERVER_PORT> <CLIENT_PORT>
```
