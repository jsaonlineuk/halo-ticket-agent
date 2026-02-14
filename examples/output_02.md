--- CLEANED TICKET ---
User Name: Not specified (new starter)
Issue Location: Outpatients Reception
Device Name / Asset Tag: Not specified
Category (Printer | EUC Hardware | Accounts/AD | Software | Clinical Software | ROUTE): Accounts/AD
Short Description: New starter unable to log in to laptop; credentials work elsewhere.
Detailed Description: User reports they cannot log in to a laptop. They believe the same password works on mobile/email but not on the PC. Account lockout suspected. Issue started yesterday.
User Impact: User unable to access workstation services.
Scope of Impact: Single user (based on provided info).
Duration / Time Open: Since yesterday.
Troubleshooting Performed: Not specified.
Severity (High/Medium/Low) + reason: Medium — user blocked from access; patient-care impact not specified.
Escalation Recommended (Yes/No) + reason: Yes — Accounts/AD trigger met (no resolution within 1 working day).

--- NEXT ACTIONS ---
1. Confirm username and check account status in AD (locked out/disabled/expired/password change required).
2. Check group memberships / provisioning status if new starter (access readiness).
3. Verify device is on domain and has network connectivity; confirm time sync (Kerberos).
4. Attempt login with known-good credentials (if policy allows) to isolate device vs account.
5. If account issues persist after standard AD actions, escalate to IAM/AD resolver group with timestamps and error messages.

Info to capture next: exact login error text, device name/asset tag, whether user is domain-joined, and any recent password changes.
