# SoClean — Cleaning Service Training and Recruitment

Envato **Elementor Template Kit** (not a full WordPress core/database dump). Pages, global styles, and media references live in `manifest.json` and `templates/`.

## Staging / client review

- **Live kit demo (full Elementor site):** https://demo.deverust.com/soclean/
- **Kit screenshots in this repo:** GitHub Pages (enabled after first push)
- **Disposable WordPress with required plugins:** open the Playground blueprint after this repo is public:

  `https://playground.wordpress.net/?blueprint-url=https://raw.githubusercontent.com/Dhaval1441/soclean-elementor-template-kit/main/blueprint.json`

This package has **no WordPress database, `wp-config.php`, or credentials**. Do not commit those files.

## Requirements

| Plugin / theme | Version in kit | Notes |
| --- | --- | --- |
| Elementor | 3.32.4+ | wordpress.org |
| ElementsKit Lite | 3.7.3+ | wordpress.org |
| MetForm | 4.0.6+ | wordpress.org |
| Gum Addon for Elementor | 1.3.14+ | Envato / TemeGUM (not in this zip) |
| Hello Elementor theme | latest | recommended |

PHP 7.4+ / 8.x, WordPress 6.x. Elementor Pro is **not** required.

## Local setup (another computer)

1. Install WordPress (Local, MAMP, or any host). Activate **Hello Elementor**.
2. Install and activate the plugins above. Skip the setup wizards.
3. Zip these kit files only (not this whole git folder):

   - `manifest.json`
   - `templates/`
   - `screenshots/`
   - `help.html`

   Name the zip e.g. `soclean-kit.zip`.
4. In WP Admin: **Elementor → Tools → Import/Export Kit → Start Import**. Upload the zip. Import templates, site settings, and content.
5. **Templates → Theme Builder** (or ElementsKit headers/footers): assign Header and Footer to the entire site.
6. **Settings → Reading:** set Home as the homepage.
7. **Elementor → Settings:** enable unfiltered file uploads if images fail to import, then re-import.

Media in the JSON points at `demo.deverust.com` until Elementor downloads it during import (needs a machine with outbound HTTP).

## Database migration

There is no SQL dump in this repository. After WordPress is installed:

- **Same kit on a new WP:** re-import the Elementor kit zip (preferred).
- **Moving an already-built WP site:** export with a migration plugin (All-in-One WP Migration, Duplicator, or WP-CLI `db export`). On the destination, import, then search-replace the old URL with the new one (`wp search-replace`). Never commit `wp-config.php` or SQL files; keep DB user/password only on the server.

## Deployment

1. Provision PHP + MySQL hosting and a standard WordPress install.
2. Repeat **Local setup** on that host, or migrate an existing built site as above.
3. Set permalinks to Post name and flush permalinks.
4. Do not put database passwords, WP admin passwords, or `.env` files in git.

Free sandbox hosts (TasteWP and similar) expire unless you create an account; use them only for short reviews. For a lasting client preview of this kit’s design, use the live demo URL above until you have durable WordPress hosting.

## Repo layout

```
manifest.json      # kit index, plugins, image map
templates/         # Elementor JSON (pages, header, footer, forms, global styles)
screenshots/       # page previews
blueprint.json     # WordPress Playground plugins/theme
help.html          # Envato kit help redirect
```
