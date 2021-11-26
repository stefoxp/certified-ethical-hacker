# Appendix A: Ethical Hacking Essential Concepts - I

## Operating System Concepts

### Windows OS

#### MS-Dos-based and 9x Windows OS Versions

- MS-DOS 1.0 - 2.0 - 2.1X - 3.0 - 3.1X
- Windows 95 - 98 - 98 SE - ME

#### NT Kernel-Based Windows OS Version

For PC:

- Windows NT 3.1 - 3.51 - 3.5 - 4.0
- Windows 2000 - XP - Vista - 7 - 8 - 8.1 - 10

For Server:

- Windows server 2003 - 2003 R2
- Windows Server 2008 - Windows Home Server - 2008 R2
- Windows Server 2012 - 2012 R2
- Windows Server 2016
- Windows Server 2019

### Windows Architecture

The processors of the Windows system work in two different modes for operation:

- User Mode
A collection of Sub-Systems.
Has limited access to resources.
- Kernel Mode
HAL, Kernel, executive.
Unrestricted access to system memory and external devices.

![Windows Architecture](img/windows_architecture.png "Windows Architecture")

### Windows Commands

![Windows Commands](img/windows_commands.png "Windows Commands")

### UNIX OS

Three main components:

- kernel
- shell
- programs

All files are grouped together in the directory structure.

The file system is arranged in a hierarchical structure.

The top of the hierarchy is traditionally called **root** ("/")

![UNIX directory structure](img/unix_directory_structure.png "UNIX directory structure")

![UNIX commands](img/unix_commands.png "UNIX commands")

### Linux OS

Components:

- hardware
- kernel
- shell
- applications or Utilities
- system libraries
- daemons
- graphical server

![Linux Architecture](img/linux_architecture.png "Linux Architecture")

Features:

- portability
- open source
- multi-user
- multi-programming
- hierarchical file system
- shell
- security

### MAC OS X

... is a series of closed-source graphical os developed by Apple Inc.

... is the primary operating system for Apple's Mac computers.

Layers:

- cocoa application layer
- media layer
- core services layer
- core OS layer
- Kernel and Device Drivers layer

![MAC OS X Architecture](img/macosx_architecture.png "MAC OS X Architecture")

## File Systems

The ... is a set of data types that is employed for storage, hierarchical categorization, management, navigation, access, and recovering data.

... provide a mechanism for users to store data in a hierarchy of files and directories.

... includes a format for specifying the path to a file.

... is organized in the form of tree-structured directories.

Major ... include:

- FAT
- NTFS
- HFS+
- APFS
- Ext2
- Ext3
- Ext4
- others

Types of File Systems:

- shared disk
- disk
- network
- database
- flash
- tape
- special purpose

### File Allocation Table (FAT)

... is used with DOS

... was the first FS used with Windows OS

... is placed at the beginning of the volume.

... contains three different versions:

|System|Bytes per cluster|Cluster limit|
|---|---|---|
|FAT12|1,5|Fewer than 4.087|
|FAT16|2|4.087 - 65.526|
|FAT32|4|65.526 - 268.435.456|

FAT32 is derived from a FAT file system and supports drives up to 2 terabytes in size.
It uses drive space efficiently and uses small clusters.
It crete backups of the FAT instead of using the default copy.

### New Technology File System (NTFS)

... is the standard FS of windows >= NT

... includes several improvements.

![NTFS Architecture](img/ntfs_architecture.png "NTFS Architecture")

![NTFS System files](img/ntfs_system_files.png "NTFS System files")

### Encrypting File Systems (EPS)

... was first introduced in version 3.0 of NTFS.

This encryption technology maintains a level of transparency to the user who encrypted the file: is no need for users to decrypt the file and access it for making changes.

To enable the encryption and decryption facilities, a user has to set the encryption attributes of the files and folders.

### Sparse Files

... provide a method of saving disk space for files.
If an NTFS file is marked as sparse, it assigns a hard disk cluster only for the data defined by the application.

![Sparse files](img/sparse_files.png "Sparse files")

### Linux File Systems

![Linux file system Architecture](img/linux_file_system_architecture.png "Linux file system Architecture")

