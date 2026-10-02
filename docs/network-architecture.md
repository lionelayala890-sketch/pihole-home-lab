# Network architecture

> **Status:** Verified — implemented and validated as of October 2, 2026.  
> Network topology and DNS flow reflect the current deployment on the home network.

## Summary

- **Design status:** Verified
- **Last reviewed:** 2026-10-02
- **Service role:** Network-wide DNS filtering and ad blocking using Pi-hole. Reduces ad content and tracking requests across all configured client devices.
- **Deployment location:** Inside the home network, on a dedicated host running Pi-hole

## High-level topology

```
            [Internet]
                 |
          [Upstream DNS]
       (Cloudflare 1.1.1.1)
                 |
          [Home Router]
           (ATT Router)
                 |
          [Home LAN]
         /        |        \
   [Pi-hole]  [Configured]  [Unconfigured]
   (DNS      Clients (6)     Clients (4-5)
    Service)  • 5 phones
              • 1 laptop
```

**Diagram notes:** The Pi-hole instance receives DNS queries from manually configured clients and forwards unblocked requests to Cloudflare's upstream resolver (1.1.1.1). The AT&T router does not support network-wide DNS override, so all 6 currently active clients are configured individually with Pi-hole as their DNS resolver. Additional devices (~4-5) remain unconfigured and will be added to the service in future phases.

## DNS request flow

1. A client device (phone or laptop) initiates a DNS query. The device is configured manually to use Pi-hole as its primary DNS resolver.
2. The client sends a DNS request to the Pi-hole service on the home network.
3. The Pi-hole service receives the query and checks it against enabled blocklists (StevenBlack, Firebog). If the domain matches a blocklist, the query is blocked and a null response returned. If the domain is allowed, it is forwarded to the upstream resolver.
4. The upstream DNS resolver (Cloudflare 1.1.1.1) resolves the allowed query and returns the result to Pi-hole.
5. The response returns to the client device through the home network, completing the DNS resolution process.

**Exceptions or alternate paths:** 
- **Unconfigured devices** (4-5 devices) currently bypass Pi-hole and resolve DNS directly through the AT&T router's default upstream resolver, not filtered.
- **Whitelisted domains** can be manually added to override blocklists if a legitimate service is incorrectly blocked.
- **Manual fallback**: If Pi-hole becomes unavailable, manually configured devices will lose DNS resolution unless a secondary DNS is configured (currently not in place; a fallback strategy is planned).

## Components and dependencies

| Component | Role | Selection / status | Dependency or note |
| --- | --- | --- | --- |
| Pi-hole host | Runs DNS filtering and blocklist service | Active; dedicated Pi-hole instance running on home network | Requires stable power and network connectivity; currently no failover |
| AT&T Router | Provides home network gateway and DHCP | In use; does not support network-wide DNS override | Router limitation requires manual client configuration; DHCP does not distribute Pi-hole as DNS |
| Cloudflare 1.1.1.1 | Upstream DNS resolver | Selected; privacy-focused public resolver | Reliable, privacy-respecting alternative to ISP DNS |
| Client devices (configured) | Request name resolution through Pi-hole | 6 active clients: 5 phones, 1 laptop | All manually configured with Pi-hole IP as primary DNS |
| Client devices (unconfigured) | Bypass Pi-hole filtering | ~4-5 devices; to be configured in future phase | Currently use AT&T router default DNS; not yet optimized |
| Blocklists | Curated domain block lists for filtering | StevenBlack, Firebog sources | Public, community-maintained lists; no custom list maintenance required |

## Design choices and rationale

| Choice | Decision | Rationale | Verified |
| --- | --- | --- | --- |
| Manual client DNS configuration | Each device individually configured with Pi-hole IP | AT&T router does not support network-wide DNS override; manual config is only option | Yes |
| Cloudflare 1.1.1.1 upstream | Selected as upstream resolver | Privacy-focused, reliable, and fast public DNS service | Yes |
| Public blocklists only | Using StevenBlack and Firebog community lists | No custom maintenance required; well-tested and regularly updated by community | Yes |
| Phased rollout | 6 devices configured, 4-5 planned for future | Allows validation and troubleshooting on core devices before expanding scope | In progress |
| No DHCP integration | Clients manually configured instead of DHCP distribution | Router limitation; workaround is acceptable for home lab demonstration | Yes |

## Privacy-safe publication check

- [x] Topology uses logical labels; no real IPs, MAC addresses, or sensitive hostnames published.
- [x] Router model (AT&T) is generic enough; no configuration exports or credentials included.
- [x] Client groups described by type and count, not individual device names.
- [x] Upstream DNS is a public, privacy-respecting service (Cloudflare 1.1.1.1).
- [x] All design choices documented with rationale; no unresolved security concerns.
- [x] Publication reviewed against [Security and privacy](security-privacy.md).

## Future improvements and open questions

- Add a secondary DNS fallback to reduce service unavailability risk if Pi-hole goes offline.
- Configure remaining 4-5 devices to use Pi-hole DNS (planned for next phase).
- Evaluate DHCP integration alternatives if router can be upgraded or reconfigured.
- Monitor long-term blocklist performance and consider adding custom exceptions for false positives.
