# GB Consultancy Group — Website

Static, no-build-step site (plain HTML/CSS/JS + Tailwind-free hand-written CSS).
Chosen deliberately so it can be uploaded and edited directly through the
GitHub mobile web interface, the same way the Innovate Stadia Systems Poland
site is maintained — no npm install, no build pipeline, nothing that can
break from a phone browser.

## File structure

```
index.html        Home
about.html        About Us
services.html     Services
partners.html     Strategic Partners
footprint.html    EU/UK Footprint
contact.html      Contact (GDPR enquiry form)
css/style.css     Full design system
js/main.js        Nav toggle, cookie consent, legal modals, form validation
assets/images/    logo-white.png and logo-lockup.jpg (your uploaded logo files)
```

Every page is self-contained (nav, footer, cookie banner, and legal modals
are duplicated in each file rather than "included"), so nothing breaks if a
script fails to load — content is visible without JavaScript by default.

## Deploying via GitHub Pages (mobile-friendly steps)

1. Create a new GitHub repository (e.g. `gb-consultancy-group`).
2. Using the GitHub mobile web upload screen ("Add file" → "Upload files"),
   upload the files **preserving folder paths** — drag the whole unzipped
   folder if your browser supports it, or upload `css/style.css` and
   `js/main.js` into their own paths one at a time if not.
3. In the repository, go to **Settings → Pages**, set the source branch to
   `main` (or `master`) and folder to `/ (root)`, then save.
4. Your site will be live at `https://<username>.github.io/gb-consultancy-group/`
   within a few minutes. To use a custom domain, add it under
   **Settings → Pages → Custom domain** and create the matching DNS record.

## Before going live — items still needed

- [ ] Replace all `[bracketed placeholders]` in the footer, About page, and
      Contact page: CRO number, registered office address, contact email/phone.
- [ ] Have a qualified solicitor review the Privacy Policy, Terms of Use, and
      Cookie Policy text in the modals (marked as placeholder text).
- [ ] Wire the contact form (`js/main.js`, inside the `contact-form` submit
      handler) to a real, GDPR-compliant backend — e.g. Formspree, Basin, or
      a serverless function hosted in the EU. Right now it only validates
      and shows a confirmation message; it does not send anywhere.
- [ ] Replace the gold-bordered placeholder image panels (stadium exterior,
      boardroom, legal office, blueprint imagery) with licensed photography.
- [ ] Confirm whether Innovate Stadia Limited / Innovate Stadia Systems Poland
      want their own logo files used on the Partners page instead of the
      text-based placeholders currently used there.
- [ ] Auto-translation: this site's markup is clean semantic HTML with a
      `lang="en"` attribute, which is what browser-native translation tools
      (Chrome/Edge "Translate this page") key off — no extra code needed for
      that. If in-page language switching to Polish is wanted instead of
      relying on the browser, that would need a small i18n layer added later.
