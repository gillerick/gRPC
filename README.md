### What is gPCR

It is a robust _open-source_ RPC (Remote Procedure Call) framework used to build scalable and fast APIs.

gRPC owes its success to the employment of two techniques: using HTTP/2 instead of HTTP/1.1 and protocol buffers as an
alternative to XML and JSON. Most of the advantages of gRPC stem from using these technologies.

### Advantages
#### 1. Performance

It offers up to 10x faster performance and API-security than REST+JSON communication as it uses **Protocol Buffers**
and **HTTP/2**

#### 2. Lightweight

Depending on the type of call, gRPC-specific messages can be up ro 30 percent smaller than JSON messages.

#### 3. More connection options/ streaming

While REST focuses on request-response architecture, gRPC provides support for data streaming with event-driven
architectures: server-side streaming, client-side streaming, and bidirectional streaming.

### Disadvantages
#### 1. Limited browser support

Since gRPC heavily relies on HTTP/2, one can't call a gRPC service from a web browser directly given no modern browsers
can access HTTP/2 frames. A proxy must therefore be used.

#### 2. Steeper learning curve
Compared to REST and GraphQL, which primarily use JSON, it takes a developer more time to get acquainted with protocol
buffers and find tools for dealing with HTTP/2 friction.

#### 3. Non human-readable format
By compressing data to a binary format, `protobuf` files become non-human readable, unlike XML and JSON. To then analyze
payloads, debug and write manual requests, developers have to use extra tools.

#### 4. Lack of maturity
With minimal developer support outside Google, as things stand, not many tools created for HTTP/2 and protocol buffers,
the community lacks information about best practices, workarounds and success stories.

### Protocol Buffers
![](resources/images/protocol-buffers.png)

1. In a `.proto` text file, a programmer defines a schema - how they want the data to be structured. They used numbers
   instead of field names to save storage.
2. Using a _protoc compiler_, this file is then automatically compiled into any of the numerous supported languages like
   C++, Python, Go and more.
3. At runtime, messages are compressed and serialized in binary format.

Parsing with Protocol Buffers is less CPU intensive because data is represented in a binary format which minimizes the
size of encoded messages. This means the message exchange happens faster, even in devices with a slower CPU like IoT or
mobile devices.

**The essence of schema:** By forcing programmer to use a schema, we can ensure that the message doesn't get lost
between applications and its structural components stay intact on another service as well.

### HTTP/2 as the transport protocol
Unlike text-based HTTP/1.1, HTTP/2 communication is divided into smaller messages and framed in binary format making
sending and receiving messages compact and efficient.

![](resources/images/binary-framing.png)



