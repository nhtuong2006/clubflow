# AI-LOG — ClubFlow PA#2
Team: Đào Duy Long (24127443) · Nguyễn Hữu Tường (24127584) · CSC13008 · 24KTPM1

---

## Member A — Đào Duy Long (24127443)

Tools: **Kiro** (agentic session in the repository: it reads and edits the files) and **Claude** (claude.ai chat: reviewer and prompt writer; I paste files into it, it does not touch the repository). "Checked by Kiro" lines are Kiro's own report; "By hand" lines are what I did myself.

### 2026-11-05 — index.html and css/campaign.css, first version (Screen 1)
Tool: Kiro.

Asked for: read CLAUDE.md, CLUBFLOW-DATA.md, css/styles.css, applications.html and screen1-create-campaign.png, then build the "Create Recruitment Campaign" page: static HTML, mobile first, semantic, no JavaScript, data exactly as in CLUBFLOW-DATA.md, the brief's "Fix these" items applied.

Kept: the app shell copied from applications.html; the two-section form; three position cards (quotas 3, 5, 2); `<form action="applications.html">` so Publish Campaign opens the next page; not-wired buttons as `type="button"`; spacing tokens from styles.css.

Changed: dates 02 Nov – 15 Nov 2026 (the image had 09/15 and 10/30); the word "verified" removed from the instructions; one-line footer (no © 2025, Privacy Policy, Terms of Service, Support Center); user "Phan Hải Yến / SAB Executive"; navigation reduced to the three pages; the long Vietnamese title added as an "Also known as" hint under the Content Team role title. 

Rejected: the sidebar navigation at 360 px (used a wrapping row instead); the breadcrumb (applications.html has none in the shared shell).

By hand: I ran the prompt in Kiro and read its report. Checked by Kiro: no `!important`, no `overflow-x: hidden`, no `href="#"`, no "verified", one `<h1>`, a `<label>` on every input.

### 2026-11-05 — Claude rendered index.html at 360, 768 and 1280 px and found six problems
Tool: Claude (claude.ai chat), as a reviewer.

Asked for: check whether index.html looks like the Screen 1 design and follows CLAUDE.md. I pasted index.html, campaign.css, styles.css and the design.

Kept: Claude's measurements: no horizontal scroll at the three widths, nothing past the right edge, no control under 44 px.

Changed: nothing in this step (review only). Claude found, and the 1280 px render compared with the design showed: (1) the `<fieldset>` kept the browser border, so each position card had a double frame; (2) the description and instruction textareas were half width at 768 px and above, the design has them full width; (3) there was no Publish Campaign button in the top bar; (4) the "Also known as" hint touched the next label; (5) `padding: 2px` on two badges was outside the spacing scale; (6) "Back to Campaigns" linked to index.html itself.

Rejected: fixing anything in this step (review only).

By hand: I pasted my files into Claude and read the report, then copied its fix prompt into Kiro (next entry).

### 2026-11-05 — Fix index.html and css/campaign.css (the six problems)
Tool: Kiro.

Asked for: fix the differences from the previous entry without rewriting the page.

Kept: all content and structure.

Changed: top Publish button `<button class="button button-primary" type="submit" form="campaign-form">` with `id="campaign-form"` on the form; fieldset reset (`border: 0; padding: 0; margin: 0; min-width: 0`); eight rows changed to `field-row field-row--full`, with the override in the 768 px media query; `margin-bottom: var(--space-3)` on `.position-fields-row`; the self-link "Back to Campaigns" removed; `padding: 2px var(--space-2)` replaced by `padding: 0 var(--space-2); min-height: var(--space-3)` on `.duration-badge` and `.openings-badge`; "organise" changed to "organize" to match the design.

Rejected: replacing the "Back to Campaigns" self-link with `href="#"`; a `#` link breaks the rubric's link check, so the link was removed instead.

By hand: I ran the prompt in Kiro and read its report. Checked by Kiro: `field-row--full` count is 8, `id="campaign-form"` present, no `2px` padding left, applications.html and styles.css unchanged.

### 2026-11-05 — schedule.html and css/schedule.css, first version (Screen 3)
Tool: Kiro.

