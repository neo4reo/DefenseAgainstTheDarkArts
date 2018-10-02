# Tuesday, September 4th: Course Introduction
* This is my favorite course
* A little exercise:
	- When you hear the term "cyber security", list some topics, issues, or things that come to mind. Free-for-all
  - Observations?
    - Cyber Security is very broad and interdisciplinary
    - WARNING about this course: you will feel dumb and lost at times because of the enormous amount of Computer Science content you have not learned (and may not even have time to learn).  From a former student: "At times this class made me feel dumb, I'll admit, but coming out the other side I feel like my eyes have been opened to another layer of the web of technology that surrounds us."
* What this course is NOT
* What this course IS and expectations, outcomes:
  1. Question and debate everything, ask why
  2. Gain the mindset of thinking like an attacker, #whatcouldpossiblygowrong
  3. Gain the mindset to understand how things work and fail
  4. THAT picture
  5. Understand tradeoffs --which is what Security really is
  6. The ultimate goal of this course, to be revisited on the last day of this class
* The effect of not studying Security...
  - The Tacoma Bridge Failure https://www.youtube.com/watch?v=XggxeuFDaDU
* The schtick is very different in this course, and this may be arguably the most "different" course you will take in the CS curriculum
* The definition of security in the context of technology, information, computers
* Terminology: Is it Computer Security?  Is it Information Security (infosec)?  Is it Cyber Security?
* Technology requirements for this class: a hypervisor, and Kali Linux
* The basics you all absolutely need to have: experience and comfort with the command line
  - Why? Versatility, productivity, accessibility, scripting
  - Not everything can be accomplished by fancy graphics and GUIs (sometimes constrained to certain features too)
  - Many systems do not use a windows manager or have a graphical desktop interface (e.g., servers)
    - Graphical interface (especially on servers) => more software requirements, more overhead, more bloat, more vulnerabilities
  - Many security tools are command line based
  - Remote execution of commands
  - Lab 1

# Thursday, September 6th: Networking 101
* The really hard problems in Security
	- Sexual harassment and gender
* Why study networking?
	- Basics
  - The "Trinity of Trouble" by Gary McGraw
    - Complexity
    - Extensibility
    - Connectivity
	- The "Connectivity" issue
	- Where the "cool stuff" happens
	- The cyber attribution problem => https://twitter.com/thegrugq/status/706545282645757952
* The telephone conversation analogy for basic networking stuff
* Take it a step further: the OSI model and the seven layers
* Analogy for the OSI model: the US Postal Service => http://bpastudio.csudh.edu/fac/lpress/471/hout/netech/postofficelayers.htm
* Get comfortable reading Request For Proposals (RFPs):
	- Internet Protocol (IP): RFC 791 => http://www.ietf.org/rfc/rfc791.txt
	- Transfer Control Protocol (TCP): RFC 793 => http://www.ietf.org/rfc/rfc793.txt
* A packet: contains implementations of all the protocol layers; encapsulation model
* A PCAP: a file of packet captures from a network

# Tuesday, September 11th: Basic Packet Analysis
* Last class: TCP Three-Way Handshake, OSI model, IP Header, TCP Header, RFCs, a packet, PCAP
* simple.pcap
* Things that you can do with PCAP files
  - Visualizing the traffic; see which computer is communicating with who
  - Troubleshoot network problems
  - See if there is any malicious traffic or malware
  - Reconstruct files (e.g., images) and conversations
  - Rip out any username:password pairs sent-in-the-clear
* The Wall of Sheep
* Ettercap
* The next lab

# Thursday, September 13th: Sniffing
* Last class: we delved into basic packet analysis
  - Visualized network at a given time using Etherape
  - Extracted all images in PCAP using Driftnet
  - Filter packets by IP address in Wireshark
  - Extract username:password pairs sent in plaintext on the network using Ettercap
  - Reconstructed a conversation in Wireshark via show TCP stream
* Recent news: Tinder https://www.wired.com/story/tinder-lack-of-encryption-lets-strangers-spy-on-swipes/
* An almost ugly spat: https://twitter.com/0xmchow/status/941145910213562369
* So you may be curious: how did we at the Wall of Sheep capture all those packets?
* tcpdump, Wireshark, ettercap
* Two types of networks:
  1. Unswitched - packets flow through all devices on network but you look at only the packets addressed to you......
    - Welp... http://superuser.com/questions/191191/where-can-i-find-an-unswitched-ethernet-hub
  2. Switched - packets flow through specific devices on network (most networks now)
* Step 1: promiscuous mode
* LAN Tap: http://hakshop.myshopify.com/products/throwing-star-lan-tap-pro
* Address Resolution Protocol
  - IP address to MAC address on a network
  - Recall OSI model and packets
  - `arp -a`
  - ARP cache on machine for 20 minutes
  - No authentication
* ARP spoofing or ARP poisoning
* Bettercap
* Video: https://www.youtube.com/watch?v=9uiA6dGuEE0

# Tuesday, September 18th: Scanning, Reconnaisance
* Last class: sniffing unswitched and switched networks
* Is sniffing still relevant today?
* Preventing sniffing:
  1. Use encryption and encrypted network protocols
  2. VPN
  3. Use switched network......?
* Preventing ARP poisoning on switched network:
  - anti-arpspoof
  - ArpON
  - Antidote
  - Arpwatch
* Scanning
  - Why? Network reconnaissance.  Warfare 101
  - What devices and computers are up?
  - What ports are open on a computer?
  - What services are running?
  - Where are the computers geographically?
  - Determine possible vulnerabilities
* Is scanning still relevant today?
* Basic method: ping sweep
* Problems with ping?

# Thursday, September 20th: Scanning, Part II
* Last class: the idea of scanning, ping, Netcat...
* Think poking holes, "ask questions"
* Poking holes => finding interesting and unwanted stuff on networks
  - https://pen-testing.sans.org/blog/2017/02/28/opening-a-can-of-active-defense-and-cyber-deception-to-confuse-and-frustrate-attackers
* Netcat
* Nmap
* Geographical information: SHODAN

# Tuesday, September 25th and Thursday, September 27th: Distributed Denial of Service (DDoS) Attacks
* "Inexperienced users and script kiddies, on the other hand, try to solve every problem with the default SYN scan. Since Nmap is free, the only barrier to port scanning mastery is knowledge. That certainly beats the automotive world, where it may take great skill to determine that you need a strut spring compressor, then you still have to pay thousands of dollars for it... By default, Nmap performs a SYN Scan, though it substitutes a connect scan if the user does not have proper privileges to send raw packets (requires root access on Unix). Of the scans listed in this section, unprivileged users can only execute connect and FTP bounce scans." https://nmap.org/book/man-port-scanning-techniques.html
* Defending against scanners
  - No certain way
  - Firewalls?
  - Close services
  - Packet filtering
* What could possibly go wrong?
* Want to be stealthy!
* RFC 793: if ports are closed and you send "junk" to it, RST packet will be sent! (page 65 of https://tools.ietf.org/html/rfc793)
  - FIN scan: `sudo nmap -sF ...`
  - NULL scan: `sudo nmap -sN ...`
  - XMAS scan: `sudo nmap -sX ...`, # FIN, PSH, URG flags in packet
* Decoy:
  - `sudo nmap -D...`
  - spoofed connections
  - Must use real + alive IP address, else SYN flood
* The first "D" (Distributed) in DDoS: attack source is more than one, often thousands of, unique IP addresses
* SYN flood
  - The idea: exhaust states in the TCP/IP stack
  - Recall TCP/IP handshaking
  - Attacker sends SYN packets with a spoofed source address, the victim, (that goes nowhere)
  - Victim sends SYN/ACK packet but attacker stays slient
  - Half-open connections must time out which may take a while
  - Alas, good SYN packets will not be able to go through
  - Reference 1: https://www.cert.org/historical/advisories/CA-1996-21.cfm?
  - Reference 2, RFC 4987: https://tools.ietf.org/html/rfc4987
  - Reference 3: https://www.juniper.net/documentation/en_US/junos12.1x44/topics/concept/denial-of-service-network-syn-flood-attack-understanding.html
* Defending against SYN flood
  - Increase queue
  - Filtering
  - SYN cookies
  - Reduce timer for SYN packets
* Teardrop (old)
  - The idea: "involves sending fragmented packets to a target machine. Since the machine receiving such packets cannot reassemble them due to a bug in TCP/IP fragmentation reassembly, the packets overlap one another, crashing the target network device." https://security.radware.com/ddos-knowledge-center/ddospedia/teardrop-attack/
  - Recall RFC 791 (IP), the IP packet fields in question: Fragment Offset, Flag (namely "Don't fragment" and "More fragments")
  - Result: "Since the machine receiving such packets cannot reassemble them due to a bug in TCP/IP fragmentation reassembly, the packets overlap one another, crashing the target network device."
  - Reference: https://www.juniper.net/techpubs/software/junos-es/junos-es92/junos-es-swconfig-security/understanding-teardrop-attacks.html
* Ping of Death (old)
  - The idea: violate the IP contract
  - In RFC 791, the maximum size of an IP packet is 65,535 bytes --including the packet header, which is typically 20 bytes long.
  - An ICMP echo request is an IP packet with a pseudo header, which is 8 bytes long. Therefore, the maximum allowable size of the data area of an ICMP echo request is 65,507 bytes (65,535 - 20 - 8 = 65,507)
  - Result: "However, many ping implementations allow the user to specify a packet size larger than 65,507 bytes. A grossly oversized ICMP packet can trigger a range of adverse system reactions such as denial of service (DoS), crashing, freezing, and rebooting."
* ICMP Flood Attack => Overload victim with a huge number of ICMP echo requests with spoofed source IP addresses.
* UDP Flood Attack => Same idea of ICMP flood attack but using UDP packets

# Tuesday, October 2nd: Encoding
* How to defend against DDoS?
* About that target on the scanning lab
* This week and next week: cryptography, the foundation of Computer Security
* Encoding vs encryption: they are not the same
  - Encoding: "The purpose of encoding is to transform data so that it can be properly (and safely) consumed by a different type of system. The goal is not to keep information secret, but rather to ensure that it’s able to be properly consumed."
  - Encryption: "to transform data in order to keep it secret from others, e.g. sending someone a secret letter that only they should be able to read, or securely sending a password over the Internet. Rather than focusing on usability, the goal is to ensure the data cannot be consumed by anyone other than the intended recipient(s)."
  - Source: https://danielmiessler.com/study/encoding-encryption-hashing-obfuscation/
* So why did I give you a scanning lab, PCAP lab?  Finer points on target, set3.pcap
* About that peculiar port on the honeypot...
* About set3.pcap on the PCAPs lab:
  - A goal of this class: recognition and mindset
  - Base64: binary-to-text encoding scheme.  That is: binary data to ASCII
  - http://stackoverflow.com/questions/6916805/why-does-a-base64-encoded-string-have-an-sign-at-the-end
  - Why? Dangers in printing payload: https://unix.stackexchange.com/questions/73713/how-safe-is-it-to-cat-an-arbitrary-file
  - Why? Basic authentication on web. Example: https://github.com/LiamRandall/BsidesDC-Training/blob/master/http-auth/http-basic-auth-multiple-failures.pcap
* So far, you have been using tools like Ettercap, Nmap, Wireshark.  Now, you must learn how they work!

# Thursday, October 4th: Cryptography
* So now crypto...
* Definitions
* The golden rule: "Never Roll Your Own Crypto"
* Crypto algorithms: symmetric, hash functions, asymmetric
* Tradeoffs to consider:
  - Cost of breaking a cipher
  - Value of the information that is encrypted
  - Time required to break info
  - Lifetime of information?
* The only secure crypto algorithm: One-Time Pad
  - Video: https://www.khanacademy.org/computing/computer-science/cryptography/crypt/v/one-time-pad
* Symmetric algorithms: DES, AES, RC4. What do they provide in terms of security? What do they not provide?
* One way hash functions: MD5, SHA-1.  What do they provide in terms of security? What do they not provide?

# Thursday, October 11th: Crypto, Part II
* Last class: the golden rules of crypto, symmetric algorithms, one-way hash functions
* Today: more on one-way hash functions, asymmetric crypto
* Applications: checksums, Git hash (SHA-1), passwords
* Storing passwords the wrong way
* Storing passwords the wrong way, redux
* Storing passwords the right way with a salt
* Cracking user accounts on Linux systems:
  - Use /etc/passwd and /etc/shadow files from Linux-based systems
  - $algorithm$salt$hash
  - $1$ = MD5
  - $2$ = Blowfish
  - $5$ = SHA-256
  - $6$ = SHA-512
* Tool: John the Ripper.  Default: simple list then brute force
* Daniel Miessler's SecLists
* The spring 2018 password cracking contest
* Q: How long is your password good for?
* Asymmetric crypto, public and private keys: RSA
* Example: SSH, GitHub
* What does asymmetric crypto does not provide?