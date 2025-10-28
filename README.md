
---

## 4) Manual Test Plan — Demo Retail Web App v1.0

Owner: Hector Maldonado  
Test Window: 2 weeks (smoke, functional, regression)  
Date: 2025-10-28

### 1. Objective
Validate core shopping journeys on typical PC and Android setups with clear defect reporting and simple coverage/traceability.

Success criteria
- 0 Critical/High open at exit
- ≥ 95% pass rate on critical tests
- Smoke test ≤ 15 minutes; last 3 builds green

### 2. Scope
In scope
- Web (desktop): Login, Search, Product Detail Page (PDP), Cart, Coupon, Checkout (stub), Profile
- Cross‑configuration: 1080p/1440p, 60/120 Hz, windowed/borderless
- Android (sanity): basic navigation/layout on a Pixel‑class device

Out of scope
- Real payment settlement/tax, admin/back‑office, performance/load testing

### 3. Test Items
- Web App v1.0 (builds: 1.0.x)
- Browsers: Chrome (stable), Edge (stable)
- Android App/WebView (sanity only)

### 4. Environments
- Windows 11, Chrome stable; 1920×1080 @ 60/120 Hz; keyboard/mouse and controller (if supported)
- Android 14 (Pixel 7)

### 5. Risks & Assumptions
- Stable test accounts and seed data available
- Coupon logic/inventory may change during window (log as risk)
- Android covered as sanity only

### 6. Approach
- Smoke: Launch, login, browse, add to cart (≤ 15 mins)
- Functional: Requirements/use‑case driven test cases per area
- Regression: Re‑run critical tests after hotfixes
- Exploratory: 60‑minute timeboxes on Cart, Checkout, and PDP variations
- Usability: Clarity of labels, keyboard navigation, error messages
- Evidence: Screens/video for any failure; environment captured on each report

### 7. Entry/Exit Criteria
Entry
- Test environment ready; accounts created; build notes received

Exit
- All Critical/High closed or formally deferred; pass rate meets targets; summary report delivered

### 8. Test Cases (sample set)

| ID            | Title                      | Priority | Area     |
|---------------|----------------------------|----------|----------|
| TC-LOGIN-001  | Valid login                | High     | Login    |
| TC-LOGIN-002  | Invalid password           | High     | Login    |
| TC-NAV-003    | Browse categories          | Medium   | Nav      |
| TC-SEARCH-004 | Search by keyword          | High     | Search   |
| TC-PDP-005    | PDP loads                  | High     | PDP      |
| TC-PDP-006    | Select variant updates     | Medium   | PDP      |
| TC-CART-007   | Add to cart from PDP       | High     | Cart     |
| TC-CART-008   | Remove item from cart      | High     | Cart     |
| TC-COUPON-009 | Apply valid coupon         | High     | Cart     |
| TC-COUPON-010 | Reject invalid coupon      | Medium   | Cart     |
| TC-CHK-011    | Guest checkout (stub)      | High     | Checkout |
| TC-PROF-012   | Update profile info        | Medium   | Profile  |
| TC-LYT-013    | Layout at 2560×1440        | Medium   | Layout   |
| TC-AND-014    | Android nav sanity         | Low      | Mobile   |

Detailed examples
- TC-LOGIN-001 — Valid login  
  Preconditions: Valid account exists  
  Steps: Open site → Click Login → Enter valid email/password → Submit  
  Expected: Redirect to dashboard, user name visible

- TC-COUPON-009 — Apply valid coupon  
  Preconditions: Cart has coupon‑eligible item  
  Steps: Cart → Enter “SAVE10” → Apply  
  Expected: 10% discount applies; totals recalc; no crash

- TC-LYT-013 — Layout at 2560×1440  
  Steps: Set display to 2560×1440 → Relaunch → Visit PDP/Cart  
  Expected: No overlaps/cut‑offs; responsive layout intact

### 9. Configuration Matrix
- Windows 11: 1080p@60, 1080p@120, 1440p@60
- Browsers: Chrome stable, Edge stable
- Input: Keyboard/Mouse; Controller (if supported)
- Android 14 (Pixel 7)

