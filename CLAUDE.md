# CLAUDE.md — rules for the assistant (PA#2, ClubFlow)

Team: Đào Duy Long (24127443), Nguyễn Hữu Tường (24127584) · CSC13008 · 24KTPM1
Product: ClubFlow, a club recruitment tool. The Executive's main flow has three screens. Source: `docs/clubflow-brief.pdf` (screens in `docs/pa1/*.png` are a design to improve, not a picture to copy). All sample data is in `CLUBFLOW-DATA.md`: use it exactly, on every page.

## Stack
- Static HTML and plain CSS. One stylesheet: `css/styles.css`. No CSS framework, no build step, no CDN.
- Pages open straight from the folder (`index.html`), with no server and no network.
- No JavaScript. Every page must show all its content with JavaScript off.
- Page text is English; code, comments, file names and docs are English.

## Pages (the main flow, in order)
1. `index.html` — Create Recruitment Campaign
2. `applications.html` — Application Review
3. `schedule.html` — Interview Scheduling

## Links and controls
- Moving to another page is an `<a href="applications.html">` or the submit button of a `<form action="applications.html">`. Relative file names only: never `/applications.html`, never a folder, never `#`, never `href=""`.
- Main flow: Publish Campaign (submit of the campaign form) → `applications.html`; Continue to Interview Scheduling → `schedule.html`. The sidebar links Recruitment Campaigns, Applications and Interview Schedule open the three pages.
- A control that is not wired yet (Save as Draft, Preview Campaign, Export, Approve & Confirm Schedule, Edit, Resolve, + Assign Slot, Dashboard, Help) is a real `<button type="button">` with a visible label. Never `href="#"`, never `onclick`.

## Design system (use only these)
- Spacing scale as custom properties on `:root`: `--space-1: 4px`, `--space-2: 8px`, `--space-3: 16px`, `--space-4: 24px`, `--space-5: 32px`, `--space-6: 48px`. Use `padding`, `margin` and `gap` from this scale only.
- Mobile first: base styles are for 360 px. Add `@media (min-width: 768px)` and `@media (min-width: 1280px)`. Never `max-width` media queries.
- Body text 16 px or larger. Body text and buttons contrast at least 4.5:1.
- Buttons and links that stand on their own are at least 44 px tall (`min-height: 44px`).
- App shell on every page: `<header>` with the page title, `<nav>` with the three pages (a sidebar at 1280 px, a row or stack at 360 px), `<main>`, and a `<footer>` with one line of text only. The footer has no Privacy Policy, Terms of Service, Support Center or "© 2025".
- Each page has one clearly most important thing (campaign form; the application list with its detail panel; the schedule table).

## Layout rules for the hard parts
- Application Review: the list and the application detail panel are both always visible, with no overlay and no covering. At 360 px the detail panel sits below the list; at 1280 px they sit side by side. Do not use a modal, `position: fixed` drawer, or `:target` tricks.
- Tables (applications, schedule): a table that is wider than the screen scrolls inside its own wrapper only (`overflow-x: auto` on the wrapper, with an accessible name). The page itself never scrolls sideways. A long name wraps.

## Semantic rules
- Landmarks: `<header>`, `<nav>`, `<main>`, `<footer>`. One `<h1>` per page and no skipped heading level.
- Every input, select and textarea has a visible `<label>` joined with `for` and `id`. A placeholder is not a label. Radio and checkbox groups use `<fieldset>` and `<legend>`.
- Every `<img>` has `alt` (decorative: `alt=""`). Status badges say the status in text, not only in colour.
- Never a `<div>` or `<span>` as a button. Tables use `<th scope>` and a `<caption>`.

## Scope: what the sample data must not say
- No word "verified" anywhere (no "Verified Student", "100% verified", "Verified Attachments"). University account verification is Not Building.
- No AI ranking, dashboards, audit trail, chat, payments, multi-club, sign-up or SSO.
- CV screening notes are for the Executive only; no page for applicants or interviewers appears in these three screens.

## Never
- Never `!important`.
- Never a fixed `width` that can be wider than 360 px; use `max-width`, `%`, `rem`. Images get `max-width: 100%`.
- Never `overflow-x: hidden` on `html`, `body` or a wrapper to hide a layout problem.
- Never a JavaScript framework, a new dependency, inline `style=""` attributes or `onclick`.
- Never lorem ipsum, and never change the numbers in `CLUBFLOW-DATA.md` on one page only.
- Never touch files outside the page you were asked to change (and `css/styles.css`), and never rename pages.

## How done is checked
- At 360, 768 and 1280 px: `document.documentElement.scrollWidth > document.documentElement.clientWidth` prints `false`, and `[...document.querySelectorAll('body *')].filter(e => e.getBoundingClientRect().right > document.documentElement.clientWidth)` prints `[]` (anything inside a table's scrolling wrapper is fine).
- JavaScript off (DevTools → Ctrl+Shift+P → Disable JavaScript): every page still shows all its content.
- The W3C checker (validator.w3.org/nu, File upload) shows 0 errors for every page.
- DevTools → Elements → Accessibility: landmarks, one heading outline, a name on every control.
