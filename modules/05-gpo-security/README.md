# Module 05 — Group Policy + Security Hardening

## Goal
Implement GPOs for application restrictions, password policy, and account
lockout. Configure software firewall rules on DCs and file server.

## Status
⏳ Planned

## Policies Planned
- Block Control Panel, CMD, PowerShell access for standard users
- Password history: 3 passwords remembered
- Maximum password age: 45 days
- Minimum password length: 8 characters
- Block RDP (port 3389) on Domain Controllers
- Block ports 80/443 on Domain Controllers — DCs do not serve web requests

## Design Decisions
- GPOs applied at OU level, not domain level — allows different policies
  per department without affecting all users.
- Port 3389 blocked on DCs — RDP not needed on domain controllers.
  Remote management handled through approved admin tools only.

## Steps Completed
<!-- Document each step here as you complete it -->

## Issues Encountered
<!-- Any problems hit and how they were resolved -->

## Verification
<!-- GPO applied confirmation, policy test results -->
