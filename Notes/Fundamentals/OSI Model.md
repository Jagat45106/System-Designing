OSI Model (Opem System Interconnections)

It is a reference frameworks that explain the process of transmission fo data between computers/servers/devices.
7 layers architecture where each layers has their own protocols and specific fucntions to perform

Application Layer (OSI Layer 7)
	•	Used in network applications such as Chrome, Edge, FileZilla, Outlook, and Microsoft Teams.
	•	At this layer, data is presented in a visual or user-understandable form.
	•	Provides an interface between the user and the application.
Common uses include:
	•	Remote login
	•	File transfer
	•	Mail services
	•	Resource sharing
	•	The application layer provides multiple protocols that allow software to easily send and receive data.(FTP,HTTP/S, SMTP)

Presentation Layer (OSI Layer 6)

Application Layer
        ↓
Presentation Layer
        │
        ├── Translation
        │       "Hello World!!" (ASCII)
        │                ↓
        │       01001000011 0010... (EBCDIC)
        │
        ├── Compression
        │       0100100001  →  (Lossy / Lossless)
        │
        └── Encryption
                Input: 0100100001
                        ↓
                Output: 0111110101 (Encrypted Data)

Key Points
	•	The Presentation Layer is also known as the Translation Layer.
	•	It extracts the data received from the Application Layer and formats, converts, or encodes it as required for transmission over the network.
	•	Main responsibilities include:
1. Translation
	•	Converts data between different formats (e.g., ASCII ↔ EBCDIC).
	•	Ensures that sender and receiver interpret data consistently.
2. Compression
	•	Reduces data size to improve transmission speed.
	•	Supports lossy and lossless compression techniques.
3. Encryption / Decryption
	•	Encrypts data before sending over the network for security.
	•	Decrypts incoming data so the application layer can understand it.

In simple terms, this layer ensures:
“The data is in the right format, compressed efficiently, and secured before transmission.”

Session Layer (OSI Layer 5)

Device A  ←─────────────── Session ───────────────→  Device B
                  │
                  ├── Half-duplex / Full-duplex
                  │
                  └── Authentication & Authorization

Key Points
	•	The Session Layer is responsible for opening, managing, and closing communication sessions between two devices.
	•	The duration between when communication starts and when it ends is called a session.
	•	It enables two systems to communicate in:
	•	Half-duplex mode (one direction at a time), or
	•	Full-duplex mode (both directions simultaneously).
	•	It also manages Authentication & Authorization to ensure that only permitted devices or users can establish a communication session.
	•	In simple terms, this layer controls the start, maintenance, and end of conversations between devices.

Transport Layer (OSI Layer 4)

Device A (100 Mbps)  
        │
        ├── Data
        │       ↓
        │   ┌────────────────────────┐
        │   │     Segmentation       │
        │   └────────────────────────┘
        │       ↓   ↓   ↓
        │   [Data Unit] [Data Unit] [Data Unit]
        │    SqNo:xx     SqNo:xx     SqNo:xx
        │    PortNo:xx   PortNo:xx   PortNo:xx
        │
        ├── Flow Control
        │       ↓
        │   Data Speed: 50 Mbps
        │
        └── Error Control
                ↓
        [Data Unit + CHECKSUM]
        [Data Unit + CHECKSUM]
        [Data Unit + CHECKSUM]
        
Device B (50 Mbps)

Key Points
	•	The Transport Layer manages the end-to-end communication between hosts.
	•	It ensures that data is delivered accurately, reliably, and in the correct order.
	•	Key functions of the Transport Layer include:
1. Segmentation
	•	Breaks large data chunks into smaller data units (segments).
	•	Each segment contains:
	•	Sequence number (SqNo)
	•	Port number (PortNo)
	•	Helps the receiving device reassemble data correctly.
2. Flow Control
	•	Regulates the data transmission rate between sender and receiver.
	•	Prevents the sender from overwhelming the receiver.
	•	Example shown: Data speed adjusted to 50 Mbps.
3. Error Control
	•	Ensures error-free data delivery using:
	•	Checksums
	•	Acknowledgements (ACK)
	•	Retransmissions when needed
	•	Validates integrity of each segment.
	•	In short, the Transport Layer ensures:
“Reliable, orderly, and controlled delivery of data between two hosts.”

Network Layer (OSI Layer 3):

Transport Layer Output
        ↓
┌────────────────────────────────────┐
│            Data Segment            │
│   Data Unit                        │
│   SqNo: xx                         │
│   PortNo: xx                       │
│   CHECKSUM                         │
└────────────────────────────────────┘
        ↓  (Network Layer adds IP addresses)
┌────────────────────────────────────┐
│             Data Packet            │
│   src IP: 192.168.2.1              │
│   dest IP: 192.168.34.2            │
│                                    │
│   Data Unit                        │
│   SqNo: xx                         │
│   PortNo: xx                       │
│   CHECKSUM                         │
└────────────────────────────────────┘
        ↓
Sent across different networks


Key Points
	•	The Network Layer is responsible for the transmission of data from one device to another located in different networks.
	•	It handles the movement of packets across multiple networks using routing.

⸻

Functions of the Network Layer

1. Logical Addressing
	•	Assigns a logical address (IP address) to both the sender and receiver.
	•	These IP addresses are placed in the packet header.
	•	Ensures the packet can find its way across different networks.

2. Routing
	•	Finds the best path for the data packet to travel from source to destination.
	•	Routers operate at this layer.

⸻

In Summary

The Network Layer is responsible for:
	•	Adding IP addresses (source + destination)
	•	Routing packets between networks
	•	Delivering data logically (not physically like Layer 2)

It ensures that the packet created from the transport segment can travel across multiple interconnected networks to reach the correct destination.


Data Link Layer (L2)