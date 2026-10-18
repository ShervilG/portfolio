# CLAUDE.md

Personal portfolio site for **Shervil Gupta**, Lead Member of Technical Staff at Salesforce (working on Slack).

## Project overview

- A static site of three files: `index.html` (markup), `style.css` (all styles) and `script.js` (theme toggle and footer year). `script.js` is loaded in `<head>` without `defer` on purpose so the saved theme applies before first paint.
- No build step, no framework, no package manager, no dependencies. Keep it that way unless asked.
- To preview, open `index.html` in a browser, or run `python3 -m http.server` and visit `http://localhost:8000`.

## Page structure

Sections in order, each linked from the sticky header nav:

1. **Hero** (`#home`): eyebrow with the current role, the "Building things that scale." heading, a short intro and CTA buttons.
2. **About** (`#about`): a short bio paragraph.
3. **Experience** (`#experience`): `.company` blocks (logo + company name, then its `.role` entries), newest first.
4. **Contact** (`#contact`): `.contact-box` with Email, LinkedIn and GitHub buttons.
5. **Footer**: copyright plus social links.

There is intentionally **no projects section** (it was removed in `fefcb18`). Don't add one back unless asked.

## Content facts (keep consistent everywhere)

- Name: Shervil Gupta
- Current role: Lead Member of Technical Staff, Salesforce · Slack (Aug 2026 – Present)
- Email: wintergpt45@gmail.com
- GitHub: https://github.com/ShervilG
- LinkedIn: https://www.linkedin.com/in/shervil-gupta-098216164/

Career history, newest first: Salesforce/Slack (Lead MTS, Senior MTS) → Microsoft (SWE II, SWE) → Google → DP World → OYO (SDE, Intern).

When the role changes, update **all** of these spots together: the `<title>`, the `<meta name="description">`, the hero eyebrow, the hero intro, the About text and the top experience entry.

## Adding an experience entry

Experience is grouped by company, newest company first. Add a new role to the top of its company's `.company` block, or copy a whole block for a new company (the logo is an inline SVG or a text badge in `.company-logo`):

```html
<div class="company">
  <div class="company-header">
    <span class="company-logo" title="Company">…logo…</span>
    <h3>Company</h3>
  </div>
  <div class="role">
    <div class="role-head">
      <h4>Role Title</h4>
      <time>Mon YYYY – Present</time>
    </div>
    <p class="role-team">Team</p>
    <ul class="experience-details">
      <li>Impact-focused bullet with a measurable result.</li>
    </ul>
  </div>
</div>
```

- Recent or major roles get an `<ul class="experience-details">` bullet list. Older roles use a single `<p class="role-desc">` summary.
- Dates use the format `Mon YYYY – Mon YYYY` with an en dash (`–`). The current role ends in `Present`.
- When a new role is added, change the previous role's `Present` to its end date.

## Styling conventions

- Dark theme driven by CSS variables in `:root`: `--bg`, `--surface`, `--text`, `--muted`, `--accent` (purple `#a78bfa`), `--border`. Use these variables rather than hard-coding new colors.
- Layout width comes from `.container` (`min(100% - 40px, 1000px)`).
- The single responsive breakpoint is `@media (max-width: 650px)`. Check that changes still work at phone width.
- Buttons are `.button`, with `.button.primary` for the main CTA.
- External links use `target="_blank" rel="noopener noreferrer"`.

## Writing style

- First person, concise and professional.
- Bullets lead with a verb ("Led", "Built", "Reduced") and include concrete impact (e.g. "reducing infrastructure costs by 50%").
- Don't invent achievements, metrics, employers or dates. Ask if something is unclear.
