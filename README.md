This Python script implements a simple UDP-based file transfer protocol (UFTP) for client-server communication. The protocol supports two main operations: **put** (uploading a file from the client to the server) and **get** (downloading a file from the server to the client). The script provides a basic implementation of the Trivial File Transfer Protocol (TFTP).

### Usage:
1. Run the server script on the host machine.
2. Run the client script on another machine to perform file transfer operations.

### Operations:
#### 1. PUT (Upload)
- Syntax: `put [filename origin] [filename destination] [timeOut]ms [blockSize]B`
- Example: `put sample.txt server_sample.txt 1000 512`
- The client sends a Write Request (WRQ) to the server, indicating the intention to upload a file.
- The server responds with an acknowledgment (ACK) or error message.
- If accepted, the client sends the file data in blocks to the server, and the server acknowledges each block.

#### 2. GET (Download)
- Syntax: `get [filename origin] [filename destination] [timeOut]ms [blockSize]B`
- Example: `get server_sample.txt client_sample.txt 1000 512`
- The client sends a Read Request (RRQ) to the server, indicating the intention to download a file.
- The server responds with an acknowledgment (ACK) or error message.
- If accepted, the server sends the file data in blocks to the client, and the client acknowledges each block.

### Configuration:
- Server and client configurations include parameters such as `timeOut` (timeout duration) and `blockSize` (block size for data transfer).

### Error Handling:
- The scripts handle common errors, such as file not found, and provide appropriate error messages.
