# Future roadmap

Treat roadmap items as ideas until they are prioritized and accepted into the milestone list. Do not imply a feature is available because it appears here.

## Candidate improvements

| Priority | Idea | User or operational value | Dependencies / risks | Status |
| --- | --- | --- | --- | --- |
| High | Configure the remaining devices to use Pi-hole as their primary DNS resolver | Expands the ad-blocking benefit across the full home network and brings the deployment closer to full coverage | Each remaining device must be configured manually because the home router does not allow network-wide DNS override | In progress |
| High | Add a recovery and fallback plan for Pi-hole outages | Prevents network disruption if the DNS service becomes unavailable or restarts unexpectedly | Requires a documented fallback DNS procedure and client guidance; should be tested before relying on it | Planned |
| High | Document and monitor power stability for the Pi-hole host | Reduces the chance of future service interruptions caused by hardware instability | Requires periodic uptime checks and documentation of power supply performance | Verified |
| Medium | Review and tune the active blocklist set | Improves filtering quality while reducing false positives and unnecessary blocking | Blocklist changes should be tested carefully to avoid breaking legitimate services | Planned |
| Medium | Create a recurring maintenance routine for uptime, failed domain checks, and dashboard review | Keeps the deployment stable and makes future maintenance easier | Requires a consistent documentation habit and a review schedule | Planned |
| Medium | Expand documentation for client configuration and troubleshooting steps | Makes it easier to repeat the setup and help future users or reviewers understand the process | Relies on keeping the project documentation current as the setup evolves | Planned |
| Low | Explore a DHCP or router-based DNS override if the home network hardware permits it | Would make deployment easier to scale and reduce the need for manual device configuration | Depends on router capability, firmware limitations, and compatibility checks | Candidate |
| Low | Evaluate whether additional privacy or monitoring tools are worth adding | Could improve visibility into query patterns and service health, if the project expands | Extra tooling may add complexity or require more maintenance than the current home-lab scope | Candidate |

## Possible areas to consider

- Configure the remaining 4-5 home devices to use Pi-hole DNS.
- Document a clear fallback DNS plan if Pi-hole is offline or the host is rebooted.
- Review blocklist effectiveness and false positives after more clients are added.
- Improve monitoring for uptime, query volume, and blocked domain patterns over time.
- Record recurring maintenance checks for the Pi-hole host, power supply, and networking equipment.
- Reassess whether a router-level change is possible in the future to avoid manual per-device DNS editing.
- Keep the project privacy-safe by limiting documentation to logical labels and generic system descriptions.

## Review notes

- **Last reviewed:** 2026-10-02
- **Next review trigger:** When the remaining devices are configured or when the deployment changes materially
- **Items promoted to milestones:** [Project charter](project-charter.md), [Milestones](milestones.md), [Progress log](progress-log.md)
