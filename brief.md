# brief.md — what we gave the assistant (PA#2, ClubFlow)

Team: Đào Duy Long (24127443), Nguyễn Hữu Tường (24127584)
Assistants: Claude (claude.ai) for Member B; Kiro and Claude (claude.ai) for Member A.
---

## Member B — Nguyễn Hữu Tường (24127584)

### Prompt 1 — hand over the brief, the rules and the data

I am building a static responsive prototype for the ClubFlow project (course CSC13008, PA#2).
I attach three things:

1. `ClubFlow-final-project-brief.pdf`: the product brief, with the three screens and the "Fix these" list.
2. `PA2-rubric-responsive-prototype.pdf`: the rubric the pages are marked against.
3. My repository rules (`CLAUDE.md`) and the shared sample data (`CLUBFLOW-DATA.md`).

The main flow has three pages, in this order:
`index.html` (Create Recruitment Campaign) → `applications.html` (Application Review) → `schedule.html` (Interview Scheduling).
I build `applications.html` and the shared `css/styles.css`. My teammate builds `index.html` and `schedule.html` and reuses the same CSS.

The screens in the brief are a design to improve, not a picture to copy. Fix every item in the brief's "Fix these" list:
one timeline on all pages, the correct page title, a list and a detail panel that are both readable (no drawer covering the list),
counts that add up, a real conflict, interviewers who are not applicants, no "verified" wording, and no template footer.

### Prompt 2 — constraints (these are the things an assistant breaks when nobody says them)

**Stack**
- Static HTML and plain CSS only. One stylesheet: `css/styles.css`.
- No CSS framework, no build step, no CDN, no new dependency.
- No JavaScript at all, and certainly no JavaScript framework (React and Vue are PA#3). Every page must show all its content with JavaScript off.

**Spacing and design system**
- Spacing scale as custom properties on `:root`: `--space-1: 4px`, `--space-2: 8px`, `--space-3: 16px`, `--space-4: 24px`, `--space-5: 32px`, `--space-6: 48px`.
  Use `padding`, `margin` and `gap` from this scale only.
- Body text 16 px or larger. Body text and buttons must pass 4.5:1 contrast.
- Buttons and links that stand on their own are at least 44 px tall (`min-height: 44px`).
- No `!important`, no inline `style=""`, no `onclick`.

**Mobile first and breakpoints**
- Base styles are for 360 px. Add `@media (min-width: 768px)` and `@media (min-width: 1280px)`. Never `max-width` media queries.
- No fixed `width` that can be wider than 360 px: use `max-width`, `%`, `rem`. Images get `max-width: 100%`.
- No `overflow-x: hidden` on `html`, `body` or a wrapper to hide a layout problem.
- A table wider than the screen scrolls inside its own wrapper (`overflow-x: auto`, with an accessible name). The page never scrolls sideways. Long names and titles wrap.
- Application Review: the list and the detail panel are both always visible. At 360 and 768 px the panel sits below the list; at 1280 px they sit side by side.
  No modal, no `position: fixed` drawer, no `:target` tricks.

**Semantic rules**
- Landmarks: `<header>`, `<nav>`, `<main>`, `<footer>`. One `<h1>` per page, no skipped heading level.
- Every input, select and textarea has a visible `<label>` joined with `for` and `id`. A placeholder is not a label.
- Every `<img>` has `alt`. Status badges say the status in text, not only in colour.
- Going to another page is an `<a href>` or the submit button of a `<form action="...">`.
  An action that is not wired yet is a real `<button type="button">`, never `href="#"`, never a `<div>`.
- Tables use `<caption>` and `<th scope>`.

**Links**
- Relative file names only: `applications.html`, never `/applications.html`, never a folder, never `#`, never `href=""`.
- Main flow: Publish Campaign (form submit) → `applications.html`; Continue to Interview Scheduling → `schedule.html`.
  The navigation links the three pages.

**Content**
- Use the data in `CLUBFLOW-DATA.md` exactly. Do not invent other dates, counts or people. No lorem ipsum.
- Include at least one long item (a long position title) to show the layout survives it.
- Page text is English.
- Scope: no word "verified", no AI ranking, no dashboards, no audit trail, no chat, no payments, no multi-club, no sign-up or SSO.
  CV screening notes are for the Executive only.

### Prompt 3 — how "done" is checked

Do not call a page done until I can pass all of these:

1. At 360, 768 and 1280 px, in the DevTools console:
   `document.documentElement.scrollWidth > document.documentElement.clientWidth` prints `false`,
   and `[...document.querySelectorAll('body *')].filter(e => e.getBoundingClientRect().right > document.documentElement.clientWidth)` prints `[]`
   (anything inside a table's scrolling wrapper is fine).
   `document.documentElement.clientWidth` prints the width I set, so the viewport `<meta>` is present.
2. JavaScript turned off (DevTools → Ctrl+Shift+P → Disable JavaScript): the page still shows all its content.
3. The W3C checker (validator.w3.org/nu, File upload) shows 0 errors.
4. DevTools → Elements → Accessibility: landmarks present, one heading outline, a name on every control.
5. Tap targets at 360 px are at least 44 px tall.

### Prompt 4 — the page

Build `applications.html` and `css/styles.css` from the Screen 2 design and `CLUBFLOW-DATA.md`:
a static mobile-first Application Review page with the statistics, the search and filter form, the applications table (page 1 of 4, six rows),
and the detail panel for the open application, with no JavaScript. Keep the shared stylesheet generic enough that
`index.html` and `schedule.html` can reuse the header, navigation, footer, cards, badges, buttons and table styles.

### Follow-up questions

After Prompts 1–4 I only asked short follow-up questions in the same chat, in Vietnamese
(for example how to run the browser checks, and what to change after a check).
They add no new constraints, so they are not repeated here.
A review of my 360 px screenshot was done in a separate claude.ai chat (a different account).

---

## Member A — Đào Duy Long (24127443)

<!-- Long: paste the prompts you really sent for index.html and schedule.html here, in order. -->