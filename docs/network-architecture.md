# Network architecture

> **Status:** Template — replace prompts only with reviewed, shareable information.  
> Do not publish public IPs, exact addresses, hostnames, credentials, tokens, or a detailed map of a sensitive network. See [Security and privacy](security-privacy.md).

## Summary

- **Design status:** [Proposed / In progress / Verified]
- **Last reviewed:** [YYYY-MM-DD]
- **Service role:** [Describe at a high level]
- **Deployment location:** [Generic description, e.g. “inside the home network”; avoid a precise physical or network location]

## High-level topology

Use logical labels instead of actual network values. Remove any element that does not apply.

```text
[Internet / upstream resolver]
              |
       [Home router]
              |
        [Home LAN]
       /          \
[DNS service]   [Client devices]
```

**Diagram notes:** [Explain the intended relationship. Confirm whether the diagram is proposed or reflects a verified setup.]

## DNS request flow

1. A client [how it is expected to learn which resolver to use].
2. The client sends a DNS request to [logical service name, not a real hostname or address].
3. The Pi-hole service [filtering and forwarding behavior at a high level].
4. The upstream resolver [placeholder or general description].
5. The response returns to the client through [high-level path].

**Exceptions or alternate paths:** [For example, guest devices, VPN clients, or manually configured clients, if applicable.]

## Components and dependencies

| Component | Role | Selection / status | Dependency or note |
| --- | --- | --- | --- |
| Pi-hole service host | Runs the DNS filtering service | [Not selected / selected; shareable description] | [Power, network, or availability dependency] |
| Router / DHCP service | May distribute DNS settings | [Unknown / to be confirmed] | [Record capability only after verifying] |
| Client devices | Request name resolution | [Groups, not identifiable device names] | [Client-specific exceptions, if any] |
| Upstream DNS | Resolves requests forwarded by the service | [Not selected / selected] | [Privacy, reliability, and policy considerations] |

## Design choices to confirm

- [ ] Where client DNS settings will be configured.
- [ ] Whether the service will be the only resolver or one of multiple resolvers.
- [ ] How service unavailability will affect clients and how recovery will work.
- [ ] Which client groups should or should not use the service.
- [ ] How upstream DNS behavior will be selected and documented.
- [ ] How changes will be tested without disrupting other users.

## Privacy-safe publication check

- [ ] Topology uses logical labels; no real IPs, MAC addresses, or sensitive hostnames.
- [ ] No router screenshots, configuration exports, or client lists contain identifying details.
- [ ] All unresolved design choices are labeled as unknown or proposed.
- [ ] Publication reviewed against [Security and privacy](security-privacy.md).
