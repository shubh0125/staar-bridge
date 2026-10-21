# Staarbridge website

A simple website for Staarbridge: financial and legal literacy for underprivileged kids. Plain HTML and CSS, no build step. Open any `.html` file in a browser to see it.

Please read `rules.md` before making changes.

## Pages

| File | What it is |
| --- | --- |
| `index.html` | Home page |
| `about.html` | Our Mission |
| `blog.html` | Blog: picks between the Finance and Law sections |
| `finance.html` | Finance lessons |
| `law.html` | Law lessons |
| `finance-day-1.html` … `finance-day-5-part-2.html` | One page per finance lesson (Day 1 to Day 5, Part 2) |
| `law-lesson-1.html` … `law-lesson-5.html` | One page per law lesson |
| `contact.html` | Contact details |
| `donate.html` | Donation buttons (Stripe Payment Links) |
| `css/styles.css` | All styles. Colors and fonts are at the top. |
| `fonts/` | The two site fonts (Fraunces for headings, Plus Jakarta Sans for text), stored here so nothing loads from other sites |

## Still to add

- [x] **Logo.** The header uses `images/logo-mark.png`, the star and bridge cut out of `images/staarbridge_logo.jpeg` (the full logo, kept as the original).
- [x] **Photos.** About, Donate, and the Finance/Law cards all have photos. The home page hero is drawn with CSS (soft gradient, dot pattern, faint logo), so it needs no photo.
- [x] **Lesson content.** 6 finance and 5 law lessons, copied from the team Google Doc.
- [ ] **Stripe Payment Links** on `donate.html`. Shubh adds these. Until then the page shows a "Coming Soon" box, and the amount buttons are hidden inside an HTML comment in `donate.html` (see the "DONATION BUTTONS" note for how to switch them back on).

## How to add a lesson

Each lesson is its own page.

1. Copy an existing lesson page (for example `law-lesson-5.html`) and rename it (`law-lesson-6.html`).
2. In the new file, change the `<title>`, the label (`Lesson 6`), the `<h1>` title, the lesson text, and the Previous/Next links at the bottom.
3. In `finance.html` or `law.html`, copy one `<li>` … `</li>` lesson card, paste it after the last one, and point it at the new file.
4. Add a Next link to the lesson that used to be last.
5. Update the lesson count ("5 lessons") on `index.html` and `blog.html`.

Small fixes to existing lessons: open the lesson page and edit the text between `<p>` and `</p>`.

## How to add a photo

1. Shrink it to under ~500 KB and save it as `.jpg` or `.webp` in `images/`.
2. Replace the matching `<div class="image-slot" …>` line with
   `<img src="images/your-photo.jpg" alt="Short description of the photo">`.
