# Module 02 — Domain Controller (Wayne HQ)

## Goal
Install and promote DC1 as the forest root domain controller for abcxyz.local.
Configure DNS. Set static IP. Take baseline snapshot.

## Status
⏳ Planned

## VM Specs
| Setting | Value |
|---------|-------|
| VM Name | DC1-Wayne-HQ |
| RAM | 4096 MB |
| CPUs | 2 |
| Disk | 60 GB (dynamic) |
| Network | LAN Segment — Wayne_HQ |
| Static IP | 10.10.0.10 |
| Gateway | 10.10.0.1 (pfSense) |
| DNS | 127.0.0.1 (self) |

## Design Decisions
- DNS installed on DC1 — required for Active Directory to function correctly.
  pfSense handles upstream DNS forwarding to the internet only.
- Static IP assigned manually — DHCP reservation would also work but static
  is cleaner for a server that other machines need to find reliably.
- DSRM password stored securely in lab notes — required for directory
  services recovery if AD becomes corrupted.

## Steps Completed

## DC1 — Initial Build Status

**VM Configuration:**
- Hostname: DC1
- Operating System: Windows Server 2022 Standard (Desktop Experience)
- Network Adapter: Custom (Wayne_HQ LAN Segment)
- VMware Tools: Installed

**Static IP Configuration:**
- IP address: 10.10.0.10
- Subnet mask: 255.255.255.0 (/24)
- Default gateway: 10.10.0.1
- Preferred DNS server: 127.0.0.1

**Addressing convention note:** pfSense owns the .1 gateway address on
each site subnet. Primary site domain controllers are conventionally
assigned .10. DHCP-assigned clients fall in the .100-.200 range. DC1's
DNS is set to 127.0.0.1 (self) since it will become the authoritative
DNS server for the abcxyz.local domain once promoted to a domain
controller.

**Build note:** Initial Windows Server installation hit a known VMware
"Easy Install" bug that throws a "Windows cannot find the Microsoft
Software License Terms" error. Resolved by selecting "I will install
the operating system later" when creating the VM, then manually
mounting the ISO via VM Settings > CD/DVD after VM creation, bypassing
VMware's automated install wizard.

**Status:** VM built, renamed, static IP configured and confirmed
persistent. Ready for connectivity verification and AD DS role
installation in the next session.

## Issues Encountered
<!-- Any problems hit and how they were resolved -->

## Verification
<!-- Commands run and output confirming the module works -->
