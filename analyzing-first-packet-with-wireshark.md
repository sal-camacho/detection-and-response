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


## Task 1. Explore data with Wireshark
Opened a network packet capture file that contains data captured from a system that made web requests to a site and scrolled down the packet list until a packet is listed where the info column starts with the words 'Echo (ping) request'.

<img width="1920" height="932" alt="47" src="https://github.com/user-attachments/assets/ce2fd91e-5ddd-4d7f-b21e-cebb5f372f00" />
<img width="746" height="563" alt="48" src="https://github.com/user-attachments/assets/aabbb053-f058-4df6-a602-0c2065e98449" />

### Question: What is the protocol of the first packet in the list where the info column starts with the words 'Echo (ping) request'?
### Answer: ICMP

## Network Analysis — Analyze Your First Packet

This analysis was completed as part of the Google Cybersecurity Certificate. It documents how to analyze a packet capture file using Wireshark. These tasks are essential for network monitoring, incident response, and foundational packet analysis skills.

## Task 2. Apply a basic Wireshark filter and inspect a packet
Opened a packet in Wireshark for more detailed exploration and filter the data to inspect the network layers and protocols contained in the packet.
Entered the following filter for traffic associated with a specific IP address. ip.addr == 142.250.1.139
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
