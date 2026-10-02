# Network design and configuration

[← Project overview](../README.md)

Device inventory, addressing plan, and service configuration for the small-office LAN.

## Device inventory

| Component | Quantity | Device names / model | Role in the design |
| --- | ---: | --- | --- |
| Desktop PCs | 6 | PC1–PC6 | Wired client endpoints |
| Central switch | 1 | Switch0 | Connection point for wired devices |
| Router | 1 | Router1 / Cisco 2911 | Routing component |
| Wireless router | 1 | Wireless Router2 / HomeRouter-PT-AC | Wireless client access |
| Mobile clients | 2 | Tablet PC0, Smartphone0 | Wireless endpoints |
| Printers | 2 | Printer1, Printer2 | Shared network peripherals |
| Servers | 3 | DNS_Server, HTTP_Server, AAA_Server | DNS, web, and authentication service roles |

## Addressing and DHCP

The addressing plan uses the private network **192.168.1.0/24**, subnet mask **255.255.255.0**, and default gateway **192.168.1.1**. The wireless router provides DHCP and acts as the default gateway in the lab. The addressing plan reserves consistent addresses for clients, printers, and servers.

| Device / role | IPv4 address | Allocation |
| --- | --- | --- |
| Default gateway | 192.168.1.1 | Router LAN address |
| DNS server | 192.168.1.2 | Reserved server address |
| HTTP server | 192.168.1.3 | Reserved server address |
| PC1 | 192.168.1.100 | DHCP reservation |
| PC2 | 192.168.1.111 | DHCP reservation |
| PC3 | 192.168.1.112 | DHCP reservation |
| PC4 | 192.168.1.113 | DHCP reservation |
| PC5 | 192.168.1.114 | DHCP reservation |
| PC6 | 192.168.1.115 | DHCP reservation |
| Printer1 | 192.168.1.253 | DHCP reservation |
| Printer2 | 192.168.1.254 | DHCP reservation |

Mobile-client and AAA-server addresses are not included in this addressing table.

## Wireless security

- **SSID:** `pollyvacher wireless`
- **Security mode:** WPA2-Enterprise
- **Encryption:** AES
- **Authentication:** RADIUS/AAA, with an AAA server included in the topology

The lab shared secret is omitted from this documentation. WPA2-Enterprise uses an authentication server; the router-to-RADIUS shared secret is distinct from user login credentials.

## DNS and HTTP services

The DNS server at `192.168.1.2` maps the lab hostname `www.pollyvacher.ac.uk` to the HTTP server at `192.168.1.3` using an **A record**. Name-resolution and browser-access checks cover both a PC and a mobile device.

The hostname is used inside the Packet Tracer simulation. Open `http://www.pollyvacher.ac.uk` in a simulated client's browser when exploring the lab.

## Implementation notes

Wired endpoints connect through the central switch. The topology also includes a Cisco 2911 router and a wireless router. Interface settings are available in the saved simulation. The documented tests cover the LAN and internal services; external internet access is not covered.
