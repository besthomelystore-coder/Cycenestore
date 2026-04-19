# Cycenestore Affiliate Page — WordPress Installation Guide

## What's included

```
cycenestore-affiliate-child/
├── style.css              ← Child theme header (required by WordPress)
├── functions.php          ← Enqueues fonts & CSS; adds body class
├── affiliate-page.css     ← All scoped styles (prefixed "csa-")
└── page-affiliate.php     ← Page template (the full affiliate page)
```

---

## Step 1 — Set the correct parent theme

Open `style.css` and change the `Template:` line to match your
active theme's **folder name** (not its display name):

```css
Template: astra          /* if your theme folder is /wp-content/themes/astra */
Template: generatepress  /* GeneratePress */
Template: kadence        /* Kadence */
Template: twentytwentyfour /* WordPress default */
```

---

## Step 2 — Upload the child theme

1. In your WordPress admin go to **Appearance → Themes → Add New → Upload Theme**.
2. Zip the entire `cycenestore-affiliate-child/` folder.
3. Upload the zip and click **Activate**.

Alternatively, upload the folder via FTP/SFTP to:
`/wp-content/themes/cycenestore-affiliate-child/`
then activate from **Appearance → Themes**.

---

## Step 3 — Create the affiliate page

1. Go to **Pages → Add New**.
2. Give it a title, e.g. *"Kitchen Finds"* or *"Shop"*.
3. In the right sidebar, find **Page Attributes → Template**.
4. Select **"Cycenestore Affiliate Page"** from the dropdown.
5. Click **Publish**.

The full affiliate landing page now lives at that page's URL.

---

## Step 4 — (Optional) Hide your theme's header & footer

If you want a completely standalone page (no theme nav/footer):

**Option A — Full-width page template (recommended)**
Many themes (Astra, GeneratePress, Kadence, Elementor) have a
built-in "Blank" or "Canvas" template. Select it *alongside* this
template, or use their "Disable header/footer" toggle in the page
settings panel.

**Option B — Suppress via functions.php**
In `functions.php`, find the `csa_maybe_suppress_chrome()` function
and uncomment the `remove_action()` lines that match your theme.

**Option C — Custom header/footer templates**
Copy your parent theme's `header.php` and `footer.php` into the child
theme folder and strip out anything you don't need.

---

## Customisation tips

| What to change | Where |
|---|---|
| Affiliate link URLs | `page-affiliate.php` — search for `amzn.to` |
| Colour palette | `affiliate-page.css` — edit the CSS variables in `.csa-wrap { --csa-* }` |
| Google Fonts | `functions.php` — edit the `csa-google-fonts` URL |
| Product descriptions / copy | `page-affiliate.php` — plain HTML, no shortcodes needed |
| Section padding / spacing | `affiliate-page.css` — look for `padding: 7rem 6%` etc. |

---

## Affiliate disclosure compliance

The page already includes a disclosure notice at the bottom.
Make sure your Amazon Associates tag is embedded in every `amzn.to`
link and that the disclosure is visible above the fold if required
by your local regulations (e.g. FTC in the US).

---

## Compatibility

Tested with:
- Twenty Twenty-Four (block theme)
- Astra (classic)
- GeneratePress (classic)
- Kadence (hybrid)

Requires WordPress 6.0+ and PHP 7.4+.

---

## Support

For questions about Cycenestore products visit https://cycenestore.com
