# Activity Overview

As a security analyst, it’s important to know how to capture and filter network traffic in a Linux environment. You’ll also need to know the basic concepts associated with network interfaces.

In this activity, you’ll perform tasks associated with using tcpdump to capture network traffic. You’ll capture the data in a packet capture (p-cap) file and then examine the contents of the captured packet data to focus on specific types of traffic.

## Scenario

You’re a network analyst who needs to use tcpdump to capture and analyze live network traffic from a Linux virtual machine.

The lab starts with your user account, called analyst, already logged in to a Linux terminal.

Your Linux user's home directory contains a sample packet capture file that you will use at the end of the lab to answer a few questions about the network traffic that it contains.

## Linux Networking — Capture Your First Packet

This report was completed as part of the Google Cybersecurity Certificate. It documents how to use Linux Bash commands to capture and inspect network traffic. These tasks are foundational for network monitoring, packet analysis, and hands-on cybersecurity workflows.

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
- `Ctrl+C` — to stop live capture


## Reflections
- Capturing live traffic helped me understand how data flows through a network interface.
- Using tcpdump reinforced the importance of filtering and saving relevant packet data.
- Generating traffic with curl showed how application-layer activity appears in raw packet captures.
- Viewing packet data in hex and ASCII simulated real-world forensic analysis and deep packet inspection.
- This exercise strengthened my confidence in using Linux tools for hands-on network analysis.
