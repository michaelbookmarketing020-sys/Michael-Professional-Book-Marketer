# Michael | Professional Book Marketing Website

A premium, editorial-inspired, six-page marketing website built for Michael's professional book marketing practice. The website is designed to communicate credibility, experience, and strategic expertise to authors seeking thoughtful book marketing support.

---

## 1. Project Overview

This is a static, multi-page website built with pure HTML5, CSS3, and vanilla JavaScript. No frameworks, build tools, or package managers are required. The project is intentionally simple to open, edit, and maintain in VS Code.

**Business owner:** Michael
**Business:** Professional Book Marketing
**Professional email:** michael.bookmarketing020@gmail.com

---

## 2. Project Structure

```text
MICHAEL-BOOK-MARKETING/
│
├── index.html         Home page
├── services.html      Services catalogue (7 categories)
├── about.html         About Me
├── faq.html           Frequently Asked Questions (accordion)
├── pricing.html       Three editable marketing packages
├── contact.html       Contact form with Formspree integration
├── style.css          Complete shared stylesheet (design system, layouts, animations, responsive rules)
├── my logo.png        Logo file (to be added by Michael)
├── images/            Reserved for any additional local images
└── README.md          This documentation file
```

All six HTML pages share a single stylesheet (`style.css`) and use consistent navigation, typography, color palette, and layout patterns.

---

## 3. How to Run the Website

No installation or build process is needed.

### Option A: Open directly in a browser
1. Make sure all project files are in the same folder.
2. Place your `my logo.png` file in the project root (see Section 5).
3. Double-click `index.html` to open it in your default browser.

### Option B: Use VS Code with Live Server
1. Install the "Live Server" extension in VS Code.
2. Open the project folder in VS Code.
3. Right-click `index.html` and select **Open with Live Server**.
4. The site will open at `http://127.0.0.1:5500` with automatic reload on save.

Live Server is recommended during development because it mirrors how the site will behave once uploaded to a real domain.

---

## 4. Pages Overview

| Page | File | Purpose |
|------|------|---------|
| Home | `index.html` | Hero, experience figures, intro, services preview, why work with me, CTA |
| Services | `services.html` | Full 7-category services catalogue with all sub-services |
| About Me | `about.html` | Professional introduction, values, approach, experience figures |
| FAQ | `faq.html` | Interactive accordion answering 14 common questions |
| Pricing | `pricing.html` | Three marketing packages with editable pricing placeholders |
| Contact Me | `contact.html` | Contact information and Formspree-integrated enquiry form |

The logo appears only on **Home**, **About Me**, and **Contact Me**, as specified.

---

## 5. Logo Setup

The logo file must be named exactly:

```
my logo.png
```

Place it in the project root (the same folder as `index.html`). The HTML files reference it with the path `my logo.png`.

Do not rename the file. If the file is missing, the logo area on Home, About Me, and Contact Me pages will display a broken image icon until the file is added.

---

## 6. Images

All non-logo images on the website are loaded directly from Unsplash via hotlinked URLs. This keeps the project lightweight and avoids bundling large image files locally. Every image includes meaningful alternative text and uses `loading="lazy"` or `loading="eager"` where appropriate.

The `images/` folder is included in the project structure for your own use if you later wish to replace any Unsplash images with local copies. If you do, simply download the image, place it in `images/`, and update the `src` attribute in the relevant HTML file to point to `images/your-image-name.jpg`.

