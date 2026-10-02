# Setup and deployment journal

Record each meaningful setup or change session. Keep sensitive values out of entries; use generic component labels and redact command output.

## Entry template

### [YYYY-MM-DD] — [Short session title]

- **Status:** [Planned / In progress / Completed / Rolled back]
- **Objective:** [What this session intends to accomplish]
- **Scope:** [Systems or components affected, described generically]
- **Pre-checks:** [Backups, access, maintenance window, recovery path]
- **Actions taken:** [Ordered summary; omit secrets and sensitive identifiers]
- **Outcome:** [Observed result, or state that the work is not yet verified]
- **Validation:** [Checks performed; link to testing-validation.md]
- **Issues / follow-up:** [Anything unresolved; link to troubleshooting.md if useful]
- **Rollback:** [How changes were reversed, or how to reverse them]
- **Related records:** [Milestone, decision, or progress-log link]

---

## Journal entries

### 2026-09-20 — Initial Pi-hole host setup and configuration

- **Status:** Completed
- **Objective:** Install and configure Pi-hole on a Raspberry Pi host; enable blocklists and prepare the service for network deployment.
- **Scope:** Pi-hole host setup, OS installation, DNS service initialization, blocklist selection and loading
- **Pre-checks:** Host power and network access verified; no conflicts with existing network services
- **Actions taken:**
  1. Installed Raspberry Pi OS on the Pi-hole host
  2. Configured network interface with static IP assignment
  3. Installed Pi-hole via official installer
  4. Selected and enabled public blocklists (StevenBlack, Firebog)
  5. Verified DNS service listening on port 53
  6. Accessed Pi-hole dashboard and confirmed active status
- **Outcome:** Pi-hole service running and accepting DNS queries; dashboard shows active status and blocklist data loaded
- **Validation:** Dashboard query metrics visible; service responding to DNS requests on the home network
- **Issues / follow-up:** See [troubleshooting.md](troubleshooting.md) — power supply instability prevented stable IP assignment during initial setup
- **Rollback:** Configuration backups retained; service can be restarted cleanly from current state
- **Related records:** [Progress log](progress-log.md), [Project charter](project-charter.md)

### 2026-09-21 — Resolve Pi-hole host power supply issue

- **Status:** Completed
- **Objective:** Diagnose and resolve instability in the Pi-hole host caused by insufficient power delivery; ensure stable IP address assignment and uptime.
- **Scope:** Raspberry Pi host hardware, power supply replacement, network configuration
- **Pre-checks:** Service taken offline during troubleshooting; no active clients depending on the host during repair window
- **Actions taken:**
  1. Observed repeated host resets and inability to maintain a consistent IP address
  2. Tested power supply voltage output and identified insufficient current delivery
  3. Replaced original power supply with a higher-capacity unit meeting Raspberry Pi specifications
  4. Verified stable boot and consistent IP assignment after replacement
  5. Re-enabled DNS service and confirmed stable operation
- **Outcome:** Power supply replaced; Pi-hole host now boots consistently and maintains stable IP address. No further resets observed.
- **Validation:** Host remained online for 24+ hours without reset; dashboard shows continuous uptime
- **Issues / follow-up:** None; issue resolved
- **Rollback:** Original power supply retained as backup; current state is stable and preferred
- **Related records:** [Troubleshooting](troubleshooting.md#power-supply-instability-and-ip-reset-loop), [Progress log](progress-log.md)

### 2026-09-26 — Configure client devices to use Pi-hole DNS

- **Status:** Completed
- **Objective:** Update all client devices to use Pi-hole as their primary DNS resolver; establish network-wide filtering.
- **Scope:** 6 active client devices (5 phones, 1 laptop); manual DNS configuration on each device
- **Pre-checks:** Pi-hole service confirmed stable and online; AT&T router documented as not supporting network-wide DNS override; manual configuration approach planned
- **Actions taken:**
  1. Documented Pi-hole host IP address for client reference (using logical placeholder)
  2. Configured each of the 5 phones to use Pi-hole as primary DNS (Settings → WiFi → DNS configuration)
  3. Configured the laptop to use Pi-hole as primary DNS (Network settings → DNS)
  4. Tested DNS resolution on each device to confirm queries reaching Pi-hole
  5. Monitored Pi-hole dashboard query logs to verify traffic from all 6 clients
- **Outcome:** All 6 devices now routing DNS queries through Pi-hole; dashboard shows active queries from all configured clients
- **Validation:** Query logs show traffic from multiple clients; DNS resolution working on all devices
- **Issues / follow-up:** Remaining 4-5 devices on the network still use default DNS; planned for future phase (see [milestones.md](milestones.md))
- **Rollback:** DNS settings on each device can be reverted to manual entry or DHCP default if needed; clients documented for easy reversal
- **Related records:** [Network architecture](network-architecture.md), [Progress log](progress-log.md), [Milestones](milestones.md)

### 2026-09-28 — Ad-blocking effectiveness testing

- **Status:** Completed
- **Objective:** Validate that Pi-hole is reducing ad content across client devices; confirm blocklist filtering is working as intended.
- **Scope:** Testing on multiple client devices; ad-heavy websites and tracking domain verification
- **Pre-checks:** All 6 clients configured and confirmed using Pi-hole DNS; test sites and methods selected
- **Actions taken:**
  1. Visited known ad-heavy websites on multiple devices (phones and laptop)
  2. Observed significant reduction in displayed advertisements compared to baseline
  3. Checked Pi-hole dashboard query logs to verify blocked domains
  4. Confirmed 16.2% of queries were blocked, matching expected filtering behavior
  5. Tested whitelist functionality by temporarily allowing a previously blocked domain
- **Outcome:** Ad blocking confirmed working as expected across all tested devices; block rate consistent with blocklist coverage
- **Validation:** Visual confirmation of ad reduction; dashboard shows 16.2% block rate (11,243 queries blocked out of 69,342 total); no legitimate services disrupted
- **Issues / follow-up:** No issues; functionality verified
- **Rollback:** No changes required; service operating normally
- **Related records:** [Testing and validation](testing-validation.md), [Progress log](progress-log.md)

### 2026-10-02 — Monitoring and ongoing maintenance check

- **Status:** Completed
- **Objective:** Verify service stability, uptime, and consistent filtering performance over extended operation period.
- **Scope:** Pi-hole host monitoring; network query patterns; client activity review
- **Pre-checks:** Service has been running continuously since September 26; no interventions needed
- **Actions taken:**
  1. Reviewed Pi-hole dashboard uptime metrics over multi-day period
  2. Verified 6 active clients appearing in query logs
  3. Confirmed consistent block rate at 16.2% across observation window
  4. Checked for any error logs or service interruptions
  5. Documented baseline performance metrics for future reference
- **Outcome:** Service stable and performing consistently; no interruptions, restarts, or configuration issues observed
- **Validation:** Uptime log confirms continuous operation; query metrics stable; no client complaints or DNS failures reported
- **Issues / follow-up:** None; service operating nominally
- **Rollback:** N/A
- **Related records:** [Progress log](progress-log.md), [Milestones](milestones.md)