Asked for: read CLAUDE.md, CLUBFLOW-DATA.md, css/styles.css, applications.html and screen3-interview-scheduling.png, then build the "Interview Scheduling" page: static, mobile first, 8-row table in a scrolling wrapper, conflict banner, parameters form, data exactly as in CLUBFLOW-DATA.md.

Kept: the app shell; four stat cards (8, 6, 2, 1); the conflict banner; the 8-row table in `.table-wrap` with `tabindex="0"` and a `<caption>`; `disabled` on Approve & Confirm Schedule with `aria-describedby` pointing to the reason.

Changed: interview date Sat 21 Nov 2026 (image: Oct 27); interviewers Lý Hoàng Nam, Đặng Ngọc Hân, Cao Thanh Tùng (image: names that were also applicants); 4 Proposed + 2 Conflict + 2 Unassigned = 8 (image: 6 + 1 + 2 = 9); a real conflict, Phạm Quốc Bảo (S20241280) booked twice at 10:20–10:40; Unassigned rows 7 and 8 show a reason and a `+ Assign Slot` button.

Rejected: the design image's date, names and counts, because they contradict CLUBFLOW-DATA.md and the brief's "Fix these" list.

By hand: I ran the prompt in Kiro and read its report. Checked by Kiro: all 8 applicants, the 3 interviewers, the conflict text and the unassigned reasons are present.

### 2026-11-05 — Kiro reviewed both pages against a nine-point checklist (review only)
Tool: Kiro.

Asked for: list problems only (overflow, fixed widths / `overflow-x: hidden` / `!important`, headings, labels and alt, links and `onclick`, 44 px targets, spacing tokens, contrast, W3C errors); fix nothing.

Kept: no changes.

Changed: nothing. Findings by reading the code: (A) `.status-tag { min-height: 28px }` is a raw px; (B) `.dept-icon` is 36 px; (C) `aria-label` on the three `<article>` elements is redundant with the `<h3>`; (D) `role="alert"` with `aria-live="polite"` conflicts. Needing a browser or colour tool: (E) `<input type="date">` width on phones; (F) contrast of the amber badges. D was fixed in the schedule.html entry below; ⟦A, B, C, E, F: "fixed in <entry name>" or "left as is because <reason>"⟧.

Rejected: fixing anything (review only).

By hand: I ran the prompt in Kiro and read its list.

### 2026-11-06 — Claude rendered schedule.html at 360, 768 and 1280 px (JavaScript off) and found eight problems
Tool: Claude (claude.ai chat), as a reviewer.

Asked for: "is it ok, what needs fixing". I pasted schedule.html and schedule.css.

Kept: Claude's measurements: no horizontal scroll at the three widths; nothing past the right edge outside the table wrapper; no control under 44 px; at 360 px the table is 866 px wide inside a 292 px wrapper, so it scrolls inside its own wrapper only; at 1280 px it fits. Kept all the data (4 + 2 + 2 = 8, the conflict, the legend).

Changed: nothing in this step (review only). Problems found by the 1280 px render and by reading the HTML: (1) Approve & Confirm Schedule, Save Changes and Regenerate Schedule each appeared twice; (2) the top Approve button wrapped onto two lines at 768 and 1280 px; (3) informational text was 12–14 px, CLAUDE.md says 16 px or larger (`.stat-note`, `.cell-reason`, `.legend-item`, `.showing-count`, `.avatar-sm`); (4) the Active Rooms `<input readonly>` cut its own text and dropped to a second row at 1280 px; (5) the Date cells wrapped to three lines; (6) redundant ARIA (`aria-live` with `role="alert"`, `aria-disabled` with `disabled`, `aria-readonly` with `readonly`); (7) a comment on row 3 said "Long Vietnamese name" but "Trần Gia Huy" is not long; (8) unused CSS.

Rejected: fixing anything in this step (review only).

By hand: I pasted my files into Claude and read the report, then copied its fix prompt into Kiro.

### 2026-11-06 — One stylesheet: merge campaign.css and schedule.css into css/styles.css
Tool: Claude (claude.ai chat) found the problem; Kiro did the merge.

Asked for: append both files to css/styles.css as sections 7 (index.html) and 8 (schedule.html) with comment headings, define duplicates once, reuse shared classes, remove the two extra `<link>` tags, do not edit applications.html or existing sections.

Kept: every existing rule in styles.css unchanged; `.badge`, `.card`, `.field`, `.table-wrap`, `.button*` reused, not copied.

