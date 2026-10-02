# Milestones and progression

Keep milestones small enough to verify. A checkbox indicates completion only when the stated evidence exists; do not check an item merely because work was attempted.

## Status key

- **Planned** — agreed next work; not started.
- **In progress** — work has started; record the start date and current blocker or next action.
- **Blocked** — cannot continue; explain the dependency or decision needed.
- **Verified** — acceptance criteria passed and evidence is linked.
- **Deferred** — intentionally moved out of current scope.

## Completed milestones

- [x] **Verified — Define project scope and success criteria**
  - Acceptance: the charter includes project goals, constraints, scope, risks, and measurable checks.
  - Evidence: [Project charter](project-charter.md), [README.md](../README.md)
- [x] **Verified — Document the home network DNS design**
  - Acceptance: the architecture document shows the Pi-hole role, upstream resolver, router limitation, and client flow using privacy-safe labels.
  - Evidence: [Network architecture](network-architecture.md)
- [x] **Verified — Implement Pi-hole on the home network**
  - Acceptance: Pi-hole is installed and active, blocklists are enabled, and the dashboard shows live queries and blocking.
  - Evidence: [Progress log](progress-log.md), Pi-hole dashboard screenshot in project evidence
- [x] **Verified — Configure client DNS settings manually**
  - Acceptance: configured devices point to Pi-hole as their DNS server, and query traffic is visible in the Pi-hole dashboard.
  - Evidence: [Progress log](progress-log.md), device DNS configuration notes
- [x] **Verified — Validate ad-blocking effectiveness**
  - Acceptance: multiple devices were tested against ad-heavy content and the reduction in advertisements was observed and recorded.
  - Evidence: [Progress log](progress-log.md), project validation notes
- [x] **Verified — Monitor service stability and activity**
  - Acceptance: basic monitoring confirms the service is running consistently and filtering traffic without major interruption.
  - Evidence: [Progress log](progress-log.md), Pi-hole dashboard summary
- [x] **Verified — Complete privacy and publication review**
  - Acceptance: documentation avoids exposing sensitive data and follows the privacy checklist.
  - Evidence: [Security and privacy](security-privacy.md)

## Active milestone

- **Milestone:** Configure the remaining devices to use Pi-hole DNS
- **Status:** In progress
- **Started:** 2026-10-02
- **Next action:** Update the remaining 4-5 devices to use Pi-hole as their primary DNS resolver and confirm they appear in query logs.
- **Blocker or dependency:** Router does not support network-wide DNS override, so each remaining device must be configured manually.
- **Last updated:** 2026-10-02

## Planned milestones

- [ ] **Planned — Expand Pi-hole coverage to all home devices**
  - Acceptance: all devices on the home network use Pi-hole as their DNS resolver.
  - Evidence: Future client configuration record, Pi-hole dashboard client list
- [ ] **Planned — Add a recovery and continuity plan**
  - Acceptance: a fallback DNS process is documented and tested in case Pi-hole is restarted or unavailable.
  - Evidence: Future troubleshooting or deployment notes
- [ ] **Planned — Improve monitoring and maintainability**
  - Acceptance: a routine review process is documented for uptime, block rate, and false positives.
  - Evidence: Ongoing progress log entries and dashboard checks
- [ ] **Planned — Review and tune blocklists**
  - Acceptance: any false positives or performance issues are recorded and resolved with whitelist exceptions or list adjustments.
  - Evidence: Troubleshooting and lessons learned notes

## Milestone template

Use this section only after work has actually started.

- **Milestone:** [Name]
- **Status:** [In progress / Blocked]
- **Started:** [YYYY-MM-DD]
- **Next action:** [Concrete next step]
- **Blocker or dependency:** [None / Describe]
- **Last updated:** [YYYY-MM-DD]
