# Secure-Communications
Secure Client-Server Connection

# Secure TLS Client-Server Communication (Python)

This project demonstrates secure communication between a Python-based server and client using SSL/TLS encryption. It uses Python’s built-in `ssl` and `socket` modules to establish a secure channel over localhost on port 8443.

## Features

- Encrypted communication using TLS
- Certificate-based server authentication
- Self-signed certificate support (for testing)
- Simple message exchange between client and server

## Technologies

- Python 3.x
- ssl module
- socket module
- OpenSSL (for certificate generation)

## How It Works

- The server listens on localhost:8443 and wraps incoming TCP connections with TLS.
- The client connects securely to the server using the same TLS settings and validates the server certificate.
- The client sends a message, the server responds, and both close the connection securely.

## Setup

1. Generate a Self-Signed Certificate:

   Run the following command in your terminal:

   openssl req -new -x509 -days 365 -nodes -out server.crt -keyout server.key

   This generates:
   - server.crt — public certificate
   - server.key — private key

2. Run the Server

   python secure_server.py

3. Run the Client (in a separate terminal)

   python secure_client.py

## File Structure

secure_server.py   - TLS-enabled server  
secure_client.py   - TLS-enabled client  
server.crt         - Self-signed certificate (generated)  
server.key         - Private key (generated)  
README.txt         - Project documentation (this file)

## Notes

- Only use self-signed certificates for testing or educational purposes.
- In production, use a certificate signed by a trusted Certificate Authority (CA).
- You can change 'localhost' and port 8443 in the code to run across a network.

## License

MIT License

Author: Christopher Kelley
