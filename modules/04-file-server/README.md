# Module 04 — File Server + Folder Permissions

## Goal
Deploy a dedicated file server VM. Configure shared folders with group-based
permissions. Enable SMB encryption for data in transit between sites.

## Status
⏳ Planned

## Design Decisions
- File server on its own VM, never co-located on a Domain Controller.
  Rationale: role separation — a compromised file server must not give
  access to AD authentication infrastructure.
- SMB encryption enabled — protects data transferred across site tunnels.
- Folder access controlled by AD security groups, not individual accounts.
  Easier to manage at scale and survives user account changes.

## Steps Completed
<!-- Document each step here as you complete it -->

## Issues Encountered
<!-- Any problems hit and how they were resolved -->

## Verification
<!-- Access tests, SMB encryption confirmation -->
