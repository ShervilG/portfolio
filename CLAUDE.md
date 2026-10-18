# CLAUDE.md

Personal portfolio site for **Shervil Gupta**, Lead Member of Technical Staff at Salesforce (working on Slack).

## Project overview

- The whole site is one static file: `index.html`. It has inline `<style>` and a tiny inline `<script>` that fills in the footer year.
- No build step, no framework, no package manager, no dependencies. Keep it that way unless asked.
- To preview, open `index.html` in a browser, or run `python3 -m http.server` and visit `http://localhost:8000`.

## Page structure

Sections in order, each linked from the sticky header nav:

1. **Hero** (`#home`): eyebrow with the current role, the "Building things that scale." heading, a short intro and CTA buttons.
2. **About** (`#about`): a short bio paragraph.
3. **Experience** (`#experience`): `.experience-item` blocks, newest first.
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

Copy this pattern and put it at the top of `#experience`:

```html
<div class="experience-item">
  <div>
    <h3>Role Title</h3>
    <p>Company · Team</p>
    <ul class="experience-details">
      <li>Impact-focused bullet with a measurable result.</li>
    </ul>
  </div>
  <time>Mon YYYY – Present</time>
</div>
```

- Recent or major roles get an `<ul class="experience-details">` bullet list. Older roles use a single `<p>` summary.
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
