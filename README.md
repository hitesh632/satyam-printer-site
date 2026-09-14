# Satyam Printer — website

A static site for Satyam Printer (printing, packaging & branding, Mumbai), built to host on GitHub Pages with the custom domain **satyamprinter.store**.

Files:
- `index.html` — the page
- `styles.css` — all styling
- `script.js` — mobile menu + footer year
- `favicon.svg` — small tab icon
- `CNAME` — tells GitHub Pages to serve your custom domain (already set to `satyamprinter.store`)

No build step, no dependencies — it's plain HTML/CSS/JS, so GitHub Pages can serve it as-is.

---

## 1. Push it to GitHub

If you haven't made the repo yet:

1. Go to github.com → **New repository**. Name it whatever you like, e.g. `satyam-printer-site`. Public repo (Pages on a free plan needs public, unless you're on GitHub Pro/Team/Enterprise).
2. On your computer, in this folder, run:

```bash
git init
git add .
git commit -m "Initial website"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin main
```

(Replace `<your-username>/<your-repo>` with your actual GitHub username and repo name.)

## 2. Turn on GitHub Pages

1. In your repo on GitHub, go to **Settings → Pages**.
2. Under "Build and deployment" → **Source**, choose **Deploy from a branch**.
3. Branch: `main`, folder: `/ (root)`. Save.
4. GitHub will give you a URL like `https://<your-username>.github.io/<your-repo>/`. Wait a minute or two and check it loads.

## 3. Point your domain (satyamprinter.store) at it

You bought `satyamprinter.store` from a registrar (GoDaddy, Namecheap, Google Domains, etc). You need to add DNS records there pointing to GitHub Pages.

Go to your registrar's DNS settings for `satyamprinter.store` and add:

**A records** (apex domain → GitHub Pages IPs), all with host `@`:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**CNAME record** for the `www` subdomain (optional but recommended), host `www`, pointing to:
```
<your-username>.github.io
```

Then back in GitHub: **Settings → Pages → Custom domain**, type `satyamprinter.store`, and save. This writes the `CNAME` file into your repo automatically (it's already included here, but GitHub will confirm it matches). Once DNS propagates (can take a few minutes to a few hours), tick **Enforce HTTPS** in the same settings page — GitHub issues a free SSL certificate automatically.

Check propagation any time at whatsmydns.net.

## 4. About sales@satyamprinter.store

GitHub Pages only hosts the *website* — it can't send or receive email. Buying the domain does not automatically give you a working mailbox. To actually use `sales@satyamprinter.store`, you need an email host pointed at the same domain via **MX records** (separate from the A/CNAME records above). Common options:

- **Google Workspace** or **Zoho Mail** (Zoho has a decent free tier for one custom-domain mailbox) — both walk you through adding MX records at your registrar.
- Many registrars (GoDaddy, Namecheap) also sell email hosting add-ons with one-click MX setup.

Once that's set up, `sales@satyamprinter.store` will work as your real inbox, and the "Get a quote" button and contact section on the site already point to it.

## 5. Editing content later

Everything is in plain HTML/CSS in `index.html` / `styles.css` — no templating engine. To change text, open `index.html` in any editor, find the section (services, industries, contact, etc.), edit, commit, and push — GitHub Pages redeploys automatically within a minute or two.
