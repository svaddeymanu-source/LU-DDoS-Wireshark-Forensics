# LU-DDoS-Wireshark-Forensics
Wireshark-based forensic analysis project for identifying TCP-SYN DDoS attack traffic using baseline and attack PCAP evidence.
# Cybercrime-LU: Wireshark DDoS Forensic Analysis

## Project Title
Design LU based Forensic Network for Identifying DDoS Attack Traffic using Wireshark

## Course
CPSC 5207EL – Cybercrime  
Laurentian University  
Spring 2026

## Group Members
- Sandeep Vaddeymanu – 0474504
- Sadikur Rahman – 0463474
- Akashkumar Maheshkumar Patel – 0473876

## Project Overview
This project uses Wireshark to analyze baseline normal traffic and suspected TCP-SYN DDoS attack traffic. The goal is to compare normal and attack PCAP files, identify abnormal packet rates, apply forensic display filters, classify the attack type, and document mitigation strategies.

## Tools Used
- Wireshark Network Analyzer
- SDN-TCP-SYN ATTACK-DDOS dataset
- PCAP traffic captures
- Wireshark display filters
- I/O Graphs, Protocol Hierarchy, Conversations, and Endpoints

## Key Findings
- Baseline traffic: 369,702 packets over 6,954.333 seconds
- Attack traffic: 537,657 packets over 567.06 seconds
- Average packet rate increased from 53.2 pps to 948.1 pps
- TCP-SYN filter showed 179,246 SYN packets without ACK
- Victim IP: 172.17.237.22
- Major source IP: 172.17.237.23
- ICMP filter showed 0 packets
- Final classification: TCP-SYN Flood DDoS Attack

## Important Wireshark Filters
```bash
tcp.flags.syn == 1 && tcp.flags.ack == 0
tcp.flags.syn == 1 && tcp.flags.ack == 0 && ip.dst == 172.17.237.22
ip.dst == 172.17.237.22
ip.src == 172.17.237.23
icmp
