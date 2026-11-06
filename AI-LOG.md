## Member B — Nguyễn Hữu Tường (24127584)

### 2026-11-05 — applications.html and css/styles.css, first version
Tool: Claude (claude.ai chat).

Asked for: turn the PA#1 Screen 2 design and CLUBFLOW-DATA.md into a static, mobile-first applications.html with a list, a detail panel, no JavaScript, and a shared css/styles.css.

Kept: semantic structure (header, nav, main, footer; one h1; h2/h3 outline; th scope="row" in the table); the table inside a scrolling wrapper; relative links (schedule.html, index.html); sample data from CLUBFLOW-DATA.md (24 applications, 12 + 8 + 4).

Changed: adjusted the shared spacing scale in `css/styles.css` to match the exact requirements of PA#2, ensuring consistency for the upcoming pages.

Rejected: the side drawer that covers the list, because the brief says the list and the details must both stay readable at every width with JavaScript off; the detail panel is a normal section beside the list at 1280 px and below it at 768/360 px.

By hand: I ran the checks below and decided what to fix.

### 2026-11-05 — Checks at 360, 768 and 1280 px (JavaScript off)
Tool: Claude (same chat), used as a guide for the checks.

Asked for: step-by-step instructions to check applications.html the way the marking script does.

Kept: all results. Viewport width (clientWidth = 360/768/1280), horizontal scroll (false), elements past the right edge ([]), tap targets at 360 px ([]), heading outline (one h1, no skipped level), landmarks, labels and alt, W3C checker (0 errors, saved in checks/validator-applications.png).

Changed: nothing in this step; all checks passed on the first run.

Rejected: nothing.

By hand: I ran every check myself in Chrome DevTools and took the 3 screenshots + the validator screenshot.

### 2026-11-05 — Long item broke the table at 360 px
Tool: Claude (same chat).

Asked for: a long English position title in one table row ("Communications and External Relations Coordinator for the New Student Welcome Program") to test that the layout survives it, as the rubric requires.

Kept: the long title in the Position column, and the matching aria-label on that row's Review button.

Changed: at 360 px the long title pushed the row wider than the viewport. I added `td, th { overflow-wrap: anywhere; }` to css/styles.css. After that the text wraps inside its cell and the page no longer overflows.

Rejected: overflow-x: hidden, because it hides the problem instead of fixing it, which would fail the marker's check.

By hand: I re-ran the two Console lines at 360 px (false and []), re-ran the W3C checker and retook the screenshots.

### 2026-11-05 — Claude misread my screenshot
Tool: Claude (same chat).

Asked for: a check of a 360 px screenshot of the new long row.

Kept: Claude's second answer, after I sent the real HTML.

Changed: Claude first said the long title was in the wrong column (a misplaced <td>). I opened the code, found the row had the correct 5 cells, and sent the file; Claude then agreed the structure was valid and that the long title simply was not in the file yet.

Rejected: the first diagnosis (an extra/empty <td>), because the real code did not have it.

By hand: I compared the screenshot with the source before changing anything.