# Lab Report: Wireshark Packet Analysis

---

## Task 1: Explore Data with Wireshark

- Protocol of 'Echo (ping) request' packets: **ICMP**
- Summary:
  - Loaded `.pcap` file in Wireshark
  - Observed default columns: No., Time, Source, Destination, Protocol, Length, Info
  - Identified DNS (blue) and HTTP/TCP (green) packets

---

## Task 2: Apply Basic Filter and Inspect a Packet

- Filter used: `ip.addr == 142.250.1.139`
- TCP destination port: **80**
- TCP flags: Inspected (found initial connection flag set)
- Packet breakdown:
  - Frame layer: General packet metadata
  - Ethernet II: MAC address info
  - IPv4: IP addresses and encapsulated protocol (TCP)
  - TCP: Source/destination ports, flags

---

## Task 3: Use Filters to Select Packets

- `ip.src == 142.250.1.139` → Filtered outgoing packets from this IP
- `ip.dst == 142.250.1.139` → Filtered incoming packets to this IP
- `eth.addr == 42:01:ac:15:e0:02` → Filtered packets using MAC address
  - Internal protocol of first packet: **TCP**

---

## Task 4: Explore DNS Packets

- Filter used: `udp.port == 53`
- Observed Queries and Answers in DNS protocol layer
- Queried website: **opensource.google.com**
- Returned IP in DNS answer: **142.250.1.139**

---

## Task 5: Explore TCP Packets

- Filter used: `tcp.port == 80`
- TTL (Time To Live): **64**
- Frame Length: **54 bytes**
- IPv4 Header Length: **20 bytes**
- Destination IP: **169.254.169.254**

- Filter: `tcp contains "curl"`
  - Located packet with `"curl"` string in payload

---

## Conclusion

Skills Practiced:
- Reading and analyzing `.pcap` files
- Filtering by IP, MAC, protocol, and content
- Identifying DNS queries/responses and TCP payloads
- Navigating packet structures: Frame → Ethernet → IP → TCP

This is a fundamental skill for any security analyst working in network monitoring, incident response, or threat hunting.

---
