# Security and privacy

This repository may be published publicly. Treat every committed file, screenshot, diagram, and example as information anyone can read and retain.

## Never publish

**Do not commit or share:**

- Public IP addresses or other externally identifying network values.
- Passwords, Wi-Fi keys, API keys, credentials, private keys, recovery codes, or tokens.
- Detailed sensitive network information, including exact internal addressing plans, router configuration, firewall rules, VPN details, or a complete inventory of devices.
- Unredacted logs, configuration exports, screenshots, URLs, or command output that may reveal any of the above.
- Personal data or identifiable information about household members, guests, or devices.

Do not place secrets in Markdown and assume they can be safely removed later. Git history may retain previously committed values even after a file is edited.

## Safer documentation practices

- Use placeholders such as `[DNS_SERVICE]`, `[CLIENT_GROUP]`, or `[UPSTREAM_RESOLVER]`.
- Use high-level diagrams and generic descriptions instead of real addresses, hostnames, or device names.
- Share only the minimum detail needed to explain a design or demonstrate a check.
- Sanitize screenshots, logs, and evidence before adding them; check metadata and surrounding context too.
- Store credentials in an appropriate local secret store, not in this repository.
- Avoid committing private configuration or backup files.
- If a real secret is exposed, treat it as compromised: revoke or rotate it, then address the Git history and any affected systems.

## Before each commit or publication

- [ ] Search changed files for IPs, hostnames, MAC addresses, usernames, and identifying device labels.
- [ ] Check for credentials, tokens, keys, private URLs, and recovery information.
- [ ] Review diagrams, screenshots, logs, and copied command output—not just prose.
- [ ] Confirm that network details are no more specific than necessary.
- [ ] Confirm planned work is not described as a completed or verified result.
- [ ] Review Git status and staged changes so unrelated or private files are not included.

## Incident note

If sensitive information is accidentally published, do not rely on deleting the line or file alone. Revoke or rotate exposed credentials, assess the disclosure, clean repository history where appropriate, and follow the hosting provider's guidance.

**Last privacy review:** [Not yet reviewed / YYYY-MM-DD]  
**Reviewer or method:** [Optional; omit personal details if not needed]
