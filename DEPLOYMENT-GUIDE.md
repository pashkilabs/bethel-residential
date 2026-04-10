# Bethel Residential Website — Deployment Guide

## What You Have

Your site package includes:

- `index.html` — The full website
- `images/logos/` — Bethel logo + city logos
- `images/gallery/` — Where before/after photos go
- `admin/` — Content management panel (for you & Steven)
- `_data/gallery/` — Gallery data files
- `_data/testimonials/` — Testimonial data files
- `CNAME` — Points the site to bethelresidential.com

---

## Step 1: Create a GitHub Account (5 minutes)

1. Go to **github.com** and click **Sign Up**
2. Use your email, create a password, pick a username
3. Verify your email address

## Step 2: Create a Repository (2 minutes)

1. Once logged in, click the **+** icon (top right) → **New repository**
2. Name it: `bethel-residential`
3. Set it to **Public** (required for free GitHub Pages)
4. Check **"Add a README file"**
5. Click **Create repository**

## Step 3: Upload the Site Files (5 minutes)

1. In your new repository, click **Add file** → **Upload files**
2. Drag the entire contents of the `bethel-site` folder into the upload area.
   Upload these items:
   - `index.html`
   - `CNAME`
   - `images/` folder (with all logos inside)
   - `admin/` folder (both files inside)
   - `_data/` folder
3. In the "Commit changes" box, type: `Initial site upload`
4. Click **Commit changes**

**Important:** Make sure `index.html` is at the ROOT level of the repository, not inside a subfolder.

## Step 4: Enable GitHub Pages (2 minutes)

1. Go to your repository's **Settings** tab
2. In the left sidebar, click **Pages**
3. Under "Source," select **Deploy from a branch**
4. Set Branch to **main** and folder to **/ (root)**
5. Click **Save**
6. Wait 1–2 minutes, then refresh — you'll see a green banner with your site URL

Your site is now live at: `https://YOUR-USERNAME.github.io/bethel-residential/`

## Step 5: Connect bethelresidential.com (10 minutes)

You need to update DNS settings wherever the domain was purchased (GoDaddy, Namecheap, Google Domains, etc.):

### Add these DNS records:

**A Records** (point to GitHub's servers):

| Type | Name | Value |
|------|------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

**CNAME Record** (for www):

| Type | Name | Value |
|------|------|-------|
| CNAME | www | YOUR-USERNAME.github.io |

### Then in GitHub:
1. Go to repository **Settings** → **Pages**
2. Under "Custom domain," enter: `bethelresidential.com`
3. Click **Save**
4. Check **"Enforce HTTPS"** (may take a few minutes to become available)

DNS can take 15 minutes to 48 hours to fully propagate, but usually works within an hour.

---

## How to Update the Site

### Option A: Quick Edits (For You)

To update text, photos, or anything on the site:

1. Go to your repository on github.com
2. Click on `index.html`
3. Click the **pencil icon** (Edit this file)
4. Make your changes
5. Click **Commit changes**
6. The site updates automatically in 1–2 minutes

### Option B: Adding Gallery Photos

1. Go to your repository on github.com
2. Navigate to the `images/gallery/` folder
3. Click **Add file** → **Upload files**
4. Upload before/after photos (name them clearly, like `deck-repair-before.jpg` and `deck-repair-after.jpg`)
5. Commit the changes
6. Then edit `index.html` to add the new images in the gallery section

### Option C: Using the CMS Admin Panel (For Steven)

**First-time setup** (requires a free Netlify account for authentication):

1. Go to **app.netlify.com** and sign up with GitHub
2. Click **New site from Git** → select the `bethel-residential` repository
3. This connects authentication so Steven can log in

Once set up, Steven goes to: `bethelresidential.com/admin`

From there he can:
- Add new gallery projects (with before/after photos)
- Add testimonials (client name, quote, location)
- Everything saves automatically to the site

**Important:** Update the `admin/config.yml` file — replace `YOUR_GITHUB_USERNAME` with your actual GitHub username.

---

## Adding Before & After Photos to the Gallery

When Steven sends you photos, here's the quick process:

1. Resize photos to around 1200px wide (keeps the site fast)
2. Upload to `images/gallery/` in the repository
3. In `index.html`, find the gallery section and replace a placeholder with:

```html
<div class="gallery-item">
  <img src="images/gallery/project-name-before.jpg" alt="Before - Deck Repair" style="width:100%; height:100%; object-fit:cover;">
</div>
<div class="gallery-item">
  <img src="images/gallery/project-name-after.jpg" alt="After - Deck Repair" style="width:100%; height:100%; object-fit:cover;">
</div>
```

## Adding Testimonials

Find the testimonials section in `index.html` and replace a placeholder card:

```html
<div class="testimonial-card">
  <div class="testimonial-quote">&ldquo;</div>
  <p class="testimonial-text">CLIENT'S QUOTE GOES HERE</p>
  <div class="testimonial-author">
    <div class="testimonial-avatar">JD</div>
    <div>
      <div class="testimonial-name">John Doe</div>
      <div class="testimonial-loc">The Woodlands, TX</div>
    </div>
  </div>
</div>
```

---

## Quick Reference

| Task | Where |
|------|-------|
| Edit site content | github.com → repository → index.html → pencil icon |
| Upload photos | github.com → repository → images/gallery/ → Add file |
| Steven manages content | bethelresidential.com/admin |
| Check site status | github.com → repository → Settings → Pages |
| DNS settings | Your domain registrar (GoDaddy, Namecheap, etc.) |

## Need Help?

If you run into issues with any step, screenshot the error and bring it back here — happy to troubleshoot.
