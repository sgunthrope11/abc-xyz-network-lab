# Module 03 — Branch Domain Controllers + Multi-Site AD

## Goal
Deploy domain controllers at each branch site. Configure AD Sites and Services,
subnet objects, site links, and verify replication between all sites.

## Status
⏳ Planned

## Branch Sites
| Site | Subnet | DC IP | Gateway |
|------|--------|-------|---------|
| Paterson | 10.10.1.0/24 | 10.10.1.10 | 10.10.1.1 |
| Wanaque | 10.10.2.0/24 | 10.10.2.10 | 10.10.2.1 |
| East Orange | 10.10.3.0/24 | 10.10.3.10 | 10.10.3.1 |
| Lodi | 10.10.4.0/24 | 10.10.4.10 | 10.10.4.1 |

## Design Decisions
- Each branch gets its own DC for local authentication — users log in against
  their site DC, not across the WAN to HQ.
- AD Sites and Services subnet objects map each 10.10.x.0/24 to its site —
  ensures clients authenticate against the correct local DC.
- Site links configured on the IP transport — controls replication schedule
  and cost between sites.

## Steps Completed
<!-- Document each step here as you complete it -->

## Issues Encountered
<!-- Any problems hit and how they were resolved -->

## Verification
<!-- repadmin /replsummary output, dcdiag results -->
