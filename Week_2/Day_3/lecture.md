Blocking code, synchronous. Non-blocking, Asynchronous.



# Networking, Protocol

## Hafiz's Hot Tips:

So you went to a networking event?
* Introduce yourself
* Figure out if you speak the same language
* Handshake
* Make sure there is mutual desire to participate in the conversation
* Listen when they are speaking - hopefully they do the same
* End the conversation cleanly

These tips are a protocol - a list of rules. 


## Protocol

Many protocols exist
* OSI models
* TCP/IP
* FTP (File transfer protocol)
* XMPP (Extensible Messaging and Presence Protocol)
* SMTP (Email services)
* SSH: (Secure Shell)

We will focus on TCP/IP

TCP/IP is layered. 
IP (Internet (Addressing) Protocol) layer is on the bottom. -managed the IP address (like a phone number)
Layered on top of IP is TCP (Transmission Control Protocol) - manages the port (like an extension number)
HTTP (Hypertext Transfer Protocol) - Address structure built by TCP/IP, this layer makes requests and expects responses. 


## Servers

Application servers are basically apps that live on a machine, or multiple machines. 

Servers are the combination of where TCP/IP are pointing to.


For every IP address (which is pointing to a machine) there are many addressble ports that application servers can be listening on.
Some protocols have default ports.
  HTTP is bound to port 80. 
  HTTPS is bound to port 443
  SMTP - port 25 (maybe)
  SSH - port 22, sometimes 23

A URL is an alias for a particular ip, but the HTTPS implies the port we are trying to access, because of the protocol. 

### Chat Application:

Workflow:

1. Create a server.
2. Listen for connections (open the shop for business) on a particular port.
3. On connection, send a welcome message to every client.
  * set an encoding (make sure we speak the same language)
4. Listen for message from client.
5. On receiving message, broadcast to other connected clients.
6. On client disconnect say something


require('net'), our node built in server stuff

CONSOLE LOG THINGS WE DONT KNOW.

console.log(net);
const server = net.createServer();
console.log (server);

using vsCode, we know server is an object - we can use a dot notation to call some of it's object keys. 
 - but also read the documentation

server.listen(4337, () => console.log('Server listening on port', 4337))


server.on() is a common way of declaring 'when something happens'. It'll ask for two things - what am I listening for (a string, of some kind), and what do I do when it happens (some sort of callback function)?


server.on('connection', (client) => {
  
});



Clients workflow:
1. Create a connection
  * Need the address for the shop they're going to --> a host ip address and port number
2. Determine what the encoding is (what language we talking?) 
3. Wait for connection to succeed --> listen for connection acknowledgement. On connection : 
  * Listen for data or a message from the server
  * Write some message to server

Clients also use the require('net') package:
  net.createConnection({
    host: ip address
    port: 4337 (same as server)
  })

Listen for connection. 

client.on('connect', () => {
  console.log(Yep, i've connected to the server)
});


Client variable is the bridge - so when listening for client messages we listen on the client. 

The console / command line, will be our channel for getting and sending messages. We want to write messages on stdin. 
  When something is being typed to stdin (when there is data on stdin), send that data to server.


On client connections, create array and push the client into it.


## HTTP:

A number of different http clients exist:

* Browsers
* Curl
* Postman
* Code based client (eg. using a library - today we will use request). 

HTTP is made of:


### Requests
Is made from clients:

Requests are based on resources. Do you want to retreive a resource? Post one online? Update something online (Putting the change online?), Delete a resource?

composed of some **Must Haves**:
* URL
* Method (what's the plan, in this address)
  * commonly GET, POST, PUT, DELETE
  * Default is GET, if none is passed with the request
* Headers
* Body
  Header & Body are ways to send additional info with your request

### Responses

Each request gets a response back.

Two things come with EVERY response:

1. Status / codes
  These tell us the state of the request. Is it a good request? Bad request? 
    * 100s - status codes - info on the state of the request
    * 200s - usually good, task done, etc.
    * 300s - redirect instructions - these are good still (the thing you're looking for isn't here anymore, go look over there)
    *  400s - beginning of error codes. Bad requests: you as user has made a bad request.
    * 500s - Oops, server problem.
2. Headers - identifiers about the request




Summary: 

Understanding protocol - machine to machine protocol has a similar setup to our innate understanding of communicating

IP - inernet protocol, TCP - transmission control protocol

These are how we find the right place - the building, and the floor / office we need to go to. 