#### Filesystem Hiearchy Standard (FHS)

... defines the directory structure and its contents.
All files and directories are present under the root directory.

![FHS directories](img/fhs_directories.png "FHS directories")

#### Extended File System (EXT)

... was the first file system for the Linux OS.

... has a maximum partition size of 2 GB and a maximum file name size of 255 characters.

The major limitation of this file system is that it doesn't support separate access, inode modification, or data modification time stamps.

#### Second Extended File System (EXT2)

... uses improved algorithms and maintains additional time stamps.

... maintains a special field in the superblock that keeps track of the file system status.

... its shortcomings are the risk of FS corruption when writing to EXT2, and that it is not a journaling file system.

#### Third Extended File System (EXT3)

... is an enhanced version of the EXT2 file system.

... is uses file system maintenance utilities for maintenance and repair, like the EXT2 FS.

Features:

- data integrity
- speed
- easy transition

#### Fourth Extended File System (EXT4)

... is a journaling FS

... has significant advantages over EXT3 and EXT2 FS, in terms of performance, scalability, and reliability

### Mac OS X File Systems

1. Hierarchical File System (HFS)
2. HFS plus
3. Unix File System (UFS)

## Computer Network Fundamentals

Standard Network Models:

- OSI Model
- TCP / IP model

### Open System Interconnection (OSI) Model

... is the standard reference model for communication between two end users in a network.

... comprises seven layers, of which the top four layers are used when a message transfers to or from a user and the lower three layers are used when a message passes through the host computer.

![OSI model](img/osi_model.png "OSI model")

### TCP / IP Model

... is a framework for the Internet Protocol suite of computer network protocols that defines the **communication in an IP-based network**.

#### Functions

Handles high-level protocols, representation issues, encoding, and dialog control.

Constitutes a logical connection between the endpoints and provides transport services from the source to the destination host.

Selects the best path through the network for packets to travel.

Defines how to transmit an IP datagram to other devices on a directly attached network.

#### Layers

- Application layer
- Transport layer
- Internet layer
- Network Access layer

#### Protocols

- File transfer (TFTP, FTP), Email (SMTP), Remote login (Telnet, rlogin), Network management (SNMP), Name management (DNS)
- Transmission control protocol (TCP), and User datagram protocol (UDP)
- Internet protocol (IP), Internet control message protocol (ICMP), Address resolution protocol (ARP)
- FDDI, Token Ring, CDP, VTP, PPP

### Comparing OSI and TCP / IP

TCP / IP model is based on the practical implementation of protocols.

OSI model is a generic protocol-independent standard. It defines services, intervals, and protocols.

![OSI vs TCP / IP](img/osi_vs_tcp.png "OSI vs TCP / IP")

### Types of Networks

Classification of networks based on the physical location or the geographical boundaries:

- Local area network (LAN)
- Wide area network (WAN)
- Metropolitan area network (MAN)
- Personal area network (PAN). Wireless communication that uses both radio and optical signals. Covers individual's work area or work group (room-size network)
- Campus area network (CAN). Covers only a limited geographical area
- Global area network (GAN). A combination of different interconnected computer networks. The Internet is an example of...

### Wireless networks (WLAN)

... use Radio Frequency (RF) signals and the ISEE standard of 802.11, and radio waves for communication.

Advantages:

- installation is easy and eliminates wiring
- access can be from anywhere within the range of an access point
- public places can offer constant Internet connection

Limitations:

- wi-fi security may not meet expectations
- the bandwidth is impacted by the number of users
- wi-fi standard changes may require replacing wireless components
- some electronic equipment can interfere with the wi-fi network

#### Wireless standards

![Wireless standards](img/wireless_standards.png "Wireless standards")

![Wireless standards 2](img/wireless_standards_2.png "Wireless standards 2")

#### Wireless Technologies

**Worldwide Interoperability for Microwave Access (WIMAX)** is a wireless communication standard based on the IEEE 802.16 family.
It is a standardized wireless version of Ethernet that provides broadband access to wireless mobile.
It works as an alternative to wire technologies.
... signals can function over a long distance with higher data rates.
It provides high-speed data, voice, video calls, and Internet connectivity to users.

