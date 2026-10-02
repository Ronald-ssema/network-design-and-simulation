# Network Design & Simulation
### Small-office LAN, DHCP, enterprise wireless security, DNS & HTTP

**Author: Ronald Ssema** · **Platform: Cisco Packet Tracer** · **Project type: Academic network simulation** · **Outcome: Coursework passed**

A completed Cisco Packet Tracer coursework project covering the design and implementation of a small-office local area network (LAN). The project combines wired and wireless connectivity, DHCP address reservations, WPA2-Enterprise wireless security, and DNS and HTTP services.

The author reports completing and passing the coursework against the supplied brief. Configuration details below follow that brief and the author's completion statement; the topology image shows the submitted design.

[Download the Packet Tracer project](https://github.com/Ronald-ssema/network-design-and-simulation/raw/refs/heads/main/Network%20Design%20and%20Simulation%20using%20Cisco%20Packet%20Tracer.pkt) · [View the full topology](docs/images/network-topology.png) · [Review the testing documentation](docs/validation.md)

## Network topology

![Cisco Packet Tracer network topology with six PCs, two printers, three servers, a central switch, a router, and wireless clients](docs/images/network-topology.png)

*Original Packet Tracer topology screenshot. Device names identify the intended roles within the lab.*

## Design overview

The wired portion uses a star layout: desktop PCs, printers, and servers connect to a central switch. A Cisco 2911 router sits above the switch, with a wireless router and two mobile clients shown at the top of the topology.

The design brings together three areas of network study:

- **Wired LAN design:** a shared switching point for workstations, servers, and printers.
- **Wireless access:** a tablet and smartphone associated with a wireless router.
- **Network services:** separate servers labelled for DNS, HTTP, and AAA (authentication, authorisation, and accounting).

## Device inventory

| Component | Quantity | Visible device names / model | Role in the design |
| --- | ---: | --- | --- |
| Desktop PCs | 6 | PC1–PC6 | Wired client endpoints |
| Central switch | 1 | Switch0 | Connection point for wired devices |
| Router | 1 | Router1 / Cisco 2911 | Routing component |
| Wireless router | 1 | Wireless Router2 / HomeRouter-PT-AC | Wireless client access |
| Mobile clients | 2 | Tablet PC0, Smartphone0 | Wireless endpoints |
| Printers | 2 | Printer1, Printer2 | Shared network peripherals |
| Servers | 3 | DNS_Server, HTTP_Server, AAA_Server | DNS, web, and authentication service roles |

## Addressing and DHCP

The coursework specifies the private network **192.168.1.0/24**, subnet mask **255.255.255.0**, and default gateway **192.168.1.1**. The wireless router provides DHCP and acts as the default gateway in the assignment scenario. The addressing plan reserves consistent addresses for clients, printers, and servers.

| Device / role | IPv4 address | Allocation in the brief |
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

Mobile-client and AAA-server addresses are not specified in the supplied brief and are not inferred here.

## Wireless security

- **SSID:** `pollyvacher wireless`
- **Security mode:** WPA2-Enterprise
- **Encryption:** AES
- **Authentication:** RADIUS/AAA, with an AAA server included in the topology

The lab shared secret is omitted from this documentation. WPA2-Enterprise uses an authentication server; the router-to-RADIUS shared secret is distinct from user login credentials.

## DNS and HTTP services

The DNS server at `192.168.1.2` maps the lab hostname `www.pollyvacher.ac.uk` to the HTTP server at `192.168.1.3` using an **A record**. The coursework requires name-resolution and browser-access tests on both a PC and a mobile device.

The hostname is used inside the Packet Tracer simulation. Open `http://www.pollyvacher.ac.uk` in a simulated client's browser when exploring the lab.

## Testing and outcome

**Coursework outcome: passed, as reported by the author.** The assessment covered:

- Device-to-device connectivity checks for at least two device pairs.
- DNS resolution on at least one PC and one mobile device.
- HTTP access by hostname on at least one PC and one mobile device.

The public repository currently includes the simulation file and topology image. Command outputs and service-test screenshots have not yet been added; see the [testing documentation](docs/validation.md) for the assessment criteria and reproduction steps.

## Explore the project

1. Download the `.pkt` file using the link above, or clone this repository:

   ```bash
   git clone https://github.com/Ronald-ssema/network-design-and-simulation.git
   ```

2. Open Cisco Packet Tracer.
3. Select **File → Open**, then choose `Network Design and Simulation using Cisco Packet Tracer.pkt`.
4. Inspect device interfaces, IP settings, router configuration, and server services.
5. Use **Simulation** mode to explore packet flow and follow the [testing documentation](docs/validation.md) to reproduce the assessment checks.

GitHub cannot run or interactively preview `.pkt` files. Cisco Packet Tracer is required. The version used to save this project has not been recorded.

## Design notes

The brief describes wired clients connected to the wireless router. The supplied topology includes a central switch and an additional Cisco 2911 router. The diagram is retained as the author's actual design; the addressing table records the coursework plan, rather than a fresh inspection of every saved device setting.

The assignment also describes ISP/internet access. The available screenshot does not establish an external internet path, so this portfolio focuses on the local network and internal services.

## Repository contents

```text
.
├── README.md
├── Network Design and Simulation using Cisco Packet Tracer.pkt
└── docs/
    ├── images/
    │   └── network-topology.png
    └── validation.md
```

## Future improvements

- Add the coursework connectivity and service-test screenshots to the public repository.
- Document device interfaces, DHCP reservation mappings, and the AAA configuration without credentials.
- Record the Packet Tracer version used for reproducibility.
- Explore VLAN segmentation and access-control rules as extensions to the lab.
