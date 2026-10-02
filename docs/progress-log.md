# Progress log

Add one concise entry for each meaningful change. Keep entries factual and link to fuller records when useful.

## Entry template

### [YYYY-MM-DD] — [Short summary]

- **Status:** [Planned / In progress / Verified / Blocked]
- **Change or observation:** [What changed or was learned]
- **Evidence / related record:** [Link, or "None yet"]
- **Next step:** [Action, or "None"]

---

## Updates

### 2026-09-26 — Pi-hole installation and initial setup

- **Status:** Verified
- **Change or observation:** Pi-hole installed and configured on home network. Selected and enabled blocklists from public sources (StevenBlack, Firebog). Dashboard confirmed active with DNS queries being processed and blocked.
- **Evidence / related record:** Pi-hole dashboard screenshot showing active status, 69,342 total queries processed, 11,243 queries blocked (16.2%)
- **Next step:** Configure devices to use Pi-hole as DNS server

### 2026-09-27 — Manual DNS configuration across devices

- **Status:** Verified
- **Change or observation:** Configured all connected devices on home network to resolve DNS through Pi-hole. Updated device settings manually to point to Pi-hole IP address. All devices now routing DNS queries through the Pi-hole instance.
- **Evidence / related record:** Device DNS settings verified; Pi-hole query logs show traffic from multiple clients
- **Next step:** Test ad blocking effectiveness across devices

### 2026-09-28 — Ad blocker effectiveness testing

- **Status:** Verified
- **Change or observation:** Ran targeted ad-reduction tests on each device. Visited known ad-heavy websites and tracked blocking behavior. Confirmed that ads were significantly reduced compared to baseline. Query logs show expected blocklist filtering in action.
- **Evidence / related record:** Test results documented with observed ad reduction across multiple devices and browsers
- **Next step:** Monitor performance and query patterns for ongoing validation

### 2026-10-02 — Monitoring and maintenance review

- **Status:** Verified
- **Change or observation:** Reviewed network activity over multi-day period. Pi-hole remained stable with consistent uptime. Dashboard metrics show sustained ad blocking (16.2% block rate) across 6 active clients. No service interruptions or configuration issues encountered. Network performance remains normal.
- **Evidence / related record:** Dashboard uptime log; query and block rate metrics over time
- **Next step:** Ongoing routine monitoring; document any issues or optimizations needed
