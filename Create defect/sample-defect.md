# Sample Defect — Demo Retail Web App v1.0

Owner: Hector Maldonado  
Date: 2025-10-28

---

## BUG: Cart crashes when applying SAVE10 after removing an item

Environment
- Build: Web 1.0.5
- OS/Browser: Windows 11, Chrome 127.0.x
- Display: 1920×1080 @ 60 Hz
- Network: Wi‑Fi

Repro Rate
- 3/3

Severity/Priority
- Critical / High

Steps to Reproduce
1) Add “Sofa A” and “Lamp B” to the cart
2) Go to Cart
3) Remove “Lamp B”
4) Enter promo code “SAVE10” and click Apply

Expected
- 10% discount applies to remaining item; totals recalculate; no crash

Actual
- Browser tab crashes (“Aw, Snap!”) immediately after clicking Apply

Evidence
- video.mp4 (00:12–00:25)
- console.txt (JavaScript error at cart.js:214; TypeError: cannot read properties of null)

Links (for traceability)
- Story: WEB‑45 (Apply Promo Code)
- Test Case: TC‑COUPON‑009

Notes
- Issue does not reproduce if the coupon is applied before removing an item.
- Also observed once at 1440p@60 (1/3) but could not consistently reproduce at that resolution.
