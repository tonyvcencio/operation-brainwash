Operation Brainwash — K-2SO

Project Summary

Repurposed a retired Aruba AP-303H enterprise access point into a dual-purpose OpenWrt network appliance.

Device: K-2SO
Firmware: OpenWrt 25.12.6
Platform: Aruba AP-303H
Status: Wired bridge operational; isolated wireless laboratory functional; final security checks in progress.

Network Architecture

Interface

Purpose

E0 (wan)

Home network uplink

E1 (lan1)

Xbox Van Dam — Series S

E2 (lan2)

Additional home-network device

E3 (lan3)

Dedicated maintenance interface

2.4 GHz radio

Isolated experimental Wi-Fi

Home Network

Management IP: 10.0.0.142

Upstream gateway: 10.0.0.1

Ethernet interfaces bridged without introducing another routed subnet for wired clients.

Wireless Laboratory

SSID: K-2SO-Lab

Subnet: 192.168.60.0/24

Gateway: 192.168.60.1

DHCP: 192.168.60.100–199

WPA2-Personal encryption

Wireless client isolation enabled

Separate firewall zone with restricted router access

IPv4 private-network forwarding restrictions

Verified Results

OpenWrt boots independently from internal NAND.

SSH and LuCI accessible from the home network.

Xbox Van Dam achieved 1,022 Mbps download and 113.36 Mbps upload, with 0% packet loss and 35 ms latency.

Wireless laboratory assigned a client address of 192.168.60.114.

Public internet access confirmed with cellular data unavailable.

Browser access to the home router and both K-2SO management addresses was blocked from the lab.

System timezone configured for America/New_York.

Lessons Learned

OpenWrt's BusyBox utilities differ from full Linux distributions.

Modern macOS SCP defaults to SFTP; scp -O supports OpenWrt's lightweight SSH environment.

Bridge configuration and firewall-zone assignments must be considered together.

Guest-network isolation requires more than a separate SSID.

Configuration backups should be stored outside the device and excluded from public repositories.

Remaining Validation

Confirm IPv6 isolation.

Verify the dedicated maintenance firewall zone.

Create the final configuration backup.

Record a sanitized configuration snapshot.