**Microwave Transmission** is a form of wireless communication that uses high frequency radio waves.
It is widely used in point-point communications.
... offers a very large information-carrying capacity owing to its huge bandwidth.
A major limitation is its ability to transmit data only within line of sight.

**Optical Wireless communication (OWC)**

... is a form of unguided transmission through optical carriers.

... uses visible, infrared (IR) and ultraviolet (UV) ranges of light:

- Visible light communication (VLC)* operates in the visible band (390-750 nm). ... use light-emitting diodes.
- Point-to-point OWC systems (known as free space optical systems) transmit at IR frequencies (750-1600 nm). ... use laser transmitters.
- ultraviolet communication (UV) operates within the solare blind UV spectrum (200-280 nm).

**2G**

... is the second generation of mobile cellular network under the standard **Global system for Mobile communications (GSM)**. ... uses digitally encrypted signals.
A combination of 2G and **GPRS** forms its advanced version, 2.5G.
Later **Enhanced Data Rates for GSM Evolution (EDGE)**, alias 2.75G, succeeded the GPRS.

**3G**

... is the third-generation wireless technology that was launched as a **Universal Mobile Telecommunications Service (UMTS)** network.
The first version is **High-Speed Packet Access (HSPA)**, the last version is **High Speed Packet Access (HSPA+)**, alias 3.5G.

**4G**

... known as **Long Term Evolution (LTE)**, is a fourth-generation.
All capabilities defined by the International Telecommunication Union (ITU) and International Mobile Telecommunications-Advanced.
... offers transmission rates of 100Mbit/s for high-mobility communication and 1Gbit/s for low-mobility communication.

**Terrestrial trunked radio (Tetra)**

... is a European standard that describes a professional mobile radio communication infrastructure.
... is a standard for Private Mobile radio (PMR) and Public access mobile radio (PAMR) that is aimed at emergency users and transport services.
The low frequency permits coverage of a large geographic area with fewer transmitters.

**Bluetooth**

... is a short-range (up to 10 meters) device-to-device data transmission technology.
... transfers data at less than 1 Mbps and operates within a frequency range of 2.4 Ghz to 2,485 Ghz.
... comes under IEEE 802.15.

### Network topologies

... is a specification that deals with a network's overall design and flow of its data.

Types of...

#### Physical

The physical layout of nodes, workstations and cables.

![network physical topologies](img/network_topologies_physical.png "network physical topologies")

#### Logical

The information flow between different components.

### Network Hardware Components

- Network Interface Card (NIC)
- Repeater
- Hub
- Switch
- Router
- Bridges
- Gateways

### Types of LAN technology

#### Ethernet

... is the physical layer.
... describes the number of conductors required for making the connection, determines the required performance thresholds, and offers the framework for data transmission.
... can send data at a rate of up to 10 Mbps
... standard is IEEE standard 802.3

#### Fast Ethernet

... standard is IEEE 802.3u transmits data at a minimum rate of 100 Mbit/s.

3 types:

1. 100BASE-TX (level 5 UTP cable)
2. 100BASE-FX (fiber-optic cable)
3. 100BASE-T4 (extra two wires with a level 3 UTP cable)

#### Gigabit Ethernet

... standard IEEE 802.3-2008 ... Ethernet frames at a speed rate of 1 gigabit per second.

It is used for multimedia and Voice over IP (VOIP).

... also called *Gigabit-Ethernet-over-copper* or 1000Base-T, its speed is ten times more than 100Base-T.

#### 10 Gigabit Ethernet

IEEE 802.3ae-2002

10 gigabit per second

... uses optical fiber connections.

#### Asynchronous Transfer Mode (ATM)

... is a cell-based fast-packet communication standard

... operates on the *data link layer*

... used on private long-distance networks

#### Power over Ethernet (PoE)

IEEE 802.3af and 802.3at

... allows the Ethernet cables to supply power to network devices over existing data connection.

![LAN Technology specifications](img/lan_specification.png "LAN Technology specifications")

### Common Fiber Technologies

#### Fiber Optic Cable

![Fiber Optic Cable](img/cable_fiber_optical.png "Fiber Optic Cable")

Components:

- core consists of glass or plastic with higher index of refraction
- cladding ... but with lower refractive index
- buffer protects the fiber from damage
- jacket holds one or more fibers in a cable

Features:

- lower cost
- wide bandwidth
- lighter - weight and small
- more secure
- resistant to corrosion
- longer life and easy to maintain
- elimination of cross-talk
- immune to electrostatic interference

#### Coaxial Cable

![Coaxial Cable](img/cable_coaxial.png "Coaxial Cable")

Advantages:

- cheap installation cost
- great channel capacity
- good bandwidth
- easily modifiable
- cheap production cost

#### CAT 3

Used in 10Base-T Ethernet

Bandwidth of 16 MHz

Attenuation of 11.5 dB

Impedance of 100 ohms

#### CAT 4

Used in 10Base-T Ethernet

Bandwidth of 20 MHz

Attenuation of 7.5 dB

Impedance of 100 ohms

#### CAT 5

... has a maximum length of 100 m

... supports frequencies up to 100 MHz

Used in suitable for 10Base-T, 100Base-TX, and 1000Base-T

Bandwidth of 100 MHz

Attenuation of 24.0 dB

Impedance of 100 ohms

#### CAT 5 e

Used in fast ethernet (100 Mbps), Gigabit Ethernet (1000 Mbps), and 155 Mbps ATM

Bandwidth of 350 MHz

Attenuation of 24.0 dB

Impedance of 100 ohms

#### CAT 6

Used in Gigabit Ethernet (1000 Mbps), and 10 Gigabit Ethernet (10000 Mbps)

Bandwidth of 250 MHz

Attenuation of 19.8 dB

Impedance of 100 ohms

#### 10 Base-T

... has a maximum transmission speed of 10 Mbps and a maximum cable length of 100 m

... uses 802.3i IEEE standard

... uses 4 wires (pins 1, 2, 3, 6)

#### 100 Base-T

... has a maximum transmission speed of 100 Mbps

... uses 802.3u IEEE standard

... uses 4 wires (pins 1, 2, 3, 6)


#### 1000 Base-T

... has a maximum transmission speed of 1000 Mbps

... uses 802.3ab IEEE standard

... uses 8 wires (pins 1, 2, 3, 4, 5, 6, 7, 8)

### TCP / IP Protocol Suite

#### Application Layer: Dynamic Host Configuration Protocol (DHCP)

#### Application Layer: Domain Name Server (DNS)

![DNS packet format](img/dns_packet_format.png "DNS packet format")

![DNS Hierarchy](img/dns_hierarchy.png "DNS Hierarchy")

#### Application Layer: Domain Name System Security Extensions (DNSSEC)

... is a suite of the Internet Engineering Task Force (IETF)
... is used for securing certain types of information provided by DNS
... works by digitally signing records for DNS lookup.

It guarantees:

- authenticity
- integrity
- the non-existence of a domain name or type

It does not guarantee:

- confidentiality
- protection against Denial of Service

> *Delegation Signing (DS) records* provide complete information about a signed zone file.

#### Application Layer: Hypertext Transfer Protocol (HTTP)

Weaknesses in HTTP:

- vulnerable to man-in-the-middle attacks
- a data sent via HTTP are not encrypted
- can be used without any encryption or digital certificates

#### Application Layer: Secure HTTP (S-HTTP)

... is an alternate for the HTTPS (SSL) protocol.
... is generally used in situations where the server requires authentication from the user.

Not all browsers and servers support S-HTTP

#### Application Layer: HyperText Transfer Protocol Secure (HTTPS)

The connection is encrypted using the Transport Layer Security (TLS) or Secure Sockets Layer (SSL) protocol.

... protects against man-in-the-middle attacks.

... can be vulnerable to Decrypting RSA with Obsolete and Weakened eNcryption (DROWN) attacks. 

#### Application Layer: File Transfer Protocol (FTP)

TCP Port 21

... uses SSL / TLS and SSH encryptions for data security.

... uses two connections:

- control connection
- data connection

... supports two modes of operation:

- active mode (control connection is made from the client, data connection from the server)
- passive mode (both the connections are made from the client)

#### Application Layer: Secure File Transfer Protocol (SFTP)

TCP Port 22

#### Application Layer: Trivial File Transfer Protocol (TFTP)

... only reads and writes files from or to a remote server.

Weaknesses:

- vulnerable to Denial of service
- " to directory traversal

#### Application Layer: Simple Mail Transfer Protocol (SMTP)

TCP port 25

two types of model:

- end to end
- store and forward

Features:

- mail forwarding
- mail gatewaying
- mail relaying
- address debugging
- mailing list expansion

Advantages:

- ... provides the simplest form of communication through mail
- quick mail delivery
- ... is reliable for outgoing email messages
- easy to connect. Flexible with existing applications
- several platforms support
- low implementation and administration cost

Disadvantages:

- weakest security
- limited to 7 bit ASCII chars
- lack the security protocols specified in X.400
- usefulness is limited owing to its simplicity

#### Application Layer: Secure Multipurpose Internet Mail Extensions (S/MIME)

... is used to send digitally signed and encrypted email messages

... uses **RSA** for its digital signature and **DES** for message encryption

![Secure Multipurpose Internet Mail Extensions](img/s_mime.png "Secure Multipurpose Internet Mail Extensions")

#### Application Layer: Pretty Good Privacy (PGP)

... provides *cryptographic privacy* and authentication for network communication

![Pretty Good Privacy ](img/pgp.png "Pretty Good Privacy ")

|Mandatory Features                     |S/MIME v3                                  |OpenPGP                                    |
|---                                    |---                                        |---                                        |
|Message Format                         |Binary, Based on CMS                       |Application/Pkcs 7-mime                    |
|Certificate Format                     |Binary, Based on X.509v3                   |Binary, Based on previous PGP              |
|Symmetric Encryption Algorithm         |Triple DES (DES, EDE3, and CBC)            |Triple DES (DES, EDE3, and Eccentric CFB)  |
|Signature Algorithm                    |Diffie-Hellman (X9.42) with DSS or RSA     |ElGamal with DSS                           |
|Hash Algorithm                         |SHA-1                                      |SHA-1                                      |
|MIME Encapsulation of Signed Data      |Choice of Multipart/signed or CMS Format   |Multipart/signed ASCII armor               |
|MIME Encapsulation of Encrypted Data   |Application/Pkcs 7-mime                    |Multipart/Encrypted                        |
              
#### Application Layer: Telecommunications network (Telnet)

... is a TCP/IP protocol used on a LAN that helps a user to access remote computers over a network

Advantages:

- logging on to a remote computer and executing programs
- controlling web servers remotely
- fast and efficient even when the network and system loads are high

Weaknesses:

- vulnerable to DoS
- vulnerable to Packet sniffing
- is not secure: all data in clear text
- vulnerable to eavesdropping attacks

#### Application Layer: Secure Shell (SSH)

... builds a secure, encrypted tunnel for exchanging information between the network

Authentication mechanism:

1. simple -> user password
2. key-based -> generate a public and a private key (ssh-keygen -t rsa)
3. host-based

#### Application Layer: Simple Object Access Protocol (SOAP)

... is an XML-based messaging protocol.
... provides data transport for web services and is independent of both platform and language

... has *extensibility*, *neutrality*, *independence*

... is equivalent to RPC, used in DCOM and COBRA

Weaknesses:

- statelessness
- to much reliance on HTTP
- slower than CORBA, RMI, or IIOP due to the lengthy XML format
.. depends on WSDL and does not have any standardized mechanism for dynamic discovery of the services

#### Application Layer: Simple NEtwork Management Protocol (SNMP)

... manages a TCP/IP based network

... can collect and manage the information about the devices (routers, hub modems, printers, bridges, switches, servers and workstations)

Risks to Cisco IOS SNMP configurations:

- DDoS attacks
- SNMP Remote Code Execution

#### Application Layer: Network Time Protocol (NTP)

pag.3266

#### Application Layer: Remote Procedure Call (RPC)

#### Application Layer:
#### Application Layer: