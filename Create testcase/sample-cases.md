# Sample Test Cases

Owner: Hector Maldonado  
Date: 2025-10-28  
App: Demo Retail Web App v1.0

Notes
- Record environment with each failure (Build, OS/Browser, Resolution/Refresh, Network).
- Attach screenshots/video for FAIL/Blocked.
- Priority definitions: Critical (crash/data loss/checkout blocked), High (primary flow blocked), Medium (secondary flow impacted), Low (cosmetic/minor layout).

---

## TC-LOGIN-001 — Valid login
Preconditions
- Valid account exists: test_user+01@example.com / P@ssword1

Steps
1) Open site
2) Click “Login”
3) Enter valid email/password
4) Click “Submit”

Expected
- Redirect to dashboard; user name visible; no error messages

Priority
- High

Evidence
- Screenshot of dashboard upon success

---

## TC-LOGIN-002 — Invalid password
Preconditions
- Account email exists

Steps
1) Open site → Login
2) Enter valid email and wrong password
3) Click “Submit”

Expected
- Clear error: “Invalid email or password”; no login; fields remain editable

Priority
- High

Evidence
- Screenshot of error message

---

## TC-NAV-003 — Browse categories
Preconditions
- Site is up; seeded categories available

Steps
1) From home, open “Furniture”
2) Click “Sofas”

Expected
- Sofas list loads with products; no console errors

Priority
- Medium

Evidence
- Screenshot of category page

---

## TC-SEARCH-004 — Search by keyword
Preconditions
- Indexing complete; products contain “recliner”

Steps
1) Enter “recliner” in Search
2) Press Enter

Expected
- Results relevant to “recliner”; filters visible; no empty page

Priority
- High

Evidence
- Screenshot of results

---

## TC-PDP-005 — Product Detail Page loads
Preconditions
- At least one searchable product

Steps
1) From results, click first product

Expected
- PDP shows title, price, images, description, and “Add to Cart”

Priority
- High

Evidence
- Screenshot of PDP

---

## TC-PDP-006 — Select variant updates price/availability
Preconditions
- Product with multiple variants (e.g., color/size)

Steps
1) Open PDP with variants
2) Change variant (e.g., Color: Blue → Gray)

Expected
- Price/availability updates accordingly; no layout shifts breaking UI

Priority
- Medium

Evidence
- Before/after screenshots

---

## TC-CART-007 — Add to cart from PDP
Preconditions
- PDP is open; product in stock

Steps
1) On PDP, click “Add to Cart”
2) Open Cart

Expected
- Cart count increments; item appears with correct price and quantity

Priority
- High

Evidence
- Screenshot of Cart

---

## TC-CART-008 — Remove item from cart
Preconditions
- Cart has at least one item

Steps
1) Open Cart
2) Click “Remove” on an item

Expected
- Item removed; totals update; no stale UI

Priority
- High

Evidence
- Before/after screenshots

---

## TC-COUPON-009 — Apply valid coupon
Preconditions
- Cart has coupon-eligible item; valid code: SAVE10

Steps
1) Open Cart
2) Enter “SAVE10”
3) Click “Apply”

Expected
- 10% discount applied; totals recalc; success message; no crash

Priority
- High

Evidence
- Screenshot of discounted totals

---

## TC-COUPON-010 — Reject invalid coupon
Preconditions
- Cart has at least one item

Steps
1) Open Cart
2) Enter “BADCODE”
3) Click “Apply”

Expected
- Clear error: “Invalid code”; totals unchanged

Priority
- Medium

Evidence
- Screenshot of error message

---

## TC-CHK-011 — Guest checkout (stub)
Preconditions
- Cart has at least one item; checkout stub enabled

Steps
1) Open Cart → “Checkout”
2) Fill shipping form (valid data)
3) Submit

Expected
- Confirmation page (stub) displays order summary; no processing errors

Priority
- High

Evidence
- Screenshot of confirmation page (stub)

---

## TC-PROF-012 — Update profile info
Preconditions
- Logged-in user; Profile page accessible

Steps
1) Open Profile
2) Change phone number (e.g., 555-123-4567)
3) Click “Save”
4) Refresh page

Expected
- “Saved” toast; new value persists after refresh

Priority
- Medium

Evidence
- Screenshot before/after; optional short video including refresh

---

## TC-LYT-013 — Layout at 2560×1440
Preconditions
- Display supports 2560×1440

Steps
1) Set resolution to 2560×1440
2) Relaunch app
3) Navigate PDP and Cart

Expected
- No overlaps/cut-offs; responsive layout intact; text readable

Priority
- Medium

Evidence
- Screenshots of PDP and Cart at 1440p

---

## TC-AND-014 — Android navigation sanity
Preconditions
- Android 14 (Pixel 7) or similar; site/app accessible

Steps
1) Launch app/site on Android
2) Open menu → navigate categories → open PDP
3) Add to cart (if available) → open cart

Expected
- Menus usable; pages load; no clipped UI; back button works

Priority
- Low

Evidence
- Screenshots of menu, PDP, and cart on Android
