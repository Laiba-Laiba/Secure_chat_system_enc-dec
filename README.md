Secure Chat System

The Secure Chat System is a client-server application designed for secure communication over a network. The system ensures that user credentials and messages are transmitted securely using encryption and decryption techniques. Key features include secure registration, login, and encrypted message exchange.

Overview

Before starting the chat, the client and server establish a shared encryption key using the Diffie-Hellman key exchange algorithm. Once the key is securely generated, the server prompts the client for registration or login. During both registration and login, the system validates and securely stores user credentials with encryption to prevent unauthorized access. The communication continues until the client ends the session.

Features

Secure Key Exchange: 
Client and server establish a shared encryption key using the Diffie-Hellman algorithm.
Registration and Login: 
Secure registration and login system that verifies username uniqueness, email format, and password strength.
Encrypted Communication: 
All data transferred between client and server is encrypted using AES-128 CBC mode.
Password Hashing and Salting: 
Passwords are hashed with a unique salt before storage for added security.

Workflow

1. Initial Setup: Key Exchange
   
The server and client first share a key using the Diffie-Hellman algorithm. This key will be used to encrypt and decrypt all subsequent communication.

2. Registration Process

Server Menu: After establishing a shared key, the server prompts the client to register, login, or exit.

Username Verification:
If the client selects registration, the server requests a username.
The server checks for the uniqueness of the username in its database. If the username already exists, it asks the client to enter a unique username.

Email Validation:
Once a unique username is provided, the server asks for an email address.
If the email format is invalid, the server requests re-entry until a valid format is received.

Password Verification:
The server then requests a password. If the password is weak, the server prompts the client to enter a stronger password.
Password Storage:
The server generates a salt and combines it with the password.
The hashed version of the salted password is stored in the server's database along with the client’s username and email.

Registration Completion:

Upon successful registration, the server sends a "Registration Completed" message to the client.

3. Login Process
   
Server Menu: After registration, the client can choose to log in.

Username Verification:

The server requests the client’s username and checks it against the database.

Password Verification:

If the username is valid, the server asks for the password.
The server generates a salt for the username, combines it with the password, and calculates the hash.
The server then compares this hash with the stored hash in the database. If both match, login is successful.

Login Completion:

On successful login, the server sends a "Login Successful" message to the client, and secure communication begins.

4. Secure Messaging
   
Message Exchange:

After login, the client can send encrypted messages to the server.
The server decrypts each message, processes it, and replies.

Session Termination:

The communication ends when the client sends "bye."

Security Details

Key Exchange: Diffie-Hellman is used for securely sharing the initial encryption key.

Data Encryption: All credentials and messages are encrypted using AES-128 in CBC mode, providing secure and reliable communication.

Hashing and Salting: Each password is salted uniquely before hashing, ensuring that even if two users have the same password, their stored hashes differ.

Requirements

OpenSSL library for Diffie-Hellman key exchange and AES encryption/decryption.
C++ compiler (e.g., GCC) for compiling the server and client programs.
Usage Instructions
Compile the Server and Client: Compile both programs on separate machines or terminals.
Run the Server: Start the server to begin listening for client connections.
Run the Client: Connect to the server from the client program.
Proceed with Registration or Login: Follow the prompts for registration or login, ensuring unique usernames and strong passwords.
Start Chatting: Upon successful login, start secure message exchange with the server.

Conclusion

This Secure Chat System provides a robust, encrypted communication channel between a client and a server. Using Diffie-Hellman for key exchange and AES-128 CBC for data encryption ensures that sensitive information like passwords and messages remains confidential.