Changed: `.sr-only`, `.status-tag`, `.status-tag-draft` defined once; in schedule.html `<dl class="schedule-stats">` became `<dl class="stats">` and the four cards got the shared `.stat` class; both extra `<link>` tags removed; the two old files deleted afterwards.

What went wrong first: the prompts I wrote with Claude's help for the first builds told Kiro to create `css/campaign.css` and `css/schedule.css`, but CLAUDE.md and PROTOTYPE.md say "one stylesheet: css/styles.css". The code contradicted our own rules. Claude noticed it when it read CLAUDE.md and PROTOTYPE.md.

Rejected: copying the `.stats` / `.stat` rules into section 8, because styles.css already has them.

By hand: I ran the prompt in Kiro and read its report. Checked by Kiro: all 97 class names used by index.html and schedule.html have a selector in styles.css; `.sr-only` appears once. Kiro said it did not open a browser. ⟦I opened applications.html at 360/768/1280 px after the merge and it ⟦looked the same / changed in …⟧⟧

### 2026-11-06 — Fix index.html, second pass
Tool: Kiro.

Asked for: compare index.html with the Screen 1 design and applications.html and fix the app shell, top action bar, fieldset reset, full-width rows, hint spacing, the self-link and spacing tokens, editing only index.html and section 7 of styles.css.

Kept: everything that already matched (most items had been fixed in the first fix pass).

Changed: css/styles.css section 7 only: `.field-hint` margin from `0` to `var(--space-1) 0 0`, so the long Vietnamese hint has a gap from the input above it.

Rejected: adding a "Back to Campaigns" link (it would point to index.html itself); adding Dashboard and Help (the shared shell in applications.html has neither).

By hand: I ran the prompt in Kiro and read its report. Checked by Kiro: the top Publish button and `id="campaign-form"`, the fieldset reset, no `href="#"`, no "verified", no `!important` in section 7. Kiro said it did not open a browser or run the W3C checker.

### 2026-11-06 — Fix schedule.html and section 8 of css/styles.css
Tool: Kiro.

Asked for: the nine fixes from the Claude review above.

Kept: all CLUBFLOW-DATA.md data (8 candidates, 4 + 2 + 2, the conflict between rows 5 and 6, the legend counts); the app shell already matched applications.html.

Changed: Export Timetable and Approve & Confirm Schedule moved into `.schedule-title-actions` in the title row and kept on one line; the duplicate action block inside the parameters form removed, so the bottom bar holds only "← Back to Applications"; Active Rooms shortened to "3 rooms: A, B, C" and its span class removed; a read-only Interviewers field added (Lý Hoàng Nam, Đặng Ngọc Hân, Cao Thanh Tùng); `class="cell-date"` with `white-space: nowrap` on the eight date cells; `.showing-count`, `.cell-reason`, `.table-count-note`, `.legend-item` now `1rem`, `.avatar-sm` and `.conflict-tag` now `0.875rem`; `aria-live`, `aria-disabled` and `aria-readonly` removed; both "+ Assign Slot" `aria-label`s now include the applicant name; the misleading "Long Vietnamese name" comment and the unused `.interviewer-conflict` rule removed; the 1280 px parameters grid changed from 4 to 3 columns.

Rejected: keeping `aria-live` next to `role="alert"` (redundant); keeping the duplicate Approve and Export buttons in the bottom bar.

By hand: I ran the prompt in Kiro and read its report. Checked by Kiro: a 37-point static script (no `!important`, `style=`, `onclick`, `href="#"`, "verified"; the ARIA changes; the text sizes; the counts). Kiro said it did not open a browser or run the W3C checker.

### 2026-11-06 — Browser checks of index.html and schedule.html (JavaScript off)
Tool: none (my own checks in Chrome DevTools).

Asked for: nothing; these are the checks from CLAUDE.md "How done is checked".

Kept: all results below.

Changed: ⟦what I fixed after these checks and which check found it, or "nothing; everything passed on the first run"⟧

Rejected: nothing from an assistant in this step (my own checks, no assistant output). A failing check is fixed in the layout, never hidden with `overflow-x: hidden`.

