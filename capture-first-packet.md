# Activity Overview

As a security analyst, it’s important to know how to capture and filter network traffic in a Linux environment. You’ll also need to know the basic concepts associated with network interfaces.

In this activity, you’ll perform tasks associated with using tcpdump to capture network traffic. You’ll capture the data in a packet capture (p-cap) file and then examine the contents of the captured packet data to focus on specific types of traffic.

## Scenario

You’re a network analyst who needs to use tcpdump to capture and analyze live network traffic from a Linux virtual machine.
It starts with your user account, called analyst, already logged in to a Linux terminal.
Your Linux user's home directory contains a sample packet capture file that you will use at the end of the lab to answer a few questions about the network traffic that it contains.

## Linux Networking — Capture Your First Packet

This report was completed as part of the Google Cybersecurity Certificate. It documents how to use Linux Bash commands to capture and inspect network traffic. These tasks are foundational for network monitoring, packet analysis, and hands-on cybersecurity workflows.

## My Contributions
- Identified available network interfaces using Linux commands to determine where packet capture could occur
- Used tcpdump to inspect live network traffic and observe how packets flow through a selected interface
- Captured a sample of HTTP traffic and saved it to a .pcap file for later analysis
- Interpreted verbose output from tcpdump to understand packet structure, including IP headers, flags, and protocol details
- Applied filters to focus on specific traffic types (e.g., port 80) and reduce noise in the capture
- Loaded and reviewed saved packet data using tcpdump read options, including hexadecimal and ASCII views
- Practiced foundational skills in packet analysis, including identifying source/destination, protocol behavior, and traffic direction

## Testing My Knowledge
**Q1: What command would you use to capture 3 packets on any interface with the verbose option?**  
A: `sudo tcpdump -c3 -i any -v`

**Q2: What does the `-i` option indicate?**  
A: The network interface to monitor

**Q3: What type of information does the `-v` option include?**  
A: Verbose information

**Q4: What `tcpdump` command can you use to identify the interfaces that are available to perform a packet capture on?**  
A: `sudo tcpdump -D`


## Tools Used
- `ifconfig` — to identify network interfaces  
- `tcpdump -D` — to list available capture interfaces  
- `tcpdump -i` — to specify the interface for packet capture  
- `tcpdump -v` — to display verbose packet details  
- `tcpdump -nn` — to disable name resolution for IPs and ports  
- `tcpdump -c` — to limit the number of packets captured  
- `tcpdump -w` — to write captured packets to a `.pcap` file  
- `tcpdump -r` — to read saved `.pcap` files  
- `tcpdump -X` — to view packet contents in hex/ASCII  
- `curl` — to generate HTTP traffic for analysis  
- `ls` — to verify file creation  
- `sudo` — to execute privileged commands like `tcpdump` that require root access

## Reflections
- Capturing live traffic helped me understand how data flows through a network interface.
- Using tcpdump reinforced the importance of filtering and saving relevant packet data.
- Generating traffic with curl showed how application-layer activity appears in raw packet captures.
- Viewing packet data in hex and ASCII simulated real-world forensic analysis and deep packet inspection.
- This exercise strengthened my confidence in using Linux tools for hands-on network analysis.
