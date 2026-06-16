# Capstone Reference

Original capstone proposal summary — used as the planning baseline for this lab.
Implementation may deviate from the original design where better practices apply.
All deviations are documented in implementation-log.md.

## Company Background
ABC & XYZ is a fictional auto dealership partnership that originally operated
two independent sites (Paterson and Wanaque) each with a 5-PC LAN setup.
The company has since acquired two new dealerships (East Orange and Lodi) and
built a centralized super-servicing facility in Wayne, NJ serving as the new HQ.

## Original Problem Statement
- Centralize management from HQ rather than managing each site independently
- Low-cost solution with room for future expansion
- Incorporate a new internet marketing group at HQ

## Proposed Solution (Capstone)
- On-premises Active Directory with one domain, separated by sites and OUs
- Azure AD integrated for Microsoft 365 SSO
- Site-to-site VPN connecting all 5 locations
- Centralized file server at HQ
- Role-separated servers (DC, file server never co-located)

## Original IP Plan (Capstone)
The capstone originally used 192.168.x.x addressing.
Lab implementation uses 10.10.x.x to avoid conflicts with home network.
This is documented as a deliberate deviation — 10.x space is less likely
to conflict with common home router defaults (192.168.0.x / 192.168.1.x).
