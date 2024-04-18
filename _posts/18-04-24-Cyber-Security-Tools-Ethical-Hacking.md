---

title:  "Cyber Security Tools - Ethical Hacking"
date: 2024-04-18 00:00:00 +0800 
categories: [Tools] 
tags: [cybersecurity, it, tools] 
---
![OS header](assets/tools-blog.jpg)

Here is a list over tools that is and can be used in the field of cyber security and mostly ethical hacking. 
<br>
*Im going to be adding more tools, and updating the current tools if needed, so stay tuned!*

## Sniffers

- **Wireshark**: The most popular packet sniffer with cross-platform support.
- **Tcpdump**: A popular CLI sniffer available for both the Unix and Linux platforms.
    - tcpdump -i eth0 # Capture on eth0
    - tcpdump -w cap.log # Write to cap.log
    - tcpdump -r cap.log # Read from cap.log


- **Windump**: Windows version of tcpdump.
- **Cain & Abel**: An all-in-one tool to capture packets and record passwords being used in a MiTM. It can create ARP and DNS poisoning events and the cracker works with methods such as network packet sniffing, dictionary, brute force, and cryptanalysis such as rainbow attacks.
- **Ettercap**: Works very similar to Cain and Abel. However, it can also help against SSL encryption.
- **Kismet**: Wireless sniffing tool used to locate and discover hidden SSID’s. It can be used to passively sniff the traffic and gain the password that way.
- **Netstumbler**: Wireless sniffing tool.
- **OmniPeek**: Provides data like Wireshark in addition to network activity and monitoring.
- **AirMagnet WiFi Analyzer Pro**: Sniffer, traffic analyzer, and network-auditing suite.
- **WiFi Pilot**: Wireless sniffing tool.
- **Ntop**: High-speed web-based traffic analysis.
- **Network Miner**: Packet sniffer, with a built-in OS fingerprinter. Drop-down navigator for filtering specific traffic. Automatically extracts files for packet capture; it will also extract images. It will also pull some credentials for specific sites. It can also filter out “keywords” to allow for filtering of specific information being sent across the network.

## Footprinting

- **Netcraft**
- **HTTPRecon**
- **ID Serve**
- **HTTPrint**
- **Web mirroring**:
    - Wget
    - BlackWidow
    - HTTrack
    - WebCopier Pro
    - Web Ripper
    - SurfOffline

## Scanners

- **Nmap**: Uses raw IP packets in novel ways to determine what hosts are available on the network, what services (application name and version) those hosts are offering, what operating systems (and OS versions) they are running, what type of packet filters/firewalls are in use, and dozens of other characteristics.
- **Angry IP Scanner**: (or simply ipscan) is an open-source and cross-platform network scanner designed to be fast and simple to use. It scans IP addresses and ports as well as has many other features.
- **Hping2 & 3**: Custom packet-crafting tool that can be used to precisely package packets to scan and penetrate networks and bypass known security features.
- **SuperScan**: Allows you to quickly scan a range of IP addresses and do TCP port scanning. It can check all ports, or the ones you select. It is a very fast and powerful tool. Supports banner grabbing, ping, whois, tracert. Recently bought by McAfee.
- **Zanti** (mobile): An Android software used to Scan Ports, MiTM, Session Hijack, Redirect URL traffic, used for Pentesting with a mobile device.
- **NBTScan**: It sends a NetBIOS status query to each address in a supplied range and lists received information in human readable form.
- **NetScan Tools**: Created in 1999 to automate the plethora of internet tools to work with one GUI supported by Windows platforms.
    - OS Fingerprinting
    - Packet sniffing
    - Port scanning
    - Packet flooding
    - Mail exchange validation
- **Vulnerability scanners**:
   - GFI LanGuard
   - Qualys
   - FreeScan
   - OpenVAS

- **ZoomInfo**
Used to gain business intelligence on users and organizations.

- **Infoga**
Open-source tool to gain email intelligence from public sources.

## Enumeration

- **DumpSec**: Reveals users, groups, printers, shares, registry info in an easy to digest human-readable format from a targeted system.
- **NetBIOS enumeration**: 
   - SuperScan
   - Hyena
   - NetBIOS Enumerator
   - NSAuditor
- **Netcat**: A simple tool that can read and write data across a TCP or UDP connection. It’s very useful because it can create almost any type of connection. Including session binding. It allows actors to create shell and reverse shell connections between two endpoints. Allowing them to send/receive files and execute commands on both the host and compromised systems. It has since lost support; consequently, the Nmap project has incorporated an upgraded version called Ncat.
- > nc -zv -w 1 google.com 21 # Scan Google’s port 21, -z scan, -v verbose, -w timeout
nc -lvp 6969 # Opens a server on 6969, -l listens, -v verbose, -p port 6969
nc 192.168.1.54 6969 # Banner Grab with GET / HTTP/1.1 after connecting
- **Cryptcat**: A variant of netcat that encrypts communication; making it useful to evade the detection of IDS or traffic sniffing.
- **TCPView**: It will enumerate all TCP and UDP connections on the endpoint running the application. Will resolve domain names for the IPs connected to the system. Monitors changing connections and can close existing connections.
- **Sysinternals Suite**: A suite of Sysinternal tools made by Microsoft for troubleshooting.
- **NirSoft Suite**: A suite of tools used to automate the troubleshooting of Windows.
- **Firewalk**: An active reconnaissance network security tool that attempts to determine what layer 4 protocols a given IP forwarding device will pass. It works by sending out TCP or UDP packets with a TTL one greater than the targeted gateway.
> firewalk -S1-1000 -i eth0 -n -pTCP 192.168.1.254 192.168.1.30 # Scan port 1-1000 through eth0, no hostname resolution, with TCP protocol, via gateway 192.168.1.254 against target 192.168.1.30

- **nslookup**: A network administration command-line tool available in many computer operating systems for querying the Domain Name System to obtain domain name or IP address mapping, or other DNS records.
- **DIG**: A network administration command-line tool for querying the Domain Name System. dig is useful for network troubleshooting and for educational purposes. It can operate based on command line option and flag arguments, or in batch mode by reading requests from an operating system file.
- **NBTSTAT**: A diagnostic tool for NetBIOS over TCP/IP. It's included in several versions of Microsoft Windows. It's 
primary design is to helo troubleshoot NetBIOS name resolution problems. 
- **Maltego**: An interactive data mining tool that renders directed graphs for link analysis.
- **sc query**: Obtains and displays information about the specified service, driver, type of service, or type of driver.
- **Web mirroring** - allows for discrete testing offline
   - HTTrack
   - Black Window
   - Wget
   - WebRipper
   - Teleport Pro
   - Backstreet Browser
- **SNMP enumeration**
   - Engineer's Toolset
   - SNMPScanner
   - OPUtils 5
   - SNScan
- **LDAP enumeration**
   - Softerra
   - JXplorer
   - Lex
   - LDAP Admin Tool
- **NTP enumeration**
   - NTP Server Scanner
   - AtomSync
   - Can also nmap adn Wireshark
