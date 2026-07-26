# KORE Landing Pages

This repository holds the KORE partner landing pages. Each page is a small static site (HTML, CSS, images)
living in its own top-level folder.

**Publishing is automatic.** When an approved change lands on the `main` branch, a GitHub Actions workflow
rebuilds **only the page(s) you changed** and publishes them to the live site — usually within a minute or
two, with no downtime. There is no separate deploy step to run.

---

## What you can and cannot change

**You can change the design of a page:** copy, headings, colors, images, and layout.

**Please do not change how a form works.** Each page's `index.html` has a small piece of wiring that sends
form submissions to the system that collects your leads — the form field names, which fields are required,
and the address the form submits to. Changing those can silently stop leads from arriving. If you need a form
change (a new field, a new recipient, different validation), request it through Tony (tbarroqueiro@fusionapps.com) rather
than editing it yourself; that part is handled on the backend so nothing breaks.

Rule of thumb: you own the **look** of the page; the **form plumbing** is managed for you.

---

## The pages

Each page is its own top-level folder. `_template/` is a starting scaffold, not a live page — do not edit or
deploy it.

| Page | Folder |
|---|---|
| Pegatron | `pegatron` |
| Klutch | `klutch` |
| NevTech | `nevtech` |
| Always Connect | `always-connect` |
| Connected501 | `connected501` |
| VeeOne Health | `veeone-health` |
| All Roads SAT | `all-road-sat` |
| Telecom VAR | `telecomvar` |

---

## Make and publish a change

```
# once: clone the repository
git clone https://github.com/Fusionapps-LLC/giovatto-kore-landing-pages.git
cd giovatto-kore-landing-pages
```

1. **Start clean and current:**
   ```
   git checkout main
   git pull
   ```
2. **Edit the page's folder only** (e.g. `nevtech/index.html`, its images, `styles.css`). Design changes only.
3. **Bump the cache-bust stamp if you changed CSS or a script.** The public site sits behind a cache, so a
   changed `styles.css` won't reach visitors unless its version stamp changes. Each page references
   `styles.css?v=<stamp>` — set it to today's date (add a letter for a second same-day change), e.g.
   `styles.css?v=20260724`.
4. **Commit and push** (or open a pull request and merge — landing on `main` publishes):
   ```
   git add -A
   git commit -m "nevtech: updated hero copy and image"
   git push origin main
   ```

**Force a redeploy** (no content change, or to re-publish one page): the repo's **Actions** tab →
**Deploy KORE landing pages** → **Run workflow**, set `page` to a folder name (e.g. `nevtech`) or `all`.

---

## Verify and troubleshoot

- **Check the deploy ran:** the **Actions** tab → the latest **Deploy KORE landing pages** run has a green
  check. A red run means the deploy failed — open it to see which page and why.
- **Page looks stale after a push?** That's the cache on the public site. Confirm you bumped the `?v=` stamp
  for any CSS/JS change and hard-refresh. If it still won't update, let your KORE contact know so the cache
  can be cleared.
- **Roll back a change:** `git revert <commit>` then push — the workflow republishes the previous version.
- **Anything involving the form, the leads, or the data a page collects:** reach out to Tony (tbarroqueiro@fusionapps.com)
  rather than editing it directly.

---

## Per-page setup

Setting up a brand-new page from the scaffold (Font Awesome Pro assets, fonts, placeholders)? See
[`_template/README.md`](_template/README.md).
