# Kiden Studio website

The website of Daisy Kiden — contemplative, nature-inspired art.

## What's in this folder
- `index.html` — all the words and pictures on the site. Each section is marked with a comment like `<!-- ===== PAINTINGS ===== -->` so you can find it.
- `styles.css` — the look. Colours and fonts are at the very top, under `:root`.
- `images/` — all artwork and the logo.

## Editing text (on github.com)
1. Open `index.html` and click the pencil icon.
2. Press Ctrl+F (Cmd+F on Mac) to find the words you want to change.
3. Change only the words between the tags, e.g. `<p>change this text</p>`.
4. Click **Commit changes**. Netlify updates the live site within a minute.

## Adding a new artwork
1. Open the `images` folder, click **Add file → Upload files**, upload the photo (use a simple name like `painting-sunrise.jpg`, no spaces).
2. In `index.html`, find the section you want (e.g. PAINTINGS), copy one whole `<figure> ... </figure>` block, paste it below, and change the image name, title and medium.

## Changing colours
In `styles.css`, change the hex codes at the top (e.g. `--umber: #563C23;`).
