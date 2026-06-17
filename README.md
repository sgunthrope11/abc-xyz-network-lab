# ABC & XYZ Dealership — Enterprise Network Lab

## Overview
A multi-site enterprise network simulation built in VMware Workstation Pro on a single Windows desktop.
Based on a real network infrastructure proposal designed during my time at PCCC(2024).

Simulates a 5-location Active Directory infrastructure for a fictional auto dealership company
(ABC & XYZ) expanding from 2 standalone sites to a centralized 5-site enterprise network with
a new HQ in Wayne, NJ.

## Objectives
- Design and implement a multi-site Active Directory forest from scratch
- Simulate enterprise WAN routing between 5 sites using pfSense
- Apply least-privilege and role-separation security principles throughout
- Integrate on-premises AD with Azure AD for Microsoft 365 SSO
- Document every architectural decision and its reasoning

## Lab Environment
| Component | Detail |
|-----------|--------|
| Hypervisor | VMware Workstation Pro |
| Host OS | Windows (single desktop machine) |
| Server OS | Windows Server 2022 Standard Evaluation |
| Router/Firewall | pfSense CE |
| Domain | abcxyz.local |
| Sites | Wayne HQ, Paterson, Wanaque, East Orange, Lodi |

## Network IP Plan
| Site | Subnet | DC IP | Gateway (pfSense) |
|------|--------|-------|-------------------|
| Wayne HQ | 10.10.0.0/24 | 10.10.0.10 | 10.10.0.1 |
| Paterson | 10.10.1.0/24 | 10.10.1.10 | 10.10.1.1 |
| Wanaque | 10.10.2.0/24 | 10.10.2.10 | 10.10.2.1 |
| East Orange | 10.10.3.0/24 | 10.10.3.10 | 10.10.3.1 |
| Lodi | 10.10.4.0/24 | 10.10.4.10 | 10.10.4.1 |

## Module Progress
| Module | Description | Status |
|--------|-------------|--------|
| 01 | Network Foundation — VMware Workstation Pro + pfSense + site segments | 🔄 In Progress |
| 02 | Domain Controller — DC1 Wayne HQ, AD forest, DNS | 🔄 In Progress |
| 03 | Branch DCs — Multi-site AD, Sites & Services, replication | ⏳ Planned |
| 04 | File Server — Shared folders, permissions, SMB encryption | ⏳ Planned |
| 05 | GPOs & Security — Policies, firewall rules, password policy | ⏳ Planned |
| 06 | Azure AD — Hybrid identity, M365 SSO, Azure AD Connect | ⏳ Planned |

## Key Design Decisions
- **DHCP on pfSense, not the DC** — keeps Domain Controller attack surface minimal.
  A compromised DHCP server must never have direct access to AD.
- **DNS on DC1** — required for Active Directory to function. pfSense handles
  upstream DNS forwarding to the internet only.
- **File server on a separate VM** — never co-located on a Domain Controller.
- **LAN Segments per site** — VMware Workstation Pro LAN Segment mode used for each
  site segment. No lab VM is in Bridged mode except pfSense's WAN interface.

## Repository Structure
```
abc-xyz-network-lab/
├── README.md
├── docs/
│   ├── implementation-log.md
│   └── capstone-reference.md
├── modules/
│   ├── 01-network-foundation/
│   │   └── README.md
│   ├── 02-domain-controller/
│   │   └── README.md
│   ├── 03-branch-domain-controllers/
│   │   └── README.md
│   ├── 04-file-server/
│   │   └── README.md
│   ├── 05-gpo-security/
│   │   └── README.md
│   └── 06-azure-ad/
│       └── README.md
├── scripts/
│   └── README.md
└── diagrams/
    ├── README.md
    ├── 01-network-foundation/
    ├── 02-domain-controller/
    ├── 03-branch-domain-controllers/
    ├── 04-file-server/
    ├── 05-gpo-security/
    └── 06-azure-ad/
```

## Background
This lab is a hands-on implementation of a capstone network proposal, rebuilt from the
ground up as a working environment. Every module documents not just what was built,
but why each decision was made.
