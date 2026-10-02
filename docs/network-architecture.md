# Network architecture

> **Status:** Verified — implemented and validated as of October 2, 2026.
> Network topology and DNS flow reflect the current deployment on the home network.

## Summary

- **Design status:** Verified
- **Last reviewed:** 2026-10-02
- **Service role:** Network-wide DNS filtering and ad blocking using Pi-hole. Reduces ad content and tracking requests across all configured client devices.
- **Deployment location:** Inside the home network, on a dedicated host running Pi-hole

## High-level topology

```text
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
