# Pi-hole Home Network Project

A practical, privacy-conscious project journal for planning, building, validating, and improving a personal Pi-hole deployment on a home network.

This repository is both a working record and a portfolio-friendly explanation of the decisions behind the project. It is designed to be filled in as work happens—not to imply that a deployment, test, or result is complete unless it is explicitly documented.

## Project goals

- Implement Pi-hole on the home network to reduce the number of ads seen across connected devices.
- Use blocklists and DNS filtering to improve the browsing experience while maintaining privacy-conscious network practices.
- Learn how DNS servers work in practice and how they fit into a home network environment.
- Gain hands-on experience with network configuration, troubleshooting, and validating a service on a live network.

## Skills this project can demonstrate

As the project develops, its documentation can provide evidence of:

- Network planning, DNS concepts, and service placement.
- Linux or platform administration, if applicable to the chosen environment.
- Change management, operational record-keeping, and rollback planning.
- Testing, validation, troubleshooting, and evidence-based decision-making.
- Security and privacy awareness for a home-network service.
- Clear technical writing and project planning.

These are areas the project is intended to exercise; this README reflects the actual project outcome that was completed and validated.

## Current status

**Project stage:** Pi-hole implemented and validated.  
**Deployment status:** Completed and active on the home network since September 26.  
**Validation status:** Confirmed through targeted ad-reduction testing; the deployed Pi-hole reduced ads across the network as expected.

The Pi-hole dashboard confirms the service is active and filtering traffic. Screenshot evidence shows the deployment is processing queries successfully, with 69,342 total queries, 11,243 queries blocked, 16.2% blocked, and 309,659 domains on block lists. This aligns with the observed reduction in ads during testing.

## Follow the project

Start with the [documentation index](docs/README.md), then use the records below as the project evolves:

| Document | What it covers |
| --- | --- |
| [Project charter and goals](docs/project-charter.md) | Scope, motivation, constraints, and measurable success criteria |
| [Network architecture](docs/network-architecture.md) | Privacy-safe topology, DNS flow, dependencies, and design decisions |
| [Setup and deployment journal](docs/deployment-journal.md) | Dated implementation entries, changes, and rollback notes |
| [Milestones and progression](docs/milestones.md) | Planned work, active milestone, and evidence of completion |
| [Testing and validation](docs/testing-validation.md) | Test plan, expected outcomes, observed results, and evidence |
| [Troubleshooting and lessons learned](docs/troubleshooting.md) | Symptoms, diagnosis, resolution, and reusable lessons |
| [Future roadmap](docs/roadmap.md) | Prioritized follow-up work and ideas |
| [Security and privacy](docs/security-privacy.md) | Publication checks and safe documentation practices |
| [Progress log](docs/progress-log.md) | Concise dated record of meaningful changes |

## Working principles

1. **Document facts, not intentions as outcomes.** Use `Planned`, `In progress`, `Blocked`, or `Verified` and include dates for updates.
2. **Keep sensitive values out of Git.** Use the placeholders in the templates; review every change before publishing.
3. **Capture evidence without exposing the network.** Summarize results or use redacted screenshots and sanitized command output.
4. **Record decisions and reversibility.** Note why a change was made, how it was checked, and how it could be undone.
5. **Avoid tying the project to a particular device.** Record actual hardware and software only after they are selected.

## Repository structure

```text
.
├── README.md
└── docs/
    ├── README.md
    ├── deployment-journal.md
    ├── milestones.md
    ├── network-architecture.md
    ├── progress-log.md
    ├── project-charter.md
    ├── roadmap.md
    ├── security-privacy.md
    ├── testing-validation.md
    └── troubleshooting.md
```

## Updating the portfolio

Replace bracketed prompts with only the details you are comfortable sharing. Before publishing, follow the [security and privacy checklist](docs/security-privacy.md). Leave unknown values marked as not yet recorded or omit them entirely.
