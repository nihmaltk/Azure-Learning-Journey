## Azure Application Gateway & WAF

**Azure Application Gateway** is like a smart web traffic manager. It distributes incoming traffic to different servers and can inspect web requests.

**Web Application Firewall (WAF)** is a security layer in App Gateway that protects your app from attacks like SQL injection or cross-site scripting.

**Key Features:**
- Load balancing for web traffic (HTTP/HTTPS)
- SSL termination (handles HTTPS encryption)
- WAF for protection against web threats

## Azure Load Balancer

Distributes all types of network traffic (not just web) across multiple servers. It helps ensure no single server gets too much traffic.

**Key Features:**
- Works at transport level (Layer 4 - TCP/UDP)
- Supports inbound and outbound traffic

## Key Difference: App Gateway vs. Load Balancer

- Load Balancer (Layer 4): Operates at the transport layer. It's like a simple traffic director that only cares about IP addresses and ports. Good for any TCP/UDP traffic.

- Application Gateway (Layer 7): Operates at the application layer. It's like a smart traffic controller for web (HTTP/HTTPS) traffic. It understands URLs, headers, and can do more advanced routing and apply web-specific security (WAF).

## Azure DNS

A domain hosting service that translates domain names into IP addresses. Like a phone book for your Azure resources.

**Key Features:**
- Hosts custom domains
- Fast, secure, and globally available
- Easy integration with Azure services

## Azure Firewall

A cloud-based network firewall that inspects and controls traffic.

**Key Features:**
- Stateful traffic inspection (remembers past connections to make smarter decisions)
- Can block/allow traffic using rules
- Filters traffic based on domain names (FQDNs)
- Can use threat intelligence to block known bad IPs

## Key Difference: Azure Firewall vs. NSGs

- NSGs (Network Security Groups): Think of them as bouncers at the door of a single room (subnet/VM). They are simpler, free (mostly), and work at the IP/Port level. Good for micro-segmentation within your VNet.

- Azure Firewall: Think of it as the main security gate for the entire building (VNet). It's a more powerful, centralized, and paid service with advanced features (threat intelligence, URL filtering) for controlling traffic across VNets and to/from the internet. 
Often, you use both: Firewall for perimeter security and NSGs for internal subnet isolation.

## Virtual Network Peering

Connects two Virtual Networks (VNets) in Azure so they can talk to each other privately and directly.

**Key Features:**
- Works across Azure regions (Global Peering)
- No need for VPN
- Fast and low-latency traffic between VNets

## VNet Gateway

A device that connects your on-premises network to Azure using a secure VPN connection.

**Types:**
- Site-to-Site VPN: connects entire networks
- Point-to-Site VPN: for individual users connecting remotely

## VPN Gateway

A secure communication tunnel between your network and Azure.

**Key Features:**
- Uses encryption protocols like IPSec/IKE
- Supports high availability setups
- Supports dynamic routing using BGP

## Key difference between VNet Peering and VPN Gateway

**VNet Peering**: Connects Azure VNet to Azure VNet via Microsoft's private backbone (faster, lower latency).

**VPN Gateway**: Connects Azure VNet to external networks (or other Azure VNets) via the public internet with an encrypted tunnel (generally slower, higher latency).

## Comparison Table

| Service              | What It Does                              | Layer or Role                    |
|----------------------|-------------------------------------------|----------------------------------|
| App Gateway + WAF    | Manages web traffic + protects apps       | Layer 7 (HTTP/HTTPS)             |
| Load Balancer        | Balances general network traffic          | Layer 4 (TCP/UDP)                |
| Azure DNS            | Translates domain names to IP addresses   | DNS (Name Resolution)            |
| Azure Firewall       | Inspects & filters network traffic        | Network security layer           |
| VNet Peering         | Connects two Azure VNets directly         | Private internal routing         |
| VNet Gateway         | Connects Azure to on-prem via VPN         | Secure connection endpoint       |
| VPN Gateway          | Enables secure encrypted communication    | VPN tunnel management            |

