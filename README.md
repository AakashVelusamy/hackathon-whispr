# Whispr - Secure Chat Application

Whispr is a real-time, end-to-end encrypted messaging application developed as part of a hackathon challenge. It ensures secure communication between users with modern encryption techniques, OAuth authentication, and self-destructing messages. This project demonstrates a scalable and privacy-focused chat platform.

## Hackathon Problem Statement
**Title**: Secure Chat Application with End-to-End Encryption  
**Objective**: Build a real-time secure messaging application with end-to-end encryption (E2EE) for private communication, including secure API endpoints, encrypted messages, and group messaging capabilities.

## Features
- **Real-time Messaging**: Powered by WebSockets (Socket.io) for instant message delivery.
- **End-to-End Encryption**: Messages encrypted with AES (Advanced Encryption Standard) and ephemeral keys for Perfect Forward Secrecy (PFS).
- **OAuth 2.0 Authentication**: Secure login via Google OAuth using Passport.js.
- **Self-Destructing Messages**: Messages can be set to automatically delete after a specified time.
- **Encrypted Storage**: Messages stored in MongoDB in encrypted form to ensure data security.
- **Cross-Origin Security**: CORS policies implemented to prevent unauthorized access.

### Limitations
- **No File Sharing**: Secure file sharing was not implemented in this version.
- **No Rate Limiting**: Rate limiting was planned but not completed (Milestone 1 failure).

## Technologies Used
| Component              | Technology                  |
|------------------------|-----------------------------|
| Frontend              | Next.js (React framework)   |
| Backend               | Node.js, Express.js         |
| Database              | MongoDB (NoSQL)             |
| Authentication        | OAuth 2.0 (Google) with Passport.js |
| Real-time Communication | Socket.io (WebSockets)    |
| Security & Encryption | AES, Perfect Forward Secrecy, Ephemeral Keys |

## How It Works
1. **Authentication**: Users log in securely via Google OAuth 2.0 using Passport.js.
2. **Real-time Connection**: WebSocket (Socket.io) establishes a persistent connection for instant messaging.
3. **Message Encryption**: Messages are encrypted with AES and ephemeral keys before transmission.
4. **Message Relay**: The server relays encrypted messages to the intended recipient.
5. **Decryption**: The recipient decrypts the message using the shared secret key.
6. **Storage**: Encrypted messages are stored in MongoDB.
7. **Self-Destruction**: Messages can be configured to self-destruct after delivery.

### Encryption Process
- **Before Sending**: Message → Byte Array → AES Encryption → Sent via WebSocket.
- **On Receiving**: Encrypted Message → AES Decryption → Original Message Displayed.

**Example**:
- Original: "Hello"
- Encrypted: "U2FsdGVkX19Q5j1..."
- Decrypted: "Hello"

## Security Highlights
- **End-to-End Encryption**: Only the sender and receiver can read the messages.
- **Perfect Forward Secrecy**: Past messages remain secure even if future keys are compromised.
- **OAuth 2.0**: Secure and seamless user authentication.
- **WebSocket Security**: Prevents man-in-the-middle (MITM) attacks.
- **Encrypted Storage**: Protects data even if the database is breached.

