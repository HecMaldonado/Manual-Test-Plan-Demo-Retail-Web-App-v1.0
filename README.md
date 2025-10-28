# Manual QA Portfolio — Demo Retail Web App

Owner: Hector Maldonado  
Lakeland, FL • (347) 207-7133 • Hector.R.Maldonado@gmail.com • github.com/HecMaldonado  
Date: 2025-10-28

This repository showcases my manual QA skills: a concise test plan, a small test case set, a defect template, and daily status reporting—focused on smoke/regression and multi‑configuration testing across PC and Android. Artifacts are structured to fit Jira and Xray/TestRail workflows.

---

## 1) Jira — Quick guide for manual testers

What it is
- Work tracking system used to manage Bugs, User Stories, Tasks, and Epics. Teams use it to log, track, and resolve defects through a defined workflow.

Key concepts
- Issue: A tracked item (Bug, Story, Task).
- Project: A collection of related issues.
- Workflow: Status flow (e.g., To Do → In Progress → Ready for Test → Done).
- Board: Kanban/Scrum visualization of issues by status.

How I file a defect (fields I use)
- Summary (concise), Environment (Build/OS/Device/Browser/Resolution/Network), Steps to Reproduce (numbered), Expected vs Actual, Severity/Priority, Attachments (screens/video/logs), Links (Story/Test Case).

Defect description template (paste into a Jira “Description” field)
Environment:

-   Build:
-   OS/Browser:
-   Display:
-   Network:

Steps to Reproduce: 1) 2) 3)

## Expected:

## Actual:

## Severity/Priority:

Evidence:

-   attachments (screens/video/logs)

Links:

-   Story:
-   Test Case:

Tips
- One action per step; include repro rate (e.g., “3/3”).
- Add a verification comment when fixed (e.g., “Verified in 1.0.6 — PASS”).

---

## 2) Test management: TestRail vs Xray

TestRail (standalone)
- Dedicated test case and test plan management with runs/plans and rich execution reports.
- Integrates with Jira so failed tests can auto‑create/link Bugs.

Xray for Jira (inside Jira)
- Adds Test, Precondition, Test Execution, and Test Plan as Jira issue types.
- Native traceability: Requirements → Tests → Executions → Defects, all in Jira.

Rule of thumb
- Prefer TestRail for a dedicated test repository and external reports.
- Prefer Xray when the team already lives in Jira and wants everything in one system.

---

## 3) Technical writing and clear repro steps

Goal
- Write defects and test results so anyone can act without back‑and‑forth.

What good looks like
- Title: What/where/when.
- Environment: Build/OS/Device/Browser/Resolution/Network.
- Steps: Numbered, deterministic, one action per step.
- Expected vs Actual: One line each.
- Evidence: Screens/video (timestamps) and logs if available.
- Impact/Severity: Why it matters (blocker vs cosmetic).
- Links: Story and Test Case for traceability.

Example (good)
Title: Cart crashes when applying SAVE10 after removing an itemEnvironment:

-   Build: Web 1.0.5
-   OS/Browser: Windows 11, Chrome 127
-   Display: 1920×1080 @ 60 Hz
-   Network: Wi‑Fi

Steps:

1.  Add “Sofa A” and “Lamp B” to cart
2.  Go to Cart
3.  Remove “Lamp B”
4.  Enter “SAVE10” → Apply

Expected: 10% discount applies; totals recalc without errors Actual: Browser tab crashes (“Aw, Snap!”) Severity: Critical Evidence: video.mp4 (00:12–00:25), console.txt Links: Story WEB‑45; Test Case TC‑COUPON‑009
