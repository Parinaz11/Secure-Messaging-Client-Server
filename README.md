# Secure Messaging Client-Server

A Python-based messaging application exploring client-server communication, peer-to-peer messaging, access control, and cryptographic techniques. The project features graphical interfaces, user authentication, private and group chats, and cryptographic operations for message protection.

## Overview

This project demonstrates how networking and cryptographic concepts can be integrated into a desktop messaging application. Clients communicate with a central server for authentication and chat coordination, while private messaging can take place directly between peers.

The application combines TCP socket communication, cryptographic primitives, group membership management, and interactive voting features.

## Features

- **User authentication** — Registration and login with password hashing and per-user salts.
- **Graphical interfaces** — Separate GUI implementations for the client and server.
- **Client-server communication** — TCP sockets for communication with the central server.
- **Private messaging** — Peer-to-peer chat sessions between users.
- **Group chats** — Group creation, membership handling, and group messaging.
- **Access control** — Role and access-level management for group operations.
- **Message encryption** — AES-EAX encryption and authentication tags.
- **Message integrity** — HMAC-SHA-256 operations.
- **Digital signatures** — RSA-based signatures using SHA-256.
- **Interactive voting** — Poll creation, voting, and vote counting.

## System Architecture

<p align="center">
  <strong>Application Architecture</strong><br>
  <sub>Client interfaces · Central server · Peer communication</sub>
</p>

<table align="center">
  <tr>
    <td align="center" colspan="3">
      <img src="https://img.shields.io/badge/CLIENT-Desktop%20Application-3973AC?style=for-the-badge" alt="Client desktop application">
      <br><br>
      <strong>Client GUI / Command-Line Client</strong><br>
      <sub>Login · Registration · Chat · Group Operations</sub>
    </td>
  </tr>
  <tr>
    <td align="center" colspan="3">
      <strong>⬇ TCP Socket Connection ⬇</strong>
    </td>
  </tr>
  <tr>
    <td align="center" colspan="3">
      <img src="https://img.shields.io/badge/SERVER-Request%20Handling-238636?style=for-the-badge" alt="Central server">
      <br><br>
      <strong>Central Server</strong><br>
      <sub>Authentication · User Management · Chat Coordination · Access Control</sub>
    </td>
  </tr>
  <tr>
    <td align="center" colspan="3">
      <strong>⬇ Peer Coordination ⬇</strong>
    </td>
  </tr>
  <tr>
    <td align="center">
      <img src="https://img.shields.io/badge/PEER-A-8250DF?style=flat-square" alt="Peer A"><br>
      <sub>Messaging Client</sub>
    </td>
    <td align="center">
      <strong>↔</strong><br>
      <sub>Private Chat</sub>
    </td>
    <td align="center">
      <img src="https://img.shields.io/badge/PEER-B-8250DF?style=flat-square" alt="Peer B"><br>
      <sub>Messaging Client</sub>
    </td>
  </tr>
</table>

<p align="center">
  <sub>Conceptual overview of the application's communication structure.</sub>
</p>

### Message Processing Flow

<p align="center">
  <img src="https://img.shields.io/badge/1-User%20Action-3973AC?style=flat-square" alt="Step 1">
  <br>↓<br>
  <img src="https://img.shields.io/badge/2-Client%20Request-3973AC?style=flat-square" alt="Step 2">
  <br>↓<br>
  <img src="https://img.shields.io/badge/3-Server%20Processing-238636?style=flat-square" alt="Step 3">
  <br>↓<br>
  <img src="https://img.shields.io/badge/4-Response%20or%20Coordination-238636?style=flat-square" alt="Step 4">
  <br>↓<br>
  <img src="https://img.shields.io/badge/5-Client%20Updates%20UI-8250DF?style=flat-square" alt="Step 5">
</p>

<table align="center">
  <tr>
    <td align="center" width="50%">
      <strong>Server-Mediated Operations</strong><br><br>
      Authentication<br>
      User management<br>
      Group coordination<br>
      Access-level changes
    </td>
    <td align="center" width="50%">
      <strong>Messaging Operations</strong><br><br>
      Private peer communication<br>
      Group messaging<br>
      Cryptographic processing<br>
      Voting interactions
    </td>
  </tr>
</table>

The central server handles account-related operations and coordinates supported chat features. Private messaging uses peer-to-peer connections in the implemented communication flow.

## Cryptographic Components

<table>
  <tr>
    <th>Component</th>
    <th>Purpose</th>
  </tr>
  <tr>
    <td><code>AES-EAX</code></td>
    <td>Message encryption with an authentication tag</td>
  </tr>
  <tr>
    <td><code>HMAC-SHA-256</code></td>
    <td>Message integrity checking</td>
  </tr>
  <tr>
    <td><code>RSA</code></td>
    <td>Public/private key operations and digital signatures</td>
  </tr>
  <tr>
    <td><code>SHA-256</code></td>
    <td>Hashing used in password handling and signature generation</td>
  </tr>
  <tr>
    <td><code>Random salts</code></td>
    <td>Added to passwords before hashing</td>
  </tr>
</table>

These components demonstrate common cryptographic concepts in an application context. Their presence alone does not establish that the complete communication protocol is secure.

## Technology Stack

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/TCP%20Sockets-34495E?style=flat-square" alt="TCP sockets">
  <img src="https://img.shields.io/badge/Tkinter-FFCA28?style=flat-square" alt="Tkinter">
  <img src="https://img.shields.io/badge/PyCryptodome-6A5ACD?style=flat-square" alt="PyCryptodome">
</p>

- **Python** — Application logic
- **TCP sockets** — Network communication
- **Tkinter** — Graphical user interfaces
- **PyCryptodome** — AES, RSA, HMAC, SHA-256, and cryptographic utilities
- **Threading** — Concurrent communication tasks
- **Base64** — Encoding binary cryptographic data for transmission

## Project Structure

```text
Secure-Messaging-Client-Server/
├── Client.py
├── ClientGUI.py
├── Server.py
├── ServerGUI.py
├── adminClient.py
├── ca.crt
└── ca.key
```

| File | Description |
|---|---|
| `Client.py` | Command-line client functionality |
| `ClientGUI.py` | Graphical client, authentication, and chat interfaces |
| `Server.py` | Central server, user management, and request handling |
| `ServerGUI.py` | Graphical server implementation |
| `adminClient.py` | Administrative client functionality |
| `ca.crt` | Certificate-related file |
| `ca.key` | Private-key file; inspect carefully before publishing |

## Setup and Usage

### 1. Requirements

- Python 3
- A desktop environment supporting Tkinter
- PyCryptodome

### 2. Install the dependency

```bash
python -m pip install pycryptodome
```

On some Linux distributions, Tkinter must be installed separately.

### 3. Start the server

Run the server in the project directory:

```bash
python Server.py
```

For the graphical server interface, use:

```bash
python ServerGUI.py
```

Run the appropriate entry point for your intended setup rather than starting both simultaneously.

### 4. Start a client

In another terminal:

```bash
python ClientGUI.py
```

Alternatively, run the command-line client:

```bash
python Client.py
```

Start the server before launching clients. The default configuration uses localhost; update the network configuration if clients and the server are running on different machines.

Register or log in, then explore the available messaging features.

## Security Considerations

This project is intended for educational exploration of networking and cryptography, not as a production-ready secure messaging service.

## Project Context

Developed as an information security project exploring network programming, authentication, access control, and cryptographic techniques in a client-server messaging application.
