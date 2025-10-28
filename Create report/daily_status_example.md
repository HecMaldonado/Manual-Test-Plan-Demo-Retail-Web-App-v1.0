# Daily Status — Example and Template
Owner: Hector Maldonado  
App: Demo Retail Web App v1.0

How to use
- Create one entry per day. Keep it concise and action-oriented.
- Reference test IDs (e.g., TC-LOGIN-001) and defect IDs (e.g., WEB-123) for traceability.
- Include blockers/risks and your plan for the next day.

---

## Template (copy for each day)
Date: YYYY-MM-DD  
Build: x.y.z (e.g., 1.0.5)  
Environment: (OS/Browser/Resolution/Network)

Executed today
- Tests run: (list IDs or area totals)
- Results: PASS/FAIL/Blocked counts

New defects
- (ID) Title — Severity — Brief note
- (ID) Title — Severity — Brief note

Retests/closures
- (ID) Retest result — Fixed/Not Fixed — Notes

Blockers/risks
- (Env/tool/feature) — Impact — Mitigation/ETA

Notes
- Any scope changes, data issues, or deviations from plan

Plan for tomorrow
- Areas, test sets, or retests to execute next

---

## Example — 2025-10-28
Date: 2025-10-28  
Build: 1.0.5  
Environment: Windows 11 / Chrome 127 / 1920×1080@60 / Wi‑Fi

Executed today
- Smoke: 12 tests — 12 PASS (00:14 total)
- Functional: Login/Search/PDP — 9 tests — 8 PASS, 1 FAIL (TC-PDP-006)

New defects
- WEB-123 PDP variant change does not update availability — High — Repro 3/3 on 1.0.5
- WEB-124 Search results pagination skips page 2 on “recliner” — Medium — Repro 2/3

Retests/closures
- WEB-118 Profile save toast missing — Fixed — Retested in 1.0.5, PASS

Blockers/risks
- Coupon service intermittently unavailable in test env — Impacts TC-COUPON-009/010 — Mitigation: retest after service restart (ETA 10/29 AM)

Notes
- Minor copy mismatch on PDP (“colour” vs “color”) not logged; treating as Low priority for now
- Confirmed analytics calls present but not validating payloads in this cycle (out of scope)

Plan for tomorrow
- Execute Cart/Coupon functional set (TC-CART-007/008, TC-COUPON-009/010)
- Start Layout 1440p checks (TC-LYT-013)
- Retest WEB-123 after PDP hotfix if available
