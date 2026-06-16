# Module 06 — Azure AD + Microsoft 365 SSO

## Goal
Integrate on-premises abcxyz.local AD with Azure AD using Azure AD Connect.
Enable Single Sign-On for Microsoft 365 applications across all sites.

## Status
⏳ Planned

## Design Decisions
- Azure AD Connect installed on a dedicated VM, not on DC1.
  Rationale: role separation — sync service failure must not impact the DC.
- SSO via Azure AD allows users to authenticate once on-prem and access
  all M365 apps without re-entering credentials.
- Hybrid identity model — on-prem AD remains the source of truth.
  Azure AD is a synchronized copy, not a replacement.

## Steps Completed
<!-- Document each step here as you complete it -->

## Issues Encountered
<!-- Any problems hit and how they were resolved -->

## Verification
<!-- SSO test, user sync confirmation from Azure portal -->