### Current image sources
All images are sourced from [Unsplash](https://unsplash.com), which permits free commercial and non-commercial use under the Unsplash License.

### Replacing an image
If you prefer to self-host an image, the process is:
1. Download the image to your computer.
2. Place it in the `images/` folder.
3. Update the `src` in the relevant HTML file, for example:
   `src="images/library-interior.jpg"` instead of the Unsplash URL.

---

## 7. Formspree Form Integration

The contact form on `contact.html` is wired to your Formspree endpoint:

```
https://formspree.io/f/xyeeqogk
```

The form uses:
- `method="POST"`
- `action="https://formspree.io/f/xyeeqogk"`
- Client-side validation for all required fields
- An asynchronous submission using `fetch()` with a loading state, success message, and error handling
- A hidden honeypot field (`_gotcha`) for basic spam protection
- A `_subject` hidden field so submissions arrive in your inbox with a clear subject line

### Important: verify the form end to end
Before relying on the form in production:
1. Open `contact.html` in a browser.
2. Fill in every field with real information.
3. Submit the form.
4. Check your Formspree dashboard for the submission.
5. Confirm that Formspree is forwarding submissions to your Gmail address (`michael.bookmarketing020@gmail.com`).

Formspree may require you to confirm the owner email address the first time a submission is sent. Follow the instructions in the Formspree confirmation email to activate delivery.

**Note:** This form has not been submission-tested from this project environment. A real submission from your browser is required to confirm the end-to-end flow.

---

## 8. Pricing Page

The three packages on `pricing.html` are:
1. **Essential Book Promotion**
2. **Professional Book Marketing** (highlighted as the most chosen option)
3. **Comprehensive Book Marketing**

Each package currently displays a price placeholder:

```
[ Price on Request ]
```

To add real prices once you are ready:
1. Open `pricing.html`.
2. Locate each `<span class="price-placeholder">[ Price on Request ]</span>` element.
3. Replace the placeholder text with your actual price, for example:
   `<span class="price-placeholder">$750</span>`

You may also update the `<span class="price-note">` beneath each price to reflect per-project, per-month, or any other pricing structure.

---

## 9. Navigation and Active States

The navigation is identical across all six pages. Each page sets the `active` class on its own navigation link so visitors can see where they are. If you add or rename pages, remember to update the navigation `<ul>` block in every HTML file.

---

## 10. Design System

**Colors**
- Midnight Navy: `#142536`
- Warm Ivory: `#F5F0E6`
- Muted Gold: `#B69A62`

**Typography**
- Headings: Cormorant Garamond (serif)
- Body text: Inter (sans-serif)

Both fonts are loaded from Google Fonts at the top of every HTML file.

**Animations**
- Scroll-triggered fade-in and slide-up reveal effects using `IntersectionObserver`
- Smooth button hover and underline nav effects
- FAQ accordion expand and collapse transitions
- Subtle background zoom on the homepage hero
- All animations respect the user's `prefers-reduced-motion` setting

---

## 11. Responsive Design

The website is fully responsive and tested in layout across:
- Desktop (1240px and wider)
- Laptop (960px to 1239px)
- Tablet (641px to 959px)
- Mobile (up to 640px)

The mobile navigation is a slide-in panel triggered by the hamburger icon. The pricing grid, services grid, and all multi-column layouts collapse gracefully on smaller screens.

---

## 12. SEO and Accessibility

Each page includes:
- A unique `<title>`
- A relevant `<meta name="description">`
- Keywords and author meta tags
- Semantic HTML (`<header>`, `<section>`, `<article>`, `<footer>`, `<nav>`)
- Descriptive alt text on all images
- A properly linked favicon (`my logo.png`)

Accessibility considerations:
- Keyboard-focusable navigation, buttons, and form fields
- ARIA attributes on the mobile nav toggle and FAQ accordion
- `prefers-reduced-motion` support
- Sufficient color contrast for text against backgrounds

---

## 13. Browser Compatibility

The website is built with modern, well-supported CSS and JavaScript. It will work correctly in:
- Google Chrome (latest)
- Mozilla Firefox (latest)
- Safari (latest)
- Microsoft Edge (latest)

Features like `backdrop-filter`, `IntersectionObserver`, and CSS custom properties are used throughout. All have strong support in current browsers.

---

## 14. Manual Steps and Recommendations

Before launching the website publicly, please complete the following:

1. **Add the logo file.** Place `my logo.png` in the project root.
2. **Test the contact form.** Submit a real enquiry and confirm it reaches your Gmail inbox.
3. **Update pricing.** Replace `[ Price on Request ]` placeholders on `pricing.html` once you have confirmed prices.
4. **Review every page.** Open each page in a browser and review the written content to ensure the tone, voice, and details feel accurate to you.
5. **Choose a hosting provider.** Any static hosting service will work. Recommended options include Netlify, Vercel, GitHub Pages, and Cloudflare Pages. Simply upload the entire project folder.
6. **Set up a custom domain.** Once hosted, you can point a custom domain (if you have one) to your hosting provider using the instructions they provide.

---

## 15. Project Summary

- **6 HTML pages** built with semantic, hand-written markup
- **1 shared CSS file** containing the full design system, layouts, animations, responsive rules, and accessibility support
- **Inline JavaScript** only where functional (mobile nav, header scroll state, reveal animations, FAQ accordion, contact form)
- **Formspree integration** on the Contact Me page with real asynchronous submission handling
- **Editable pricing placeholders** on the Pricing page
- **Logo displayed** only on Home, About Me, and Contact Me pages
- **No frameworks, build tools, or external dependencies** beyond Google Fonts and Unsplash image URLs
- **Full responsiveness** across desktop, tablet, and mobile
- **Reduced-motion accessibility** respected across all animations

---

## 16. Features Not Independently Verified

To be fully transparent, the following have not been tested from this development environment and require your real-world verification:

1. **Formspree form submission.** The form is correctly wired to your endpoint, but only a real browser submission from your side will confirm that messages reach your Gmail inbox successfully.
2. **Logo rendering.** The logo file (`my logo.png`) needs to be added to the project root before Home, About Me, and Contact Me pages will display it.
3. **Unsplash image availability.** All images are hotlinked from Unsplash. If Unsplash ever changes an image URL, you may need to update the `src` or replace with a local copy in the `images/` folder.

---

## 17. Contact

For questions about this website:

**Email:** [michael.bookmarketing020@gmail.com](mailto:michael.bookmarketing020@gmail.com)

---

&copy; Michael. Professional Book Marketing. All rights reserved.