# PROTOTYPE.md — PA#2 responsive prototype (ClubFlow)

## 1. Team

- Đào Duy Long — 24127443
- Nguyễn Hữu Tường — 24127584

## 2. How to open it

Open `index.html` from the folder (double-click it or drag it into a browser). It does not need a network connection: plain CSS in `css/styles.css`, no framework from a CDN, no JavaScript.

## 3. Screens

| File                | Screen it comes from (the ClubFlow brief)                            | What the user does there                                                         | Where its links go                                                                                                           |
|---------------------|----------------------------------------------------------------------|----------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
| `index.html`        | Create Recruitment Campaign (`docs/pa1/screen1-create-campaign.png`) | the Executive enters the campaign, its dates, and the departments and positions  | "Publish Campaign" (submit of `<form action="applications.html">`) → `applications.html`; navigation links open the three pages |
| `applications.html` | Application Review (`docs/pa1/screen2-application-review.png`)       | reads the applications and one application's details, then shortlists or rejects | "Continue to Interview Scheduling" → `schedule.html`; navigation links open the three pages                                  |
| `schedule.html`     | Interview Scheduling (`docs/pa1/screen3-interview-scheduling.png`)   | checks the proposed schedule, its conflict and the unassigned applications       | navigation links open the three pages <!-- CONFIRM with Long: any other link, e.g. back to Applications -->                  |

## 4. Changed since PA#1

The PA#1 screens are the three screens of the ClubFlow brief, kept unchanged in `docs/pa1/`.

### The brief's "Fix these" list

| Problem in the brief | What we did | Page |
|---|---|---|
| Dates do not fit together | One timeline on all three pages: applications open Mon 02 Nov 2026, close Sun 15 Nov 2026, interviews on Sat 21 Nov 2026. | all |
| Screen 2 has the wrong page title | The heading and the `<title>` are "Application Review". | `applications.html` |
| The drawer covers the list | No drawer. The list and the detail panel are two normal sections: side by side at 1280 px, the panel below the list at 360 and 768 px. Works with JavaScript off. | `applications.html` |
| Counts on Screen 3 do not add up | 8 shortlisted = 4 Proposed + 2 Conflict + 2 Unassigned. | `schedule.html` <!-- CONFIRM --> |
| The conflict is not a conflict | A real one: Phạm Quốc Bảo is booked for two interviews at 10:20–10:40 (Design & Media and Event Operations). | `schedule.html` <!-- CONFIRM --> |
| Sample people overlap | Interviewers (Lý Hoàng Nam, Đặng Ngọc Hân, Cao Thanh Tùng) are different people from the applicants. | `schedule.html`, `applications.html` <!-- CONFIRM --> |
| "Verified" contradicts the scope | The word "verified" appears nowhere. "100% verified" and "Verified Attachments" are gone; the CV section is just "CV". | all |
| The footer is template text | One line: "ClubFlow · SAB Recruitment 2026 · Student project for CSC13008." No "© 2025", Privacy Policy, Terms of Service or Support Center. | all |

### Other differences on the pages

- **Sample data.** All pages use the shared `CLUBFLOW-DATA.md` (24 applications from 21 students: 12 Pending, 8 Shortlisted, 4 Rejected), so the three pages agree. The Executive is now Phan Hải Yến; the open application is Vũ Mai Linh.
- **Application list (`applications.html`).**
  - The student ID moved under the applicant's name instead of its own column, so the table is narrower at 360 px.
  - The table sits in its own scrolling wrapper; the page never scrolls sideways.
  - The checkbox column is dropped (there is no bulk action in this prototype).
  - The status filter and visible labels on every filter field are added.
  - Previous / Next are real buttons.
  - One row has a very long position title to test the layout; it wraps inside its cell.
- **Statistics.** Four cards (total, pending, shortlisted, rejected). The "average triage time" and "100% verified" cards are removed because they are outside the scope or not in the data.
- **Detail panel.** The panel heading is "Application details". GPA is dropped, and the panel shows the same facts as in `CLUBFLOW-DATA.md`.
- **Layout for 360 px.** Base styles are for 360 px, with `min-width` breakpoints at 768 and 1280 px; buttons and stand-alone links are at least 44 px tall.
- <!-- CONFIRM with Long: layout changes on index.html and schedule.html (position cards in one column at 360 px, schedule table in a scrolling wrapper). Only write what is true. -->

## 5. Not wired yet

These controls are real `<button type="button">` elements with a visible label. They do nothing yet and are left for later milestones.

- `index.html`: Save as Draft, Preview Campaign, Add Position.
- `applications.html`: Search and the Position and Status filters, Previous / Next (pagination), Review (the panel always shows the same application), View CV, Download, Shortlist Candidate, Reject, Close, saving the internal note, CSV export.
- `schedule.html`: Regenerate Schedule, Export Timetable, Edit, Resolve, + Assign Slot, Approve & Confirm Schedule (disabled while a conflict or an Unassigned row remains), Save Changes.
- All pages: Dashboard and Help <!-- CONFIRM: only if these controls exist on the pages -->.

## 6. CSS

Plain CSS, one file `css/styles.css`, no framework. Spacing scale (custom properties on `:root`): 4, 8, 16, 24, 32, 48 px. Mobile first: base styles for 360 px, `min-width` breakpoints at 768 px and 1280 px. Body text 16 px; buttons and stand-alone links at least 44 px tall. No `!important`.