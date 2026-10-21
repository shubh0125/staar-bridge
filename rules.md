# Project Guidelines — Sister's Website

These guidelines are for anyone (human or AI) making changes to this site. Read this file before editing anything.

## What this site is

A small static website with a few content pages and a donation page.
- Domain: `[yourdomain.com]` (registered at GoDaddy)
- Hosting: Netlify, auto-deployed from the GitHub repo
- Maintainers: Shubh (owner/reviewer) and his sister (content editor)

## Core principles

1. **Keep it simple.** Plain HTML, CSS, and minimal vanilla JavaScript. No frameworks, no build step, no npm packages unless Shubh explicitly approves.
2. **No backend.** No servers, databases, serverless functions, or forms that store data.
3. **No secrets, ever.** Nothing in this repo should be private. No API keys, passwords, tokens, or `.env` files.
4. **Easy for a non-developer to edit.** Content should be readable and easy to find in the HTML. Prefer clear structure over clever code.

## File structure

```
/
├── index.html          # Home page
├── about.html          # About page
├── donate.html         # Donation page
├── [other-page].html   # Add new pages at the root
├── css/
│   └── styles.css      # All styles live here — one stylesheet
├── js/
│   └── main.js         # Only if needed (e.g. mobile menu toggle)
├── images/             # Optimized images (see Images below)
├── CLAUDE.md           # This file
└── README.md
```

- Every page shares the same header, navigation, and footer. When adding a page, copy the header/nav/footer from an existing page and add the new page to the nav on **every** page.
- Use relative links (`about.html`, not `/about` or full URLs) for internal pages.

## Donation page rules (important)

- Donations use **Stripe Payment Links** only (plus optional Venmo / Cash App links).
- Each donation amount is a plain link/button pointing to its Stripe Payment Link:
  ```html
  <a class="donate-btn" href="https://buy.stripe.com/XXXXXXXX" target="_blank" rel="noopener">$5</a>
  ```
- Current amounts: `$1, $5, $10, $25, $50, $100` + a "Custom amount" link.
- **Never** add Stripe API keys (`sk_live_...`, `sk_test_...`, `pk_...`), Stripe.js, or any embedded card form. Payment Links need no keys.
- **Never** change a donation URL unless Shubh provides the new link. Do not invent or guess payment links.
- Venmo link format (optional): `https://venmo.com/?txn=pay&recipients=USERNAME&amount=5&note=Donation`
- Cash App link format (optional): `https://cash.app/$CASHTAG/5`

## Styling

- All styles go in `css/styles.css`. No inline styles, no extra stylesheets.
- Define colors and fonts as CSS variables at the top of `styles.css` and reuse them.
- Mobile-first: the site must look good on a phone (test at ~375px wide). No horizontal scrolling.
- Keep the design consistent across pages — same fonts, colors, spacing, and button styles.

## Images and video

- Put images in `/images/`. Keep each image under ~500 KB (resize/compress before adding). Prefer `.webp` or `.jpg`.
- Every `<img>` needs a meaningful `alt` attribute.
- **Do not commit video files.** Upload videos to YouTube (unlisted is fine) or Vimeo and embed them:
  ```html
  <div class="video">
    <iframe src="https://www.youtube-nocookie.com/embed/VIDEO_ID" title="Describe the video" allowfullscreen loading="lazy"></iframe>
  </div>
  ```

## Accessibility and quality

- Use semantic HTML: `<header>`, `<nav>`, `<main>`, `<footer>`, one `<h1>` per page, headings in order.
- Every page needs a unique `<title>` and `<meta name="description">`.
- Buttons and links must have readable text and enough color contrast.
- External links open in a new tab with `target="_blank" rel="noopener"`.

## Workflow (how changes go live)

1. **Never commit directly to `main`.** Create a branch for each change (e.g. `update-about-text`).
2. Open a Pull Request. Netlify automatically creates a **preview link** for the PR — check the change there.
3. Shubh reviews and merges. Merging to `main` deploys to the live site automatically.
4. Keep each PR small and focused on one change.

## Instructions for Claude

When asked to make a change:
- Make the smallest change that does the job. Don't refactor or restyle things that weren't asked about.
- Keep everything consistent with existing pages (copy existing patterns).
- Do not add dependencies, frameworks, build tools, analytics, trackers, or third-party scripts without explicit approval.
- Do not touch donation links unless explicitly asked and given the exact new URL.
- If a request conflicts with these guidelines (e.g. "add a contact form that saves submissions"), stop and explain the conflict and a simple alternative instead of doing it.
- After changes, briefly list which files were changed and what to check on the preview link.
- Write content in a warm, clear, simple tone unless told otherwise.