# RouterNAT Router, Wi-Fi, IP and NAT Tools

[RouterNAT](https://routernat.com/) is a collection of browser-based networking tools and practical troubleshooting guides for home users, support technicians, network administrators, and small offices. The tools cover router login paths, public and private IP addressing, CGNAT, double NAT, subnetting, DHCP, DNS, Wi-Fi planning, port forwarding, and basic router security.

Most calculators process the supplied values in the browser. Tools that need an external observation, such as detecting a public IP address, clearly identify the network data required for the result. No account is required to use the public tools.

> **Repository scope:** This repository is a maintained directory and documentation companion for the live RouterNAT tools. The production CMS, credentials, private configuration, and server infrastructure are not published here.

## Start here

| Task | RouterNAT resource | What it helps determine |
| --- | --- | --- |
| Find the address visible to the internet | [What Is My IP](https://routernat.com/what-is-my-ip/) | Public IPv4/IPv6 address and connection context |
| Identify an internet provider | [What Is My ISP](https://routernat.com/what-is-my-isp/) | ISP and network information associated with the connection |
| Check for carrier-grade NAT | [CGNAT Check](https://routernat.com/cgnat-check/) | Whether the WAN address may be behind an ISP-shared NAT layer |
| Diagnose two routing layers | [Double NAT Checker](https://routernat.com/double-nat-checker/) | Whether two devices may be performing NAT on the same path |
| Test an inbound TCP service | [Open Port Checker](https://routernat.com/open-port-checker/) | Whether a selected TCP port is reachable from outside the LAN |
| Calculate IPv4 addressing | [IPv4 Subnet Calculator](https://routernat.com/subnet-calculator/) | Network, broadcast, usable range, mask, and CIDR details |
| Plan IPv6 prefixes | [IPv6 Subnet Calculator](https://routernat.com/ipv6-subnet-calculator/) | IPv6 prefix subdivision and address-planning information |
| Reserve stable LAN addresses | [Static IP Reservation Planner](https://routernat.com/static-ip-reservation-planner/) | DHCP scope and reservation planning without address conflicts |

Browse the complete, current directory at **[RouterNAT Network Tools](https://routernat.com/tools/)**.

## Tool groups

### Public IP, NAT, and port forwarding

- [IP Lookup](https://routernat.com/ip-lookup/) — review network information associated with an IP address.
- [CGNAT IP Range Checker](https://routernat.com/cgnat-ip-range/) — compare an address with the shared `100.64.0.0/10` range and other non-public ranges.
- [Common Ports Lookup](https://routernat.com/common-ports-lookup/) — identify frequently used TCP and UDP service ports before creating firewall or forwarding rules.
- [Port Forwarding Planner](https://routernat.com/port-forwarding-planner/) — organize external ports, internal hosts, protocols, and rule notes.

### Subnet, VLAN, and DHCP planning

- [VLSM Subnet Planner](https://routernat.com/vlsm-subnet-planner/) — divide an address block according to different host requirements.
- [VLAN, SSID, and Subnet Planner](https://routernat.com/vlan-ssid-subnet-planner/) — map wireless networks and VLANs to separate IP subnets.
- [DHCP Range Calculator](https://routernat.com/dhcp-range-calculator/) — choose a DHCP pool while preserving space for gateways, infrastructure, and reservations.

### Wi-Fi design and troubleshooting

- [Wi-Fi Channel Planner](https://routernat.com/wifi-channel-planner/) — compare channel width and channel overlap considerations.
- [Wi-Fi Coverage Planner](https://routernat.com/wifi-coverage-planner/) — estimate placement and coverage constraints before moving an access point.
- [Wi-Fi Repeater Speed Calculator](https://routernat.com/wifi-repeater-speed-calculator/) — estimate relay overhead and throughput reduction for repeated wireless links.
- [Wi-Fi QR Code Generator](https://routernat.com/wifi-qr-code-generator/) — create a QR code for sharing an SSID and its authentication details.

### Router security and diagnostics

- [Router Security Settings Database](https://routernat.com/router-security-settings-database/) — review security-related router settings and their practical purpose.
- [Router Admin Page Diagnosis](https://routernat.com/router-admin-page-not-opening-local-ip-diagnosis/) — find the correct local management path without treating a private gateway address as a public website.

## A practical NAT troubleshooting sequence

When a game server, camera, NAS, or self-hosted service remains unreachable, avoid changing random router settings. Use a reproducible sequence:

1. Confirm that the service is listening on the intended LAN device and local port.
2. Give that device a stable address through a DHCP reservation or a correctly planned static address.
3. Compare the router's WAN address with the observed public address.
4. Check whether the WAN address is private, shared CGNAT space, or globally routable.
5. Look for an upstream modem/router that may create double NAT.
6. Create the smallest necessary forwarding rule and match TCP or UDP to the actual application.
7. Permit the service in the host firewall, then test from a genuinely external network.

For the reasoning behind steps 3 and 4, read [How to Detect CGNAT by Comparing WAN IP and Public IP](https://routernat.com/how-to-detect-cgnat-by-comparing-wan-ip-and-public-ip/). If both addresses are public but the test still fails, use [Port Forwarding Still Closed With a Public IP: Layer-by-Layer Diagnosis](https://routernat.com/port-forwarding-closed-with-public-ip/).

## Privacy and result limits

Network calculators are decision-support tools, not replacements for packet captures, router logs, ISP confirmation, or vendor documentation. Results based on estimated RSSI, link rate, attenuation, geolocation, or third-party network data should be treated as technically justified planning estimates rather than guaranteed measurements.

Do not paste router passwords, PPPoE credentials, private keys, recovery codes, or complete configuration backups into a public issue. When reporting a problem, redact public IP addresses and any device identifiers that are not necessary to reproduce it.

## Reporting an issue

If a link is unavailable or a calculation appears incorrect, open a GitHub issue containing:

- the exact tool name and URL;
- the expected result and the result shown;
- sanitized input values sufficient to reproduce the problem;
- browser and operating-system versions; and
- a screenshot only after credentials and personal network details have been removed.

For account, privacy, or security-sensitive reports, use the contact route published on [RouterNAT](https://routernat.com/contact/) instead of a public issue.

## Repository mirrors

The directory is also maintained on [GitLab](https://gitlab.com/routernat-tools/router-ip-tools), [Codeberg](https://codeberg.org/routernatteam/router-ip-tools), and [Bitbucket](https://bitbucket.org/router-ip-tools/router-ip-tools/). The live tools and their documentation on RouterNAT remain the authoritative product resources.

## Maintenance

Last reviewed: November 2026. Tool availability can change as RouterNAT adds or consolidates network utilities. The [live tools directory](https://routernat.com/tools/) is the source of truth for the current catalogue.
