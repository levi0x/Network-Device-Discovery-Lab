# network-device-discovery-lab-

Objective

Perform endpoint-based network device discovery using native Windows tools and analyze how segmentation and access controls impact device visibility within a managed environment.

Environment

OS: Windows 11

Network Type: Managed school network

IP Address: 172.23.32.xxx

Subnet Mask: 255.255.240.0 (/20)

-------------------------------------------------------------------------------------

Tools Used

ipconfig

ipconfig /all

arp -a

Get-NetNeighbor -AddressFamily IPv4

-------------------------------------------------------------------------------------

Methodology

Used ipconfig to identify local IPv4 address and default gateway.

Verified subnet mask and calculated network range.

Used arp -a to view ARP cache entries.

Used PowerShell neighbor table to identify reachable IPv4 devices.

-------------------------------------------------------------------------------------

Findings

Note: Discovery was limited to devices present in ARP/neighbor tables and did not include active probing techniques.

Identified multiple IPv4 addresses within the same subnet (172.23.32.0/20).

Observed that only devices directly communicated with appear in ARP/neighbor tables.

Confirmed likely presence of network segmentation/client isolation controls in a managed environment.

Security Observation

Managed networks often restrict peer visibility using:

VLAN segmentation

Client isolation

Firewall filtering

This prevents unauthorized enumeration of all connected devices from a standard endpoint.

-------------------------------------------------------------------------------------

Key Takeaways

Understanding subnet masks is critical for determining valid IP ranges.

ARP tables show cached communication, not full network inventory.

Enterprise networks intentionally limit device visibility for security.
