# NetX Duo - System Requirements

## Core System Requirements

### Hardware Requirements
- **Memory**: 5-45 KB ROM, 1-5 KB RAM minimum
- **Timer Resources**: 2 ThreadX timer objects per IP instance
- **Synchronization**: 1 ThreadX mutex object per IP instance
- **Network Interface**: At least 1 physical network interface (Ethernet recommended)
- **Processor Architecture**: Any processor with ANSI C compiler support

### Software Dependencies
- **Real-Time OS**: ThreadX RTOS (mandatory dependency)
- **Compiler**: ANSI C compliant compiler
- **Network Driver**: Hardware-specific network interface driver

## Protocol Stack Requirements

### Core Network Protocols (Mandatory)
- **IPv4/IPv6**: Dual-stack support with configurable IPv4-only or IPv6-only builds
- **TCP**: Transmission Control Protocol with congestion control (RFC 5681)
- **UDP**: User Datagram Protocol with Fast Path Technology
- **ICMP/ICMPv6**: Internet Control Message Protocol
- **ARP/RARP**: Address Resolution Protocol (IPv4 only)
- **IGMP**: Internet Group Management Protocol for multicast

### Security Requirements
- **IPsec**: Optional IP-level security (NetX Duo Secure IPsec add-on)
- **TLS 1.0/1.1/1.2**: Optional transport layer security
- **DTLS 1.0/1.2**: Optional datagram transport layer security
- **Cryptographic Support**: RSA, AES, DES/3DES, ECC, HMAC, MD5, SHA-1/SHA-2

### Network Services Requirements

#### Essential Services
- **DHCP**: Dynamic Host Configuration Protocol (client/server)
- **DNS**: Domain Name System client
- **HTTP/HTTPS**: Web server and client support
- **SMTP**: Simple Mail Transfer Protocol client
- **FTP/TFTP**: File Transfer Protocol support

#### IoT/Cloud Integration Services
- **MQTT**: Message Queuing Telemetry Transport
- **SNTP**: Simple Network Time Protocol
- **mDNS/DNS-SD**: Multicast DNS and Service Discovery
- **AutoIP**: Automatic IPv4 address assignment
- **Azure IoT Middleware**: Integration with Azure IoT services

#### Advanced Services
- **SNMP v1/v2/v3**: Network management protocol
- **NAT**: Network Address Translation
- **PPP/PPPoE**: Point-to-Point Protocol support
- **PTP**: Precision Time Protocol
- **RTP/RTSP**: Real-time streaming protocols

## Performance Requirements

### Network Performance Targets
- **UDP Performance**: 95 Mbps RX, 94 Mbps TX on 100 Mbps Ethernet (@100MHz MCU)
- **TCP Performance**: 93 Mbps RX, 94 Mbps TX on 100 Mbps Ethernet (@100MHz MCU)
- **Memory Efficiency**: Zero-copy packet implementation
- **Real-time Responsiveness**: Deterministic timing for embedded applications

### Scalability Requirements
- **Socket Limits**: No hard limits on TCP/UDP socket count
- **Interface Support**: Configurable multi-homing (NX_MAX_PHYSICAL_INTERFACES)
- **Packet Pool Management**: Dual packet pool support for optimization
- **Thread Priority**: Configurable IP thread priority and stack size

## Configuration Requirements

### System Configuration Options
- **Error Checking**: Configurable runtime error checking (NX_DISABLE_ERROR_CHECKING)
- **Debug Support**: Optional debug and tracing capabilities
- **Endianness Support**: Little/big endian architecture support
- **Fragmentation**: Configurable IP fragmentation/reassembly

### IPv6 Specific Requirements
- **IPv6 Ready Compliance**: Phase II IPv6 Ready Logo Certification
- **Address Configuration**: Stateless Address Auto Configuration (SLAAC)
- **Neighbor Discovery**: RFC 4861 compliant
- **Duplicate Address Detection**: Configurable DAD support
- **Path MTU Discovery**: Optional path MTU discovery

## Integration Requirements

### Development Environment
- **Build System**: Support for standard C build tools (GCC, IAR, Keil, etc.)
- **Header Files**: nx_api.h, nx_port.h inclusion required
- **Library Linking**: Static library linking (nx.a or nx.lib)
- **Configuration**: nx_user.h for custom configuration options

### Application Integration
- **Initialization**: nx_system_initialize() before any NetX Duo services
- **IP Instance Creation**: Minimum one IP instance with packet pool
- **Thread Integration**: Compatible with ThreadX thread model
- **Interrupt Handling**: ISR-safe packet reception/transmission

### Network Driver Requirements
- **Driver Interface**: Standard NetX Duo driver model compliance
- **Hardware Abstraction**: 4-byte aligned packet headers
- **Capability Support**: Hardware checksum offloading (optional)
- **Multi-interface**: Support for multiple physical interfaces

## Compliance and Certification Requirements

### Standards Compliance
- **RFC Compliance**: Full compliance with core TCP/IP RFCs
- **IxANVL Validation**: Industry standard network protocol validation
- **IPv6 Ready**: Certified IPv6 Ready Logo compliance

### Safety Certification
- **IEC 61508**: SIL 4 certified by SGS-TÜV Saar
- **UL Standards**: UL 60730-1, UL 60335-1, UL 1998 certified
- **Safety Critical**: Suitable for safety-critical embedded systems

## Optional Add-on Requirements

### Security Add-ons
- NetX Duo Secure TLS/DTLS
- NetX Duo Secure IPsec
- NetX Duo Crypto

### Cloud Connectivity
- Azure IoT Middleware for Eclipse ThreadX
- Microsoft Defender for IoT integration
- Device Update for IoT Hub support

### Networking Add-ons
- BSD Socket API compatibility layer
- WebSocket support
- Advanced routing capabilities