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

# Monday, September 11th: Basic Packet Analysis
* Last class: OSI model, a packet, PCAP
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