### 10. Defect Workflow
- Log in Jira as Bug with: Summary, Environment, Steps, Expected, Actual, Severity, Attachments, Affects Version
- Status flow: To Do → In Progress → Ready for Test → Done
- Link Bug to User Story and failed Test Case IDs

### 11. Reporting

Daily status (template)
Date: YYYY-MM-DD 
Executed today: (IDs) 
New defects: (IDs, severity) 
Retests/closures: (IDs and results) 
Blockers/risks: 
Plan for tomorrow:


Final summary (contents)
- Pass/fail by area
- Open defects by severity (with IDs)
- Key risks and mitigations
- Recommendation: release readiness or defer items

### 12. Traceability (sample)
- Story WEB‑12 (Apply coupon) → TC‑COUPON‑009, TC‑COUPON‑010  
- Story WEB‑18 (Cart CRUD) → TC‑CART‑007, TC‑CART‑008  
- Story WEB‑05 (Login/Session) → TC‑LOGIN‑001, TC‑LOGIN‑002

### 13. Test Data
- User: test_user+01@example.com / P@ssword1
- Coupon: SAVE10 (valid), BADCODE (invalid)
- Address: 123 Test St, Lakeland, FL 33809

### 14. Templates

Defect template
Title: Environment: (Build, OS/Browser, Resolution/Refresh, Network) 
Steps to Reproduce: 
Expected: 
Actual: 
Severity/Priority: 
Evidence: (screens/video/logs) 
Links: (Story, Test Case)

Test case template
ID: Title: 
Preconditions: 
Steps: 
Expected: 
Priority: 
Evidence:


### 15. Severity definitions (quick reference)
- Critical: Crash/data loss/checkout blocked; no workaround
- High: Primary flow blocked; workaround unacceptable
- Medium: Secondary flow impacted; reasonable workaround exists
- Low: Cosmetic/text/minor layout; no functional impact

### 16. Schedule (example)
- Day 1: Setup + Smoke
- Days 2–5: Functional (Login/Search/PDP/Cart)
- Day 6: Checkout + Exploratory
- Day 7: Regression + Final report


---

## 4) Manual Test Plan — Demo Retail Web App v1.0

Owner: Hector Maldonado  
Test Window: 2 weeks (smoke, functional, regression)  
Date: 2025-10-28

### 1. Objective
Validate core shopping journeys on typical PC and Android setups with clear defect reporting and simple coverage/traceability.

Success criteria
- 0 Critical/High open at exit
- ≥ 95% pass rate on critical tests
- Smoke test ≤ 15 minutes; last 3 builds green

### 2. Scope
In scope
- Web (desktop): Login, Search, Product Detail Page (PDP), Cart, Coupon, Checkout (stub), Profile
- Cross‑configuration: 1080p/1440p, 60/120 Hz, windowed/borderless
- Android (sanity): basic navigation/layout on a Pixel‑class device

Out of scope
- Real payment settlement/tax, admin/back‑office, performance/load testing

### 3. Test Items
- Web App v1.0 (builds: 1.0.x)
- Browsers: Chrome (stable), Edge (stable)
- Android App/WebView (sanity only)

### 4. Environments
- Windows 11, Chrome stable; 1920×1080 @ 60/120 Hz; keyboard/mouse and controller (if supported)
- Android 14 (Pixel 7)

### 5. Risks & Assumptions
- Stable test accounts and seed data available
- Coupon logic/inventory may change during window (log as risk)
- Android covered as sanity only

### 6. Approach
- Smoke: Launch, login, browse, add to cart (≤ 15 mins)
- Functional: Requirements/use‑case driven test cases per area
- Regression: Re‑run critical tests after hotfixes
- Exploratory: 60‑minute timeboxes on Cart, Checkout, and PDP variations
- Usability: Clarity of labels, keyboard navigation, error messages
- Evidence: Screens/video for any failure; environment captured on each report

### 7. Entry/Exit Criteria
Entry
- Test environment ready; accounts created; build notes received

Exit
- All Critical/High closed or formally deferred; pass rate meets targets; summary report delivered

### 8. Test Cases (sample set)

