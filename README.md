# Lab

A catchall for side projects and occasional builds. Each one lives in its own folder and serves at `lab.carterbayer.com/[folder]/`. Separate from Croak and CRI infra.

## How it serves

* **Host:** GitHub Pages
* **Domain:** `lab.carterbayer.com` (CNAME record `lab` → `cartercjb.github.io` at GoDaddy)
* **Pin:** the `CNAME` file at the repo root holds the domain
* **Front door:** the root `index.html` lists projects. Because that file exists, the root URL serves it instead of this README. This README only shows on the repo page.

Same pattern as `cri.carterbayer.com` (the `cartercjb/cri-board` repo).

## Structure

```
/
  index.html        front door, lists projects
  CNAME             lab.carterbayer.com
  README.md         this file
  dr-j/
    index.html      Dr. J's Rounds, Louisville bachelor itinerary
```

## Convention

* One folder per project.
* Folder names lowercase, kebab-case (`dr-j`, `course-name`).
* Each project keeps its own `index.html` and any assets inside its folder.
* Static files only. No build step.

## Add a project

1. Make a folder, lowercase kebab-case (e.g. `new-thing/`).
2. Drop an `index.html` inside it.
3. Add a row to the root `index.html`: copy an existing `.entry` block, point `href` at the folder, bump the number, edit the name, description, and date. A comment in the file marks the spot.
4. Commit. It serves at `lab.carterbayer.com/new-thing/` within about a minute.

## Projects

* `dr-j/` Dr. J's Rounds. Louisville bachelor weekend itinerary, animated single page. 2026 · 07.

## Notes

* HTTPS is handled by GitHub (Let's Encrypt). After first adding the custom domain, give the cert time to provision before ticking **Enforce HTTPS**.
* If GitHub flags an `InvalidDNSError` right after setup, it usually just checked before the record propagated. Confirm the CNAME resolves, then clear and re-add the domain in Settings to force a fresh check.
