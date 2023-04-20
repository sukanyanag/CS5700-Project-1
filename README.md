
# Project 1: Simple Client

The Python 3 script "client" implements a simple client that connects to a server, solves arithmetic expressions provided by the server, and sends the results back. The server runs on the machine project1.5700.network and listens for requests on a TLS socket bound to port 27995. This client uses the custom protocol specified in the project requirements.

## High-level Approach:

- The client establishes a TLS socket connection to the server using the provided hostname and port number.
- The client sends a HELLO message to the server with the user's Northeastern-username.
- The client enters a loop where it receives and processes EVAL messages from the server, evaluates the arithmetic expressions, and sends STATUS messages with the results or ERR messages in case of errors (e.g., divide-by-zero).
- The loop continues until a BYE message is received, at which point the secret flag is printed and the connection is closed.

## Challenges faced:

- My initial code was written in Java, which was unable to meet the demands. The decision to switch my project to Python was a wise one overall, despite the difficulties that came with porting the codebase to Python.
- Handling different arithmetic operations and ensuring the correct precedence of operations.
- Implementing error handling for edge cases, such as divide-by-zero errors and invalid expressions.
- Ensuring that the TLS socket connection is properly established and maintained throughout the communication with the server.

## Testing
- Unit tests were created for each function to ensure that the arithmetic operations and expression parsing were working as expected.
- Test cases were created to simulate different EVAL messages received from the server, including valid and invalid expressions, as well as edge cases such as divide-by-zero.
- The client was tested against a local server with a similar protocol to ensure correct handling of HELLO, EVAL, STATUS, ERR, and BYE messages.
- The client was tested against the actual server project1.5700.network to verify that it successfully received the secret flag in the BYE message.
    
To run the client, use the following command:

    python3 client -s [hostname] [Northeastern-username]


