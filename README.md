# End-to-End Encrypted Chat API

This project is a backend-only implementation of an end-to-end encrypted chat system, built with ASP.NET Core and Postgres. It includes secure messaging features using RSA and AES encryption, along with WebSocket (WSS) in node.js support for real-time updates.


## Encryption Model

- User RSA Keys
  Each user has a unique RSA key pair:
  - The private key is encrypted with the user’s password.
  - The public key is used for securely generating AES conversation keys.

- Per-Conversation AES Keys
  Each user in a conversation receives a AES key for that conversation.  
  These keys are:
  - Randomly generated
  - Encrypted with the recipient’s public RSA key

- End-to-End Encryption
  - Messages are encrypted on the client using the AES key before sending.
  - The server only routes encrypted data and cannot decrypt any content.

## Technology Stack

- Backend: ASP.NET Core Web API
- WebSocket Service: node.js WSS for real-time events
- Database: Postgres


