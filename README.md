# Pi-hole Home Network Project

A practical, privacy-conscious project journal for planning, building, validating, and improving a personal Pi-hole deployment on a home network.

This repository is both a working record and a portfolio-friendly explanation of the decisions behind the project. It is designed to be filled in as work happens—not to imply that a deployment, test, or result already exists.

## Project goals

- Record the project scope, requirements, and success criteria before implementation.
- Explain the network design at a useful level without exposing sensitive details.
- Keep an auditable journal of setup decisions, changes, tests, and lessons learned.
- Track progress from planning through deployment and ongoing maintenance.
- Make the work understandable to a technical reviewer while keeping the documentation easy to maintain.

## Skills this project can demonstrate

As the project develops, its documentation can provide evidence of:

- Network planning, DNS concepts, and service placement.
- Linux or platform administration, if applicable to the chosen environment.
- Change management, operational record-keeping, and rollback planning.
- Testing, validation, troubleshooting, and evidence-based decision-making.
- Security and privacy awareness for a home-network service.
- Clear technical writing and project planning.

These are areas the project is intended to exercise; this README does not claim that any implementation or outcome has been completed.

## Current status

**Project stage:** Documentation and planning scaffold.  
**Deployment status:** Not yet recorded.  
**Validation status:** No deployment or test results recorded.

Update this section as the project progresses. Distinguish planned work from work in progress and verified results; link to the relevant journal entry or evidence where appropriate.

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

Replace bracketed prompts with only the details you are comfortable sharing. Before publishing, follow the [security and privacy checklist](docs/security-privacy.md). Leave unknown values marked as not yet decided rather than guessing, and remove template guidance that no longer applies once the project has real records.
