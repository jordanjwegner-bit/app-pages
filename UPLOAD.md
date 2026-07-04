# Uploading site/ to GitHub Pages (one time, ~5 minutes)

Target: https://jordanjwegner-bit.github.io/app-pages/

1. Create the repo (public) on GitHub: account **jordanjwegner-bit**, name **app-pages**
   (github.com → New repository → no README).
2. Push this folder as the repo root:
   ```bash
   cd /Users/jordan/overnight-apps/site
   git init && git add -A && git commit -m "App privacy + support pages"
   git branch -M main
   git remote add origin https://github.com/jordanjwegner-bit/app-pages.git
   git push -u origin main
   ```
3. Enable Pages: repo → Settings → Pages → Source: **Deploy from a branch** →
   Branch **main**, folder **/ (root)** → Save. Live in ~1–2 minutes.
4. Verify (all three must load):
   - https://jordanjwegner-bit.github.io/app-pages/
   - https://jordanjwegner-bit.github.io/app-pages/abyssalbloom/privacy/
   - https://jordanjwegner-bit.github.io/app-pages/abyssalbloom/support/
5. Future updates (new apps get pages automatically named after their slug):
   ```bash
   python3 tools/make-site.py app-01 ... queue/app-YYYYMMDD-slug   # regenerate
   cd site && git add -A && git commit -m "pages update" && git push
   ```

Do this BEFORE the next ship: every app's App Store metadata now points at
these URLs, and App Review clicks them.
