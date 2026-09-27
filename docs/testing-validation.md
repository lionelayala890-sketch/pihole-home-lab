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

## Suggested checks

Adapt or remove these to fit the actual environment. A check is not a result until performed and recorded.

| Check | Expected result | Status / evidence |
| --- | --- | --- |
| Client can resolve a permitted domain through the intended DNS path | A valid response is returned through the documented resolver | Planned — [link or note] |
| A test domain covered by an enabled rule is handled as expected | Behavior matches the configured policy | Planned — [link or note] |
| Service unavailable or unreachable | Impact and recovery procedure are understood and documented | Planned — [link or note] |
| Configuration change can be reversed | Documented rollback restores the prior expected behavior | Planned — [link or note] |
| Representative client groups use the intended DNS settings | Results match the architecture and scope | Planned — [link or note] |

## Validation summary

- **Last test date:** [Not yet tested / YYYY-MM-DD]
- **Overall status:** [Not started / In progress / Issues found / Verified]
- **Known limitations:** [None recorded / Describe]
- **Next validation:** [Check and target date, if known]
