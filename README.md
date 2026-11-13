# Velociraptor DFIR Homelab

## Project overview

Deployed and verified a Velociraptor server on an Ubuntu Server virtual machine using Oracle VirtualBox, with administrative access from a Windows 11 host. This academic homelab demonstrates Linux administration, virtual networking, firewall configuration, server configuration, and practical troubleshooting.

**Project result:** Successful access to the Velociraptor web interface and verification of the server's GUI and frontend services.

## Technologies

- Oracle VirtualBox and NAT Network (`velociNAT`)
- Ubuntu Server (virtual machine)
- Windows 11 (host)
- Velociraptor v0.75.1
- SSH, UFW, YAML configuration, and TLS with a self-signed certificate

## Lab network

| Component | Configuration |
| --- | --- |
| VirtualBox NAT subnet | `10.0.3.0/24` |
| Ubuntu Server IP | `10.0.3.200/24` |
| SSH forwarding | Host `2222` to guest `22` |
| GUI forwarding | Host `18889` to guest `8889` |
| Frontend forwarding | Host `18000` to guest `8000` |

These addresses and ports describe an isolated training environment, not an internet-facing deployment.

## Implementation highlights

1. Configured the VirtualBox NAT network, a static IPv4 address, and host-to-guest port forwarding.
2. Verified remote Ubuntu access over SSH and checked network interfaces with `ip addr show`.
3. Updated Ubuntu and installed utilities including `curl`, `unzip`, `net-tools`, and `ufw`.
4. Installed the Velociraptor Linux AMD64 binary and confirmed the installed version.
5. Generated the server configuration with the interactive wizard, then edited the YAML configuration to enable host access.
6. Configured UFW rules to permit the required frontend and GUI ports.
7. Started the server and verified successful login to the web interface from Windows 11.

## Troubleshooting and lessons learned

The primary challenges involved locating the generated server YAML file and adjusting network bindings so services were reachable through the virtual network rather than loopback only. This project reinforced how host port forwarding, guest service bindings, and firewall policy must align for connectivity.

## Evidence and full report

See [Velociraptor Server Installation Report (redacted PDF)](Velociraptor-Server-Installation-Report-Redacted.pdf) for the step-by-step documentation and screenshots of the installation, configuration, firewall rules, and successful GUI access.

## Security notes

- Credentials and course/instructor details were removed from the public report.
- The lab used a self-signed certificate for demonstration purposes.
- Configuration choices were made for a controlled lab; exposing an administrative GUI or binding it to all interfaces requires additional safeguards in production.
- Do not publish actual configuration files containing private keys, secrets, or reusable passwords.

## Skills demonstrated

`Linux` · `Virtual Networking` · `SSH` · `UFW` · `YAML` · `Server Deployment` · `DFIR Tooling` · `Troubleshooting` · `Technical Documentation`

---

*Academic homelab project by Sergio Alejandro Perez.*
