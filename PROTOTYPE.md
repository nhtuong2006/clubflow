# PROTOTYPE.md — PA#2 responsive prototype (ClubFlow)

## 1. Team
- Đào Duy Long — 24127443
- Nguyễn Hữu Tường — 24127584

## 2. How to open it
Open `index.html` from the folder (double-click it or drag it into a browser). It does not need a network connection: plain CSS in `css/styles.css`, no framework from a CDN, no JavaScript.

## 3. Screens
| File | Screen it comes from (the ClubFlow brief) | What the user does there | Where its links go |
|---|---|---|---|
| `index.html` | Create Recruitment Campaign (`docs/pa1/screen1-create-campaign.png`) | the Executive enters the campaign, its dates, and the departments and positions | "Publish Campaign" (submit of `<form action="applications.html">`) → `applications.html`; sidebar links open the three pages |
| `applications.html` | Application Review (`docs/pa1/screen2-application-review.png`) | reads the applications and one application's details, then shortlists or rejects | "Continue to Interview Scheduling" → `schedule.html`; sidebar links open the three pages |
| `schedule.html` | Interview Scheduling (`docs/pa1/screen3-interview-scheduling.png`) | checks the proposed schedule, its conflict and unassigned applications | sidebar links open the three pages <<CONFIRM: any other link, e.g. back to Applications>> |

## 4. Changed since the brief
<<CONFIRM AFTER BUILDING. List every difference from the three ClubFlow screens in `docs/pa1/` (unchanged) and why. Go through the brief's "Fix these" list one by one and write what you did for each: one timeline (open 02 Nov, close 15 Nov, interviews 21 Nov 2026); the Application Review title; list and detail panel both readable with no overlay; screen 3 counts that add up (4 + 2 + 2 = 8) and a real conflict; interviewers who are not applicants; no "verified" wording; template footer removed. Then add the layout changes you made for 360 px. Only write what is true.>>

## 5. Not wired yet
<<CONFIRM AFTER BUILDING. Likely entries: Save as Draft, Preview Campaign, Add Position, Search and filters, pagination, CSV export, Shortlist and Reject, Edit / Resolve / + Assign Slot, Regenerate Schedule, Export Timetable, Approve & Confirm Schedule, Dashboard and Help.>>

## 6. CSS
Plain CSS, one file `css/styles.css`, no framework. Spacing scale (custom properties on `:root`): 4, 8, 16, 24, 32, 48 px. Mobile first: base styles for 360 px, `min-width` breakpoints at 768 px and 1280 px. Body text 16 px; buttons and stand-alone links at least 44 px tall.