| ID            | Title                      | Priority | Area     |
|---------------|----------------------------|----------|----------|
| TC-LOGIN-001  | Valid login                | High     | Login    |
| TC-LOGIN-002  | Invalid password           | High     | Login    |
| TC-NAV-003    | Browse categories          | Medium   | Nav      |
| TC-SEARCH-004 | Search by keyword          | High     | Search   |
| TC-PDP-005    | PDP loads                  | High     | PDP      |
| TC-PDP-006    | Select variant updates     | Medium   | PDP      |
| TC-CART-007   | Add to cart from PDP       | High     | Cart     |
| TC-CART-008   | Remove item from cart      | High     | Cart     |
| TC-COUPON-009 | Apply valid coupon         | High     | Cart     |
| TC-COUPON-010 | Reject invalid coupon      | Medium   | Cart     |
| TC-CHK-011    | Guest checkout (stub)      | High     | Checkout |
| TC-PROF-012   | Update profile info        | Medium   | Profile  |
| TC-LYT-013    | Layout at 2560×1440        | Medium   | Layout   |
| TC-AND-014    | Android nav sanity         | Low      | Mobile   |

Detailed examples
- TC-LOGIN-001 — Valid login  
  Preconditions: Valid account exists  
  Steps: Open site → Click Login → Enter valid email/password → Submit  
  Expected: Redirect to dashboard, user name visible

- TC-COUPON-009 — Apply valid coupon  
  Preconditions: Cart has coupon‑eligible item  
  Steps: Cart → Enter “SAVE10” → Apply  
  Expected: 10% discount applies; totals recalc; no crash

- TC-LYT-013 — Layout at 2560×1440  
  Steps: Set display to 2560×1440 → Relaunch → Visit PDP/Cart  
  Expected: No overlaps/cut‑offs; responsive layout intact

### 9. Configuration Matrix
- Windows 11: 1080p@60, 1080p@120, 1440p@60
- Browsers: Chrome stable, Edge stable
- Input: Keyboard/Mouse; Controller (if supported)
- Android 14 (Pixel 7)

### 10. Defect Workflow
- Log in Jira as Bug with: Summary, Environment, Steps, Expected, Actual, Severity, Attachments, Affects Version
- Status flow: To Do → In Progress → Ready for Test → Done
- Link Bug to User Story and failed Test Case IDs

### 11. Reporting

Daily status (template)
Date: YYYY-MM-DD 
Executed today: (IDs) 
New defects: (IDs, severity) 
Retests/closures: (IDs and results) 
Blockers/risks: 
Plan for tomorrow:


Final summary (contents)
- Pass/fail by area
- Open defects by severity (with IDs)
- Key risks and mitigations
- Recommendation: release readiness or defer items

### 12. Traceability (sample)
- Story WEB‑12 (Apply coupon) → TC‑COUPON‑009, TC‑COUPON‑010  
- Story WEB‑18 (Cart CRUD) → TC‑CART‑007, TC‑CART‑008  
- Story WEB‑05 (Login/Session) → TC‑LOGIN‑001, TC‑LOGIN‑002

### 13. Test Data
- User: test_user+01@example.com / P@ssword1
- Coupon: SAVE10 (valid), BADCODE (invalid)
- Address: 123 Test St, Lakeland, FL 33809

### 14. Templates

Defect template
Title: Environment: (Build, OS/Browser, Resolution/Refresh, Network) 
Steps to Reproduce: 
Expected: 
Actual: 
Severity/Priority: 
Evidence: (screens/video/logs) 
Links: (Story, Test Case)

Test case template
ID: Title: 
Preconditions: 
Steps: 
Expected: 
Priority: 
Evidence:


### 15. Severity definitions (quick reference)
- Critical: Crash/data loss/checkout blocked; no workaround
- High: Primary flow blocked; workaround unacceptable
- Medium: Secondary flow impacted; reasonable workaround exists
- Low: Cosmetic/text/minor layout; no functional impact

### 16. Schedule (example)
- Day 1: Setup + Smoke
- Days 2–5: Functional (Login/Search/PDP/Cart)
- Day 6: Checkout + Exploratory
- Day 7: Regression + Final report

