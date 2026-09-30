# Cisco EIGRP Routing Lab

## Overview

This project demonstrates a hands-on Cisco CML routing lab focused on **Enhanced Interior Gateway Routing Protocol (EIGRP)**.

The lab uses four Cisco IOS routers to explore dynamic routing, EIGRP metrics, unequal-cost paths, route failover, and route summarization.

The main goals were to:

- Configure EIGRP across multiple routers
- Verify dynamic route learning
- Observe how bandwidth affects EIGRP path selection
- Test unequal-cost load balancing using `variance`
- Configure EIGRP route summarization
- Troubleshoot routing using Cisco IOS commands

## Topology

The lab includes:

- **R1** – Shared LAN connection and multiple loopback networks
- **R2** – Connects the LAN to R3
- **R3** – Connects to both R2 and R4 and contains loopback networks
- **R4** – Provides an alternate path to R3
- **SW1** – Layer 2 connectivity between R1, R2, and R4

This topology creates multiple possible paths between R1 and R3, allowing EIGRP routing behavior to be tested.

## Technologies Used

- Cisco Modeling Labs (CML)
- Cisco IOS
- EIGRP
- IPv4 Routing
- Route Summarization
- Unequal-Cost Load Balancing
- Cisco CLI
- Network Troubleshooting

## EIGRP Configuration

EIGRP was configured using autonomous system **888**.

Example configuration on R1:

```text
router eigrp 888
 network 10.0.0.0
 network 172.16.40.0 0.0.0.255
 network 172.16.41.0 0.0.0.255
 network 172.17.0.0
 network 172.18.0.0