By hand: I ran every check myself on both pages.
- `document.documentElement.clientWidth` at 360 / 768 / 1280 px: ⟦360 / 768 / 1280⟧.
- `scrollWidth > clientWidth`: ⟦false at all three widths on both pages⟧.
- Elements past the right edge: ⟦[] on both pages; on schedule.html only items inside `.table-wrap`, if any⟧.
- JavaScript off (DevTools → Ctrl+Shift+P → Disable JavaScript): ⟦both pages show all their content⟧.
- W3C checker (validator.w3.org/nu, File upload): index.html ⟦0 errors⟧, schedule.html ⟦0 errors⟧; saved as checks/validator-index.png and checks/validator-schedule.png.
- Accessibility pane: ⟦landmarks present, one heading outline, a name on every control⟧.
- Tap targets at 360 px: ⟦none under 44 px⟧.
- Contrast of the amber badges in the DevTools colour picker: ⟦ratios⟧.
- Six screenshots (index and schedule at 360, 768, 1280) in screenshots/.

---

## Member B — Nguyễn Hữu Tường (24127584)

### 2026-11-05 — applications.html and css/styles.css, first version
Tool: Claude (claude.ai chat).

Asked for: turn the PA#1 Screen 2 design and CLUBFLOW-DATA.md into a static, mobile-first applications.html with a list, a detail panel, no JavaScript, and a shared css/styles.css.

Kept: semantic structure (header, nav, main, footer; one h1; h2/h3 outline; th scope="row" in the table); the table inside a scrolling wrapper; relative links (schedule.html, index.html); sample data from CLUBFLOW-DATA.md (24 applications, 12 + 8 + 4).

Changed: nothing in the first version; I committed the page and css/styles.css as they came (commit 3f6d78a). The spacing scale (4, 8, 16, 24, 32, 48 px) and the shared header, navigation, cards, badges, buttons and table styles were the ones my rules file asks for.

Rejected: the side drawer that covers the list, because the brief says the list and the details must both stay readable at every width with JavaScript off; the detail panel is a normal section beside the list at 1280 px and below it at 768/360 px.

By hand: I ran the checks below and decided what to fix.

### 2026-11-05 — Checks at 360, 768 and 1280 px (JavaScript off)
Tool: Claude, used as a guide for the checks.

Asked for: step-by-step instructions to check applications.html the way the marking script does.

Kept: all results. Viewport width (clientWidth = 360/768/1280), horizontal scroll (false), elements past the right edge ([]), tap targets at 360 px ([]), heading outline (one h1, no skipped level), landmarks, labels and alt, W3C checker (0 errors, saved in checks/validator-applications.png).

Changed: nothing in this step; all checks passed on the first run.

Rejected: nothing.

By hand: I ran every check myself in Chrome DevTools and took the 3 screenshots + the validator screenshot.

### 2026-11-05 — Long item broke the table at 360 px
Tool: Claude (claude.ai chat).

Asked for: a long English position title in one table row ("Communications and External Relations Coordinator for the New Student Welcome Program") to test that the layout survives it, as the rubric requires, and to wrap long text in table cells.

Kept: the long title in the Position column of the sixth row (Lê Văn Khôi), and the matching aria-label on that row's Review button.

Changed: td, th { overflow-wrap: anywhere; } was added to css/styles.css (commit 910eb27). It landed inside the @media (min-width: 1280px) block, so it applies from 1280 px only. At 360 px the table is wider than the screen and scrolls inside its own wrapper; the page itself does not scroll sideways (scrollWidth > clientWidth prints false, the past-the-right-edge list is []).

Rejected: overflow-x: hidden on the table or the page, because it would hide the scrolling instead of fixing it.

By hand: I re-ran the two Console lines at 360, 768 and 1280 px, re-ran the W3C checker and retook the screenshots.
### 2026-11-05 — Claude misread my screenshot
Tool: Claude (claude.ai chat, in a different account from the chat above).

Asked for: a check of a 360 px screenshot of the new long row.

Kept: Claude's second answer, after I sent the real HTML.

Changed: Claude first said the long title was in the wrong column (a misplaced <td>). I opened the code, found the row had the correct 5 cells, and sent the file; Claude then agreed the structure was valid and that the long title simply was not in the file yet.

Rejected: the first diagnosis (an extra/empty <td>), because the real code did not have it.

By hand: I compared the screenshot with the source before changing anything.