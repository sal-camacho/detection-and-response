# Activity Overview 

As a security analyst, you’ll need to analyze network traffic in order to learn what type of traffic is being sent to and from systems on the networks you’ll be working with.

Previously, you learned about packet capture and analysis. Analyzing packets can help security teams interpret and understand network communications. Network protocol analyzers such as Wireshark, which has a graphical user interface or GUI, can help you examine packet data during your investigations. Since network packet data is complex, network protocol analyzers (packet sniffers) like Wireshark are designed to help you find patterns and filter the data in order to focus on the network traffic that is most relevant to your security investigations.

Now you’ll use Wireshark to inspect packet data and apply filters to sort through packet information efficiently.

In this activity, you’ll use Wireshark to examine a sample packet capture file and filter the network traffic data.


## Scenario

In this scenario, you’re a security analyst investigating traffic to a website.

You’ll analyze a network packet capture file that contains traffic data related to a user connecting to an internet site. The ability to filter network traffic using packet sniffers to gather relevant information is an essential skill as a security analyst.

You must filter the data in order to:

identify the source and destination IP addresses involved in this web browsing session,
examine the protocols that are used when the user makes the connection to the website, and
analyze some of the data packets to identify the type of information sent and received by the systems that connect to each other when the network data is captured.

### An overview of the key property columns listed for each packet:
- No. : The index number of the packet in this packet capture file
- Time: The timestamp of the packet
- Source: The source IP address
- Destination: The destination IP address
- Protocol: The protocol contained in the packet
- Length: The total length of the packet
- Info: Some infomation about the data in the packet (the payload) as interpreted by Wireshark

## Network Analysis — Analyze Your First Packet

This analysis was completed as part of the Google Cybersecurity Certificate. It documents how to analyze a packet capture file using Wireshark. These tasks are essential for network monitoring, incident response, and foundational packet analysis skills.

## Task 1. Explore data with Wireshark
Opened a network packet capture file that contains data captured from a system that made web requests to a site.

<img width="1920" height="932" alt="47" src="https://github.com/user-attachments/assets/ce2fd91e-5ddd-4d7f-b21e-cebb5f372f00" />

Scrolled down to the packet list until a packet is listed where the info column starts with the words 'Echo (ping) request'.

<img width="746" height="563" alt="48" src="https://github.com/user-attachments/assets/aabbb053-f058-4df6-a602-0c2065e98449" />

### Question: What is the protocol of the first packet in the list where the info column starts with the words 'Echo (ping) request'?
### Answer: ICMP

## Task 2. Apply a basic Wireshark filter and inspect a packet
Opened a packet in Wireshark for more detailed exploration and filtered the data to inspect the network layers and protocols contained in the packet.
Entered the following filter for traffic associated with a specific IP address: `ip.addr == 142.250.1.139`

<img width="753" height="560" alt="49" src="https://github.com/user-attachments/assets/94deaee4-ac58-4f8b-b38f-321f8d52cbcf" />

Double-clicked the first packet that lists TCP as the protocol. This opened a packet details pane window:

<img width="758" height="588" alt="50" src="https://github.com/user-attachments/assets/7ed9809b-f881-4aaa-8990-7139ad19b665" />

The upper section of this window contains subtrees where Wireshark will provide you with an analysis of the various parts of the network packet. The lower section of the window contains the raw packet data displayed in hexadecimal and ASCII text. There is also placeholder text for fields where the character data does not apply, as indicated by the dot (“.”).

## Task 2A. Navigating through subtrees

#### Double-click the first subtree in the upper section. This starts with the word Frame.
- This provides you with details about the overall network packet, or frame, including the frame length and the arrival time of the packet. At this level, you’re viewing information about the entire packet of data.
#### Double-click Frame again to collapse the subtree and then double-click the Ethernet II subtree.
- This item contains details about the packet at the Ethernet level, including the source and destination MAC addresses and the type of internal protocol that the Ethernet packet contains.
#### Double-click Ethernet II again to collapse that subtree and then double-click the Internet Protocol Version 4 subtree.
- This provides packet data about the Internet Protocol (IP) data contained in the Ethernet packet. It contains information such as the source and destination IP addresses and the Internal Protocol (for example, TCP or UDP), which is carried inside the IP packet.
- The source and destination IP addresses shown here match the source and destination IP addresses in the summary display for this packet in the main Wireshark window.
#### Double-click Internet Protocol Version 4 again to collapse that subtree and then double-click the Transmission Control Protocol subtree.
- This provides detailed information about the TCP packet, including the source and destination TCP ports, the TCP sequence numbers, and the TCP flags.
- The source port and destination port listed here match the source and destination ports in the info column of the summary display for this packet in the list of all of the packets in the main Wireshark window.

