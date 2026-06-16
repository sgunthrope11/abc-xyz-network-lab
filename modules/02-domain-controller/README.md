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
<!-- Document each step here as you complete it -->

## Issues Encountered
<!-- Any problems hit and how they were resolved -->

## Verification
<!-- Commands run and output confirming the module works -->
