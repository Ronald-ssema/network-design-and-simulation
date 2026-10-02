# Testing and reproduction

[← Project overview](../README.md)

Connectivity, DNS resolution, and web access were covered in the completed coursework. The table below summarises the checks, followed by a guide for repeating them in Packet Tracer. Original command outputs and test screenshots are still to be added.

## Test coverage

| Area | Check | Expected behaviour |
| --- | --- | --- |
| LAN connectivity | Test at least two pairs of devices with suitable network commands. | Devices communicate successfully. |
| DNS on a PC | Resolve `www.pollyvacher.ac.uk` using a networking command. | The hostname resolves to `192.168.1.3`. |
| DNS on a mobile device | Repeat the name-resolution check on a mobile endpoint. | The hostname resolves to `192.168.1.3`. |
| HTTP on a PC | Browse to `http://www.pollyvacher.ac.uk` inside Packet Tracer. | The lab HTTP page loads. |
| HTTP on a mobile device | Open the same lab URL on a mobile endpoint. | The lab HTTP page loads. |

## Reproduce the checks

1. Open the saved `.pkt` project in Cisco Packet Tracer.
2. Check client addressing against the [addressing table](network-design.md#addressing-and-dhcp), including subnet mask `255.255.255.0`, gateway `192.168.1.1`, and DNS server `192.168.1.2`.
3. Inspect the wireless router's DHCP reservations and wireless settings. Check the SSID, WPA2-Enterprise/AES mode, and RADIUS server configuration.
4. Test two device pairs. For example, from PC1, `ping 192.168.1.111` targets PC2; from PC3, `ping 192.168.1.113` targets PC4. These example pairs can be used to repeat the connectivity checks.
5. On the DNS server, inspect the A record for `www.pollyvacher.ac.uk` and confirm its target is `192.168.1.3`.
6. On a PC and a mobile client, use an available name-resolution command such as `nslookup www.pollyvacher.ac.uk`. Command availability depends on the simulated endpoint; record the actual supported command and output used.
7. On both clients, use the simulated web browser to open `http://www.pollyvacher.ac.uk` and capture the loaded page.

## Evidence to add

Add original coursework screenshots showing DHCP reservations, wireless configuration with credentials hidden, two connectivity checks, the DNS record, and PC/mobile DNS and HTTP tests. Record the source device, expected result, actual result, and Packet Tracer version alongside each image.

The topology screenshot is already available in [the image folder](images/network-topology.png). It documents device layout; test outputs provide the separate evidence for service behaviour.
