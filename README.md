# Network Design & Simulation
### A wired and wireless network lab in Cisco Packet Tracer

**Author: Ronald Ssema** · **Platform: Cisco Packet Tracer** · **Project type: Network simulation**

A network design project bringing desktop clients, mobile devices, shared printers, and dedicated server roles into one simulated environment. The topology combines a central switched LAN with a router and a wireless router, providing a practical setting for exploring network connectivity and client–server communication.

[Download the Packet Tracer project](https://github.com/Ronald-ssema/network-design-and-simulation/raw/refs/heads/main/Network%20Design%20and%20Simulation%20using%20Cisco%20Packet%20Tracer.pkt) · [View the full topology](docs/images/network-topology.png) · [Review the validation guide](docs/validation.md)

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
| Servers | 3 | DNS_Server, HTTP_Server, AAA_Server | Named network service roles |

## Explore the project

1. Download the `.pkt` file using the link above, or clone this repository:

   ```bash
   git clone https://github.com/Ronald-ssema/network-design-and-simulation.git
   ```

2. Open Cisco Packet Tracer.
3. Select **File → Open**, then choose `Network Design and Simulation using Cisco Packet Tracer.pkt`.
4. Inspect device interfaces, IP settings, router configuration, and server services.
5. Use **Simulation** mode to explore packet flow and follow the [validation guide](docs/validation.md) to record results.

GitHub cannot run or interactively preview `.pkt` files. Cisco Packet Tracer is required. The version used to save this project has not been recorded.

## Evidence and project scope

This repository includes the original simulation file and a topology screenshot. The device inventory and design description are based on the screenshot. Server labels describe intended roles; they do not by themselves confirm that the services are configured or working.

IP addressing, routing settings, service configuration, and end-to-end connectivity results are not yet documented. Green link indicators in the screenshot show link status at capture time, rather than proof of successful application traffic. The [validation guide](docs/validation.md) identifies the next checks and evidence to collect.

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

- Document the IP addressing plan, subnet masks, and default gateways.
- Capture connectivity and service test results.
- Record the Packet Tracer version used for reproducibility.
- Explore VLAN segmentation and access-control rules as extensions to the lab.
