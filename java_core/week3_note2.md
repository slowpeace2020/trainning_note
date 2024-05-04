# Day7
### OSI Model

The OSI (Open Systems Interconnection) model is a conceptual framework that standardizes the functions of a telecommunication or computing system into seven abstraction layers.

### OSI Model

The OSI (Open Systems Interconnection) model is a conceptual framework that standardizes the functions of a telecommunication or computing system into seven abstraction layers. Here's a brief overview of each layer:

1. **Physical Layer**: This layer deals with the physical transmission of data over the network medium. It defines the hardware aspects of communication, such as cables, connectors, and electrical signals.

2. **Data Link Layer**: The data link layer is responsible for node-to-node communication, ensuring that data packets are delivered error-free and in sequence. It handles issues such as framing, error detection, and flow control.

3. **Network Layer**: The network layer facilitates routing and forwarding of data packets between different networks. It establishes logical paths, known as routes, for data transmission and handles addressing and routing functions.

4. **Transport Layer**: This layer provides end-to-end communication between devices and ensures that data packets are delivered reliably and in order. It handles issues such as segmentation, reassembly, flow control, and error correction.

5. **Session Layer**: The session layer establishes, manages, and terminates communication sessions between applications. It handles session setup, synchronization, and teardown, as well as checkpointing and recovery.

6. **Presentation Layer**: The presentation layer is responsible for data representation, encryption, and compression. It translates data into a format that the application layer can understand and handles encryption and decryption of data for secure transmission.

7. **Application Layer**: The application layer enables user interaction with network services and applications. It provides interfaces for accessing network services, such as email, file transfer, and web browsing, and supports application-specific protocols.

Each layer of the OSI model encapsulates and abstracts specific functions, allowing for modular and standardized communication protocols across heterogeneous network environments.


### TCP/IP Model

The TCP/IP model is a concise version of the OSI model, consisting of four layers: Application, Transport, Internet, and Link.

### HTTP

- **200 OK**: The request was successful, and the server has returned the requested data.

- **201 Created**: The request has been fulfilled, and a new resource has been created as a result.

- **202 Accepted**: The request has been accepted for processing, but the processing has not been completed yet.

- **204 No Content**: The server has successfully fulfilled the request, but there is no content to return.

- **301 Moved Permanently**: The requested resource has been permanently moved to a new URL, and future requests should use the new URL.

- **307 Temporary Redirect**: Similar to 301, but indicates that the redirection is temporary and future requests should still use the original URL.

- **400 Bad Request**: The server cannot process the request due to a client error, such as invalid syntax or missing parameters.

- **401 Unauthorized**: The request requires user authentication. The client must provide valid credentials to access the resource.

- **403 Forbidden**: The server understood the request but refuses to authorize it. The client does not have permission to access the resource.

- **404 Not Found**: The requested resource could not be found on the server.

- **500 Internal Server Error**: A generic error message indicating that something has gone wrong on the server side, and the server could not fulfill the request.

These are just a few of the many HTTP status codes used to communicate the outcome of HTTP requests between clients and servers. Each status code carries specific meaning and helps to diagnose and troubleshoot issues during web communication.
#### Basic
- HTTP Request: Consists of a request header and body sent from the client to the server.
- HTTP Response: Consists of a response header and body sent from the server to the client.
- HTTP Status Code: Indicates the status of the HTTP response, such as 200 OK, 404 Not Found, etc.

#### Advanced
- Safe: HTTP methods that do not modify the state of the server (GET, HEAD, OPTIONS).
- Idempotent: HTTP methods that can be called multiple times without different outcomes (GET, PUT, DELETE).
- Cacheable: Indicates whether the client can cache the response.

### TCP and UDP

- TCP (Transmission Control Protocol): Provides reliable, ordered, and error-checked delivery of a stream of bytes.
- UDP (User Datagram Protocol): Provides a connectionless and unreliable delivery mechanism for packets.

### Session and Cookie

- Session: A mechanism to maintain stateful information about a user's interaction with a web application across multiple requests.
- Cookie: A small piece of data stored on the client's browser, containing information about the user or their session.

### Java Web Application Architecture

- Three-Tier Architecture: Consists of a presentation layer (controller), business logic layer (service), and data access layer (DAO or repository).

### Spring IOC (Inversion of Control)

- Inversion of Control: A design principle in which the control of object creation and lifecycle management is shifted from the application code to a container or framework.

### DI (Dependency Injection)

- Dependency Injection: A technique in which the dependencies of an object are supplied externally (usually through constructor or setter injection) rather than being created internally by the object itself. This promotes loose coupling and easier unit testing.





      
    


