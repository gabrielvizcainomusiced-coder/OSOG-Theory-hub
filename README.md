# Okanagan School of Guitar — Theory Foundations Hub

A single-page beginner theory primer and quiz for your students, matching your studio's
look (teal/cream palette from your GoDaddy site, plus a warm amber accent).

## What's in the box

- `index.html` — the whole site. No build step, no dependencies to install.
- `assets/` — your logo, cropped and recolored for different spots on the page (nav icon,
  hero image, a white version for the dark footer, and a favicon). Keep this folder in the
  same place relative to `index.html` when you upload to GitHub, or the images won't load.
- Covers: the musical alphabet, the fingerboard grid, the major scale formula, and finding the root.
- Ends in a 10-question quiz. Students see their score instantly, and their name, score,
  and full answer breakdown get emailed to you.
- Colors and fonts are pulled from your actual logo and studio branding (the teal from your
  guitar mark, Montserrat for headings to match the wordmark's bold caps style).

## Step 1 — Get your free Formspree endpoint (5 minutes)

This is what sends quiz results to your inbox — no backend or database needed.

1. Go to **[formspree.io](https://formspree.io)** and sign up free (50 submissions/month on the free plan).
2. Click **New Form**, name it something like "Theory Quiz Results," and set the delivery
   email to `okanaganschoolofguitar@gmail.com`.
3. Formspree gives you a URL that looks like `https://formspree.io/f/abcd1234`.
4. Open `index.html`, find this line near the bottom (search for `FORMSPREE_ENDPOINT`):

   ```js
   var FORMSPREE_ENDPOINT = "https://formspree.io/f/YOUR_FORM_ID";
   ```

   Replace `YOUR_FORM_ID` with your actual form's URL from step 3, then save the file.
5. The first submission after you connect it will land you an email from Formspree asking
   you to confirm the form — click confirm, and every submission after that flows straight
   to your inbox automatically.

## Step 2 — Host it free on GitHub Pages

1. Create a new repository on GitHub (e.g. `theory-hub`).
2. Upload both `index.html` **and the whole `assets` folder** to it, keeping the same folder
   structure (drag and drop on the GitHub website works fine, or `git push` if you're
   comfortable with that — same as you did for the duo site). If the assets folder isn't
   uploaded alongside index.html, the logo images won't show up.
3. In the repo, go to **Settings → Pages**.
4. Under "Build and deployment," set **Source** to `Deploy from a branch`, branch `main`,
   folder `/ (root)`. Save.
5. GitHub gives you a live URL within a minute or two, usually
   `https://<your-username>.github.io/theory-hub/`.

That's it — no server, no monthly hosting cost, and you already know this workflow from the
duo website.

## Sending students the link

Once it's live, drop the GitHub Pages link in your welcome email or texts to new students —
"before our first lesson, work through this and take the short quiz." You'll get their
results in your inbox before they ever pick up the guitar.

## Customizing later

- **Colors/fonts:** all defined as CSS variables at the top of the `<style>` block (`:root`),
  so a palette or font swap is a few line edits, not a rebuild.
- **Adding more topics/questions:** each topic is a self-contained `<section class="topic">`
  block, and each quiz question is a `<div class="q" data-answer="...">` block — copy an
  existing one and edit the text to extend either.