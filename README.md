# AISearch BYOK — landing page

Static one-page landing site for **AISearch BYOK** WordPress plugin. Plain HTML + Tailwind via CDN. No build step.

## Deploy to Cloudflare Pages (recommended)

1. **Create the GitHub repo:**

   ```bash
   cd /Users/mo/Desktop/ai-projects/aisearch-byok-site
   git init
   git add .
   git commit -m "Initial landing page"
   gh repo create aisearch-byok-site --public --source=. --push
   ```

   (If you don't have `gh` installed: `brew install gh && gh auth login`.)

2. **Connect to Cloudflare Pages:**
   - Go to https://dash.cloudflare.com → Workers & Pages → **Create** → **Pages** → **Connect to Git**
   - Pick the `aisearch-byok-site` repo
   - Build settings: **Framework preset = None**, **Build command = (empty)**, **Build output directory = `/`**
   - Click **Save and Deploy**

3. **Custom domain (optional but recommended for Lemon Squeezy approval):**
   - Buy domain at Cloudflare Registrar (~$10/year, no markup)
   - In Pages project → **Custom domains** → **Set up a custom domain** → enter `aisearchbyok.com`
   - DNS records auto-create. SSL cert provisions in ~60 seconds.

## Local preview

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Files to fill in before going live

- `index.html` — replace `data-ls-checkout="single"` and `data-ls-checkout="unlimited"` href values with your real Lemon Squeezy checkout URLs once products are created.
- `index.html` — replace `support@aisearchbyok.com` with your real support inbox.
- `index.html` — replace `https://wordpress.org/plugins/aisearch-byok/` with the real URL once the plugin is approved.
- Add a real Open Graph image at `/og.png` (1200×630).