### Question: What is the TCP destination port of this TCP packet?
### Answer: Port 80 is the TCP destination port for this packet. It contains the initial web request to an HTTP website that will typically be listening on TCP port 80.

#### In the Transmission Control Protocol subtree, scroll down and double-click Flags.
- This provides a detailed view of the TCP flags set in this packet.

<img width="965" height="900" alt="51" src="https://github.com/user-attachments/assets/f0fa7382-1dec-4747-9c4c-04252571ac1c" />

## Task 3. Use filters to select packets
Used filters to analyze specific network packets based on where the packets came from or where they were sent to. You’ll explore how to select packets using either their physical Ethernet Media Access Control (MAC) address or their Internet Protocol (IP) address.
Entered the following filter to select traffic for a specific source IP address only: `ip.src == 142.250.1.139`

<img width="751" height="591" alt="52" src="https://github.com/user-attachments/assets/ff4e19e1-53ac-49ef-b6a0-10a9502ea4cd" />

(A filtered list is returned with fewer entries than before. It contains only packets that came from 142.250.1.139.)

Entered the following filter to select traffic for a specific destination IP address only: `ip.dst == 142.250.1.139`

<img width="747" height="588" alt="53" src="https://github.com/user-attachments/assets/2f7cb876-5dc5-4227-a3d4-d03778fcd2ca" />

(A filtered list is returned that contains only packets that were sent to 142.250.1.139.)


Entered the following filter to select traffic to or from a specific Ethernet MAC address. This filters traffic related to one MAC address, regardless of the other protocols involved: `eth.addr == 42:01:ac:15:e0:02`

<img width="750" height="586" alt="54" src="https://github.com/user-attachments/assets/b3d7baef-e963-4994-9fa0-adc6f3d11c3a" />

Double-clicked the first packet in the list

<img width="744" height="623" alt="55" src="https://github.com/user-attachments/assets/0031b2b6-d0b1-46ae-9e49-e902827033c6" />

(The MAC address you specified in the filter is listed as either the source or destination address in the expanded Ethernet II subtree.)

#### Double-click the Internet Protocol Version 4 subtree to expand it and scroll down until the Time to Live and Protocol fields appear.
- The Protocol field in the Internet Protocol Version 4 subtree indicates which IP internal protocol is contained in the packet.

### What is the protocol contained in the Internet Protocol Version 4 subtree from the first packet related to MAC address 42:01:ac:15:e0:02?
### Answer: TCP is the internal protocol contained in the first packet from MAC address 42:01:ac:15:e0:02.


---

## My Contributions

### Open and Inspect a Packet Capture File
- Launched the lab environment via Qwiklabs.
- Opened Wireshark on the Windows virtual machine.
- Loaded the provided `.pcap` file for analysis.

### Examine Packet Information
- Identified the first packet in the capture.
- Reviewed key fields including:
  - Source and Destination IP addresses
  - Protocol type (e.g., TCP, UDP, ICMP)
  - Packet length and timestamp
- Interpreted header details such as Ethernet, IP, and TCP layers.

### Apply Display Filters
- Used Wireshark filters to isolate specific traffic:
  - `http` to view web traffic
  - `ip.addr == 192.168.1.1` to focus on a particular host
- Analyzed filtered packets to understand communication flow.
- 
## Tools Used
- **Wireshark** — to open and analyze packet capture files
- **Display Filters** — to narrow down traffic types and hosts
- **Packet Details Pane** — to inspect protocol layers and payloads

## Reflections
- Opening a `.pcap` file and navigating Wireshark simulated real-world network forensics.
- Understanding packet structure reinforced foundational knowledge of network protocols.
- Applying filters demonstrated how analysts isolate relevant traffic during investigations.
