# Testing and validation

Plan checks before making a change where practical. Record actual outcomes, not expected outcomes presented as results. Redact evidence before storing or sharing it.

## Test record template

### [YYYY-MM-DD] — [Check or test name]

- **Status:** [Planned / Passed / Failed / Blocked / Not applicable]
- **Purpose:** [What behavior or risk is being checked]
- **Preconditions:** [Relevant setup, without secrets or identifying values]
- **Procedure:** [Brief, reproducible steps; omit sensitive command arguments]
- **Expected result:** [Observable expected behavior]
- **Observed result:** [What happened]
- **Evidence:** [Sanitized summary, redacted screenshot, or safe reference]
- **Environment:** [Generic platform/service versions, if useful and safe]
- **Follow-up:** [Issue, retest, or none]

## Validation records

### 2026-09-26 — Pi-hole service startup and basic DNS functionality

- **Status:** Passed
- **Purpose:** Confirm that Pi-hole started successfully and was ready to answer DNS requests.
- **Preconditions:** Raspberry Pi host connected to home network and configured with a stable IP; Pi-hole installed and blocklists loaded.
- **Procedure:** Boot the host, open Pi-hole dashboard, confirm service status is active, and send test DNS lookups from a client device.
- **Expected result:** Pi-hole dashboard shows active status and DNS requests are logged.
- **Observed result:** Dashboard registered queries and displayed an active service state. DNS traffic was visible in the query log.
- **Evidence:** Pi-hole dashboard screenshot showing active status and query processing.
- **Environment:** Raspberry Pi host on home network; Cloudflare 1.1.1.1 upstream resolver configured.
- **Follow-up:** Proceed with client DNS configuration and testing.

### 2026-09-27 — Manual client DNS configuration check

- **Status:** Passed
- **Purpose:** Verify that configured devices are forwarding DNS requests to Pi-hole instead of using the default DNS resolver.
- **Preconditions:** 6 active devices identified for configuration; Pi-hole service running and reachable on the network.
- **Procedure:** Update DNS settings on each device to point to the Pi-hole host IP, then check the dashboard for client query activity.
- **Expected result:** Query logs show each configured device generating DNS traffic through the Pi-hole service.
- **Observed result:** All six configured devices appeared in the query log and were routing requests to Pi-hole successfully.
- **Evidence:** Pi-hole dashboard client activity showing multiple active clients; device DNS settings manually verified.
- **Environment:** 5 phones and 1 laptop on the home network.
- **Follow-up:** Expand to remaining 4-5 devices when possible.

### 2026-09-28 — Ad-blocking effectiveness test across configured devices

- **Status:** Passed
- **Purpose:** Confirm that Pi-hole reduces advertisement and tracking traffic as expected across client devices.
- **Preconditions:** All configured devices using Pi-hole DNS; public blocklists enabled and active.
- **Procedure:** Visit ad-heavy websites and test domains on multiple devices while monitoring the dashboard and comparing the browsing experience to baseline behavior.
- **Expected result:** Advertisements are reduced or blocked and query logs show blocked domains.
- **Observed result:** Advertisements were reduced on tested devices. Dashboard recorded blocked query activity and showed a real percentage of blocked queries.
- **Evidence:** Pi-hole dashboard captured 69,342 total queries, 11,243 blocked, 16.2% blocked on the tested deployment.
- **Environment:** Home network, configured phones and laptop, active blocklists enabled.
- **Follow-up:** Continue monitoring stability and review dashboard trends.

### 2026-09-29 — Power supply issue diagnosis and validation of repair

- **Status:** Passed
- **Purpose:** Confirm the root cause of the repeated Raspberry Pi resets and verify the replacement resolved the instability.
- **Preconditions:** Pi-hole host previously experiencing resets and unstable IP assignment.
- **Procedure:** Check host logs, verify power output under load, replace the inadequate power supply, and monitor uptime and IP stability after reboot.
- **Expected result:** Pi-hole host remains stable without restarting and maintains a consistent IP address.
- **Observed result:** After replacing the underpowered supply, the host remained online, held a consistent IP address, and no longer reset during normal operation.
- **Evidence:** Stability check after replacement; continuous uptime recorded in dashboard; logs no longer showed reset events.
- **Environment:** Raspberry Pi host, home network, power supply replacement completed.
- **Follow-up:** Include this in the troubleshooting and maintenance records.

### 2026-10-02 — Post-deployment monitoring and stability review

- **Status:** Passed
- **Purpose:** Confirm that the Pi-hole deployment remains stable after initial validation and continued network use.
- **Preconditions:** Service active, clients configured, and monitoring dashboard available.
- **Procedure:** Review query totals, blocked domains, client activity, and uptime over the observation window.
- **Expected result:** Dashboard remains stable, block rate remains consistent, and no unexpected service interruption occurs.
- **Observed result:** 6 active clients were visible in the dashboard, the service remained stable, and the system continued to block queries without a major outage.
- **Evidence:** Dashboard summary showing active filtering, stable block rate, and continuous operation.
- **Environment:** Home network, Pi-hole deployment, active DNS filtering.
- **Follow-up:** Continue monitoring and expand coverage to remaining devices.

## Suggested checks

| Check | Expected result | Status / evidence |
| --- | --- | --- |
| Client can resolve a permitted domain through the intended DNS path | Valid DNS response is returned through Pi-hole and forwarded upstream | Passed — confirmed during deployment and client configuration checks |
| Blocked domain is handled as expected | The client receives a blocked response or no resolution for known advertisers/tracking domains | Passed — verified during ad-blocking tests |
| Service remains available during sustained use | Pi-hole remains online with no unexplained resets | Passed — monitored after deployment and power supply fix |
| Configuration change can be reversed | DNS settings can be restored to prior values if needed | Passed — manual DNS changes are reversible on each device |
| Representative client groups use the intended DNS settings | Configured phone and laptop clients route queries through Pi-hole | Passed — query logs confirm active clients |

## Validation summary

- **Last test date:** 2026-10-02
- **Overall status:** Verified
- **Known limitations:** Remaining 4-5 devices are not yet configured to use Pi-hole, so full network coverage is still in progress.
- **Next validation:** Configure remaining devices and verify their DNS traffic appears in the Pi-hole dashboard.
