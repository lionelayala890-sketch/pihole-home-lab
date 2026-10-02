# Project charter and goals

> **Status:** Complete — implementation verified September 26, 2026.

## Overview

- **Project name:** Pi-hole home-network deployment
- **Last updated:** 2026-10-02
- **Current stage:** Complete

## Purpose

**Problem or motivation:**  
Reduce the number of advertisements and tracking requests seen across devices on the home network. Gain practical experience with DNS servers, blocklists, and network-wide filtering while learning how DHCP and DNS integrate in a real-world environment.

**Intended outcome:**  
Deploy a working Pi-hole instance that filters DNS queries network-wide, reduces ad content and tracking domains across all connected devices, and provide a foundation for understanding DNS behavior and network traffic management.

## Goals and success criteria

| Goal | Success criterion | How it will be verified | Status |
| --- | --- | --- | --- |
| Block ads across all network devices | At least 15% of DNS queries are blocked by blocklists | Dashboard shows percentage blocked; test ad-heavy sites on multiple devices | Verified |
| Provide network-wide DNS filtering | All devices on the network resolve DNS through Pi-hole, not external resolvers | Check Pi-hole query logs; verify device DNS settings point to Pi-hole IP | Verified |
| Maintain DNS performance | Average DNS response time stays under 200ms; no noticeable slowdown on client devices | Pi-hole dashboard latency metrics; user testing on web browsing speed | Verified |
| Allow DNS bypass for specific services | Whitelist/blacklist functionality works as configured | Manual testing: block a known-good domain, verify it's blocked; unblock and verify it resolves | Verified |

## Scope

**Included**

- Pi-hole installation and configuration on home network
- Selection and integration of public blocklists
- Network-wide DNS redirection through DHCP or manual client configuration
- Testing and validation of ad blocking effectiveness
- Documentation of setup process, decisions, and lessons learned

**Not included**

- Changes to router firmware or advanced network architecture
- Custom blocklist creation or maintenance
- Integration with external logging or analytics services
- VPN or encryption configuration beyond standard DNS over HTTPS

## Constraints and assumptions

| Type | Detail | How it will be confirmed |
| --- | --- | --- |
| Constraint | Pi-hole must coexist with existing home network infrastructure without disrupting other services | Verify all devices can access network resources; DNS fallback plan tested |
| Constraint | Documentation must not expose network topology, IP addresses, or personal device names | Security and privacy checklist completed before publication |
| Assumption | Home network has a stable power source and internet connection | Uptime log over 7 days |
| Assumption | Clients can be configured to use Pi-hole as DNS server | Manual client testing and configuration record |

## Risks and mitigations

| Risk | Impact | Mitigation or contingency |
| --- | --- | --- |
| DNS service interruption | Clients may have difficulty resolving names or accessing the internet | Document fallback DNS; test recovery procedure; keep upstream DNS configuration available |
| Over-aggressive blocklist | Legitimate domains blocked, breaking services or user experience | Test blocklists before deployment; maintain whitelist; monitor query logs for false positives |
| Network performance degradation | Slow DNS response times; user frustration with latency | Monitor dashboard metrics; test client performance; optimize blocklist selection if needed |

## Definition of done

- [x] Scope and success criteria are agreed and documented.
- [x] The deployment is recorded with enough detail to reproduce safely.
- [x] Planned validation checks have recorded outcomes and evidence.
- [x] Recovery and maintenance steps are documented.
- [x] Public-facing documentation passes the [privacy review](security-privacy.md).

## Decision record

| Date | Decision | Rationale | Alternatives considered |
| --- | --- | --- | --- |
| 2026-09-26 | Deploy Pi-hole on home network | Direct, practical way to learn DNS and reduce ads; low-cost learning opportunity | Cloud-based DNS filtering, pfSense, Unbound |
| 2026-09-26 | Use public blocklists (StevenBlack, Firebog) | Community-maintained lists are well-tested and require no custom maintenance | Custom lists, single-source lists, manual domain blocking |
