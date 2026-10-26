# Kiden Studio website

Live at kidenstudio.com — the website of Daisy Kiden, contemplative nature-inspired art.

## What's in this folder
- `index.html` — all the words and pictures. Each section is marked with a comment like `<!-- ===== SHOP ===== -->`.
- `styles.css` — the look. Colours and fonts are at the top, under `:root`.
- `images/` — all artwork and the logo.
- `SHOP-SETUP.md` — step-by-step guide to turning on the shop.

## IMPORTANT
Your repository also has a file called `CNAME` which holds your domain name.
Do not delete it, or kidenstudio.com will stop working.

## Editing text (on github.com)
1. Open `index.html` and click the pencil icon.
2. Press Ctrl+F (Cmd+F on Mac) to find the words you want to change.
3. Change only the words between the tags, e.g. `<p>change this text</p>`.
4. Click **Commit changes**, wait a minute, then hard-refresh (Ctrl+Shift+R).

## Adding a new artwork
1. Open the `images` folder, click **Add file → Upload files**, upload the photo (simple name, no spaces).
2. In `index.html`, copy one `<figure> ... </figure>` block, paste it below, and change the image name, title and medium.
