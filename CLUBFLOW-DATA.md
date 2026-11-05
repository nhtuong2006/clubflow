# CLUBFLOW-DATA.md — one set of sample data for all three pages

Use these facts on every page. Do not invent other dates, counts or people.

## One timeline (fixes the date problem in the brief)
- Campaign: **SAB Recruitment 2026**, host club **Student Activities Board (SAB)**; Executive: **Phan Hải Yến**, SAB Executive (use "Executive" role label).
- Applications open **Mon 02 Nov 2026**, close **Sun 15 Nov 2026** (14 days).
- Interview day (the only one): **Sat 21 Nov 2026**, 09:00–12:00, 20 minutes per session, rooms A, B, C.

## Screen 1 — Create Recruitment Campaign (status: Draft)
Positions (3 positions, 10 openings):
| Role | Department | Quota |
|---|---|---|
| Content Team Specialist | Media & Communications | 3 |
| Event Operations Coordinator | Logistics & Planning | 5 |
| Media & Visual Designer | Creative Arts | 2 |
Instructions to candidates: complete the form, submit a motivation statement (max 300 words), and attach your CV as a PDF (max 5 MB). A very long item for the layout test: role "Điều phối viên Truyền thông và Quan hệ Đối ngoại cho Chương trình Chào đón Tân sinh viên" (Content Team Specialist's long alternative title).

## Screen 2 — Application Review (campaign is published, closed on 15 Nov)
- **24 applications** from **21 students** (3 students applied for 2 positions). Status: **12 Pending**, **8 Shortlisted**, **4 Rejected** (12 + 8 + 4 = 24).
- List shows page 1 of 4, 6 per page (24 items). Rows (applicant, student ID, position, submitted, status):
  1. Vũ Mai Linh · S20240512 · Content Team · 03 Nov · Pending  ← the one open in the detail panel
  2. Nguyễn Minh Anh · S20241088 · Content Team · 04 Nov · Shortlisted
  3. Lê Thu Hà · S20240954 · Content Team · 04 Nov · Shortlisted
  4. Phạm Quốc Bảo · S20241280 · Design & Media · 05 Nov · Shortlisted
  5. Phạm Quốc Bảo · S20241280 · Event Operations · 05 Nov · Shortlisted  (same student, two separate applications)
  6. Lê Văn Khôi · S20240677 · Event Operations · 06 Nov · Rejected
- Detail panel (Vũ Mai Linh): email mai.linh.vu@student.example, phone 0912 345 678, Year 2, Business IT; position Content Team, first choice; statement of purpose (142 / 300 words, 2–3 realistic sentences); CV `VuMaiLinh_CV_2026.pdf`, 1.4 MB, uploaded 03 Nov 2026; internal notes box ("visible only to the Executive"); timeline: Submitted 03 Nov 2026 → Awaiting review; buttons Reject, Close (not wired) and Shortlist Candidate (not wired).
- "Continue to Interview Scheduling" → `schedule.html` (there are 8 Shortlisted).

## Screen 3 — Interview Scheduling (status: Draft schedule)
Interviewers (they are NOT applicants): **Lý Hoàng Nam**, **Đặng Ngọc Hân**, **Cao Thanh Tùng**. Rooms: A (Media Lab), B (Conference Room), C (Studio).
Qualified: Content → Nam, Hân · Event Operations → Tùng, Nam · Design & Media → Hân, Tùng.

Date: Sat 21 Nov 2026. The 8 shortlisted applications:
| # | Applicant (ID) | Position | Slot | Interviewer | Room | Status |
|---|---|---|---|---|---|---|
| 1 | Nguyễn Minh Anh (S20241088) | Content Team | 09:00–09:20 | Lý Hoàng Nam | Room A | Proposed |
| 2 | Lê Thu Hà (S20240954) | Content Team | 09:20–09:40 | Lý Hoàng Nam | Room A | Proposed |
| 3 | Trần Gia Huy (S20241102) | Event Operations | 09:00–09:20 | Cao Thanh Tùng | Room B | Proposed |
| 4 | Đỗ Đức Thắng (S20240741) | Event Operations | 09:20–09:40 | Cao Thanh Tùng | Room B | Proposed |
| 5 | Phạm Quốc Bảo (S20241280) | Design & Media | 10:20–10:40 | Đặng Ngọc Hân | Room C | Conflict |
| 6 | Phạm Quốc Bảo (S20241280) | Event Operations | 10:20–10:40 | Cao Thanh Tùng | Room B | Conflict |
| 7 | Bùi Quang Huy (S20240321) | Design & Media | — | — | — | Unassigned (no shared free time with a qualified interviewer) |
| 8 | Hoàng Thảo Vy (S20240812) | Content Team | — | — | — | Unassigned (no free room in the time window for Nam or Hân) |

Counts (they must add up): **8** shortlisted · **4 Proposed + 2 Conflict + 2 Unassigned = 8** rows · 6 sessions have a slot (4 + 2). The one conflict: the same student, Phạm Quốc Bảo, is booked for two interviews at 10:20–10:40 (rows 5 and 6). No other rows overlap. Banner: "1 conflict affects 2 interviews: Phạm Quốc Bảo is booked twice at 10:20–10:40." Approve & Confirm Schedule is disabled while a conflict or an Unassigned row remains.
