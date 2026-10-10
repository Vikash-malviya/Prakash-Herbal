# Prakash Herbal — static shared-hosting deployment

## Output folder to upload
Build output: `/app/frontend/build`

Upload the **contents** of `/app/frontend/build` into your shared hosting web root, usually `public_html/` or `www/`:
- `index.html`
- `404.html`
- `robots.txt`
- `sitemap.xml`
- `asset-manifest.json`
- `static/css/main.*.css`
- `static/js/main.*.js`

(Source maps `*.map` and `asset-manifest.json` are optional; keep them if unsure, they do no harm.)

## Rebuild command
```bash
cd /app/frontend
yarn build
```

## Hosting requirements
- Static file hosting only is enough.
- The Python backend has been removed: no FastAPI, Uvicorn, ASGI, MongoDB, Passenger WSGI app, cron, or long-running process is required. Do not upload `/app/backend`.
- The site uses hash/anchor sections only, so **no special `.htaccess` rewrite rules are required**.
- Optional: to show the branded `404.html` for missing URLs, either set the custom 404 page in your hosting control panel, or (only if your host allows `.htaccess` overrides) add one line: `ErrorDocument 404 /404.html`. If your host shows errors after adding it, delete the `.htaccess` file — the website itself does not need it.
- `package.json` uses `"homepage": "."`, so asset paths are relative and the build also works if uploaded inside a subfolder.

## SEO notes
- Title, meta description, Open Graph, Twitter card and LocalBusiness structured data (JSON-LD) are included in `index.html` using only verified business details.
- The canonical URL and og:url set themselves automatically to whatever domain the site is hosted on — nothing to edit.
- `sitemap.xml` contains the placeholder `https://your-domain-here/`. After your domain is live, replace it with your real domain (one edit) and optionally add `Sitemap: https://your-domain/sitemap.xml` to `robots.txt`.

## Steps
1. Run the rebuild command above.
2. Open `/app/frontend/build` and confirm it contains `index.html`, `404.html`, `robots.txt`, `sitemap.xml`, and `static/css` + `static/js`.
3. In your hosting file manager or FTP, open `public_html/`.
4. Upload everything inside `/app/frontend/build` into `public_html/` (do not upload it as a nested `build/build` path unless you want the site under `/build/`).
5. Visit your domain and test: category filters, product detail panel, images, mobile menu, and the enquiry form.
6. Submit a test enquiry. It should open WhatsApp for `+91 80059 87791` with the prefilled product/category/quantity/name/phone/address message. If the browser blocks the WhatsApp tab, the page shows a "Copy enquiry message" button instead.
7. Update the domain inside `sitemap.xml` and submit it in Google Search Console if you use it.

## Notes / limits
- Product data is bundled locally in the frontend JavaScript; no database is used.
- Logo is loaded from the existing hosted asset URL; category/hero/story/privacy images are loaded from Unsplash; Google Fonts and Google Maps are external services. The site still needs normal internet access for those third-party assets.
- Below-the-fold images use lazy loading; the logo and hero banner are not lazily loaded.
