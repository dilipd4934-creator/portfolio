# Dilip D — Portfolio Website

A single-page portfolio built with plain HTML/CSS/JS (no build step, no framework —
loads instantly and is trivial to host on GitHub Pages).

## Files
```
index.html      → page structure & content
styles.css      → all styling
script.js       → scroll reveal + active nav highlight
```


## 2. Host it with GitHub Pages

1. In your repo, go to **Settings → Pages** (left sidebar).
2. Under **Build and deployment → Source**, select **Deploy from a branch**.
3. Under **Branch**, select `main` and folder `/ (root)`, then **Save**.
4. Wait ~1 minute. Your site will be live at:
   ```
   https://<your-username>.github.io/dilip-portfolio/
   ```
   Tip: if you name the repo exactly `<your-username>.github.io`, your site
   lives at the root — `https://<your-username>.github.io/` — with no repo
   name in the URL.
5. GitHub Pages auto-redeploys every time you push new commits to `main`.

---

## 3. Add Google Analytics (GA4)

1. Go to [analytics.google.com](https://analytics.google.com) → **Admin** → **Create property**.
   Name it "Portfolio", pick your timezone/currency, and finish setup.
2. Choose **Web** as the platform, enter your GitHub Pages URL, and create a
   **Data stream**.
3. Copy the **Measurement ID** shown — it looks like `G-XXXXXXXXXX`.
4. Open `index.html` in this project and replace **both** occurrences of
   `G-XXXXXXXXXX` (in the `<head>`, inside the two `<script>` tags) with your
   real ID:
   ```html
   <script async src="https://www.googletagmanager.com/gtag/js?id=G-ABC123XYZ"></script>
   <script>
     window.dataLayer = window.dataLayer || [];
     function gtag(){dataLayer.push(arguments);}
     gtag('js', new Date());
     gtag('config', 'G-ABC123XYZ');
   </script>
   ```
5. Commit and push the change (or re-upload `index.html` via the GitHub website).
6. Visit your live site, then check **Google Analytics → Reports → Realtime**
   — you should see yourself as an active user within a minute or two.

That's it — pageviews, visitor locations, and referral sources will now
populate under **Reports** in Google Analytics as people visit your site.

---

## Customizing later
- **Colors/fonts**: all defined as CSS variables at the top of `styles.css` under `:root`.
- **Content**: edit directly in `index.html` — it's plain text/HTML, no build step required.
- **Adding a project**: duplicate a `.project-card` block inside the `#projects` section.
