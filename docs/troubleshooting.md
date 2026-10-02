# Troubleshooting and lessons learned

Record issues encountered, how they were diagnosed, resolved, and what was learned for future reference.

## Entry template

### [Issue title]

**Symptom:**  
[What the user observed; how the problem manifested]

**Root cause:**  
[What actually went wrong; why it happened]

**Diagnosis steps:**  
1. [First diagnostic step]
2. [Second diagnostic step]
3. [etc.]

**Resolution:**  
[How the issue was fixed; step-by-step fix procedure]

**Verification:**  
[How you confirmed the fix worked; expected outcome]

**Prevention:**  
- [How to avoid this issue in the future]
- [What to check or test early]

**Lesson learned:**  
[Key takeaway for similar situations]

---

## Resolved issues

### Power supply instability and IP reset loop

**Symptom:**  
Raspberry Pi host running Pi-hole repeatedly reset and could not maintain a consistent IP address assignment. Service would come online briefly, then reboot unexpectedly, preventing reliable DNS service. Network clients lost connectivity whenever the host restarted.

**Root cause:**  
Original power supply was under-rated and failing to deliver sufficient current under load. Raspberry Pi resets when power delivery drops below minimum thresholds, triggering IP loss and service interruption. This is a common hardware failure mode in small single-board computers.

**Diagnosis steps:**  
1. Observed repeated system resets in host kernel logs
2. Checked power supply voltage output with a multimeter and found sagging under load
3. Compared measured voltage against official Raspberry Pi specifications (5V, ±5% tolerance)
4. Confirmed voltage was dropping below minimum threshold during DNS query processing
5. Tested with alternative higher-capacity power supply temporarily to confirm hypothesis
6. Issue disappeared with the higher-capacity unit, confirming root cause

**Resolution:**  
1. Powered down the Pi-hole host safely
2. Disconnected the original under-rated power supply
3. Replaced it with a higher-capacity unit meeting official Raspberry Pi power specifications (5V, 2.5A minimum)
4. Powered on the host and verified stable boot
5. Confirmed consistent IP address assignment in system logs
6. Re-enabled DNS service and verified stable operation

**Verification:**  
- Host remained online for 24+ hours without any reset
- Pi-hole dashboard shows continuous uptime since power supply replacement
- Network clients report stable DNS resolution with no interruptions
- No errors or power-related warnings in system logs

**Prevention:**  
- Verify power supply specifications before initial deployment (match or exceed device requirements)
- Monitor host uptime, reset frequency, and system logs during initial testing phase
- Use official or certified power supplies from reputable manufacturers to avoid compatibility issues
- Document actual power supply model and specifications for future reference and troubleshooting
- Test service stability for at least 24 hours before declaring deployment complete

**Lesson learned:**  
Even intermittent or hidden hardware failures (like underpowering) can completely prevent service stability and are easy to overlook if not tested systematically. Power delivery is a critical infrastructure dependency that must be verified early, not assumed to be correct. This issue delayed the project by one day but was resolved definitively once diagnosed properly.

---

## Open issues

No open issues currently recorded. Add items here if troubleshooting is in progress.

---

## Future considerations

- Monitor power usage over time as the service processes more queries; plan for power supply upgrades if needed
- Consider adding an uninterruptible power supply (UPS) or redundant power for high-availability scenarios (deferred for home lab scope)
- Document any false positives from blocklists and add exceptions as needed
