# Network validation guide

Use this guide after opening the saved project in Cisco Packet Tracer. These are proposed checks; no pass results are claimed in this repository.

## 1. Record the configuration

Before testing, record each device's interface, IP address, subnet mask, default gateway, and DNS server where applicable. Inspect router and switch configurations to identify the actual subnets and routing behaviour. Record the Packet Tracer version from the application's About dialog.

Do not assume that the topology's server names imply enabled services. Inspect each server's **Services** tab to establish what is configured.

## 2. Run applicable checks

| Check | Procedure | Evidence to capture |
| --- | --- | --- |
| Local connectivity | Ping another PC on the same subnet from a PC command prompt. | Source/destination addresses and ping output. |
| Gateway reachability | Ping a client's configured default gateway. | Client IP settings and ping output. |
| Server reachability | Ping each server from a client, where ICMP is permitted. | Destination address and result for each server. |
| DNS resolution | If DNS is configured, resolve an existing record from a client using its configured DNS server. | DNS record, client DNS setting, and lookup result. |
| HTTP access | If HTTP is enabled, open the server's address in a client browser; also test its hostname if DNS is configured. | Browser result and the URL used. |
| Wireless connectivity | Check wireless association and addressing, then test an intended reachable destination. | Wireless settings and connectivity result. |
| AAA authentication | If AAA is configured, test an authorised login through a device configured to use that server, then test an invalid login. | Sanitised configuration and accepted/rejected results; omit credentials. |
| Packet flow | Use Simulation mode to follow an applicable ICMP, DNS, or HTTP exchange. | Event list and a brief explanation of the packet path. |

For every test, record the expected outcome, actual outcome, and any issue or fix. Mark checks that do not apply as **Not configured** instead of treating them as passed.

## 3. Publish the evidence

Save readable screenshots under `docs/images/` and link them from a short results table in this document. Include enough context to reproduce each test, but do not publish passwords or other secrets.
