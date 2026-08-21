# Flynn & Phoenix — Setting Up Johnna's Dashboard

This gives Johnna a real login screen where she can add items, change
prices, upload photos, and mark things sold — no code, no texting Sam,
no waiting on Claude. Changes go live on the actual site automatically,
usually within about a minute.

It takes real setup to turn on (you're doing this part once), but
after today, day-to-day updates are just Johnna logging in and
filling out a form.

**Heads up before you start:** this changes *how* the site gets
updated. Up to now you've been dragging a folder onto Netlify by
hand. After this setup, the site lives on GitHub instead, and Netlify
watches it automatically — so for your own future edits, it's
`git add` / `git commit` / `git push` instead of drag-and-drop.
Johnna never touches any of this — she only ever sees the dashboard
in Part 5.

---

## Part 1: Push the site to GitHub (~5 min)

You've got GitHub already, so let's use real git.

1. On github.com, click the **+** icon top-right → **New repository**.
   Name it `flynn-and-phoenix`. Keep it **Public** (fine — it's just
   the site's code, already visible to anyone who views the website
   anyway). **Don't** check "Add a README" — an empty repo makes the
   push below cleaner. Click **Create repository**.
2. GitHub will show you the repo's URL, something like
   `https://github.com/your-username/flynn-and-phoenix.git` — copy it.
3. In your terminal, `cd` into the Flynn & Phoenix folder (the one
   with `index.html`, `products.json`, `admin/`, `images/` in it),
   then:

   ```bash
   git init
   git add .
   git commit -m "Initial site with CMS dashboard"
   git branch -M main
   git remote add origin https://github.com/your-username/flynn-and-phoenix.git
   git push -u origin main
   ```

   Swap in your actual repo URL from step 2. The push will take a
   minute or two — the images make it a real upload, not instant.
4. Refresh the GitHub repo page — you should see all the files there.

## Part 2: Point Netlify at GitHub instead of drag-and-drop (~5 min)

1. Log into **Netlify** → your Flynn & Phoenix site → **Site
   settings**.
2. Look for **"Build & deploy"** or **"Link repository"** (wording
   varies slightly). Choose **Link site to Git** (or similar).
3. Pick **GitHub**, authorize Netlify to access your account, then
   select the `flynn-and-phoenix` repository you just made.
4. When asked for a **build command**, leave it **blank** — this
   site doesn't need one. For **publish directory**, enter `.` (a
   single period, meaning "the whole folder").
5. Click **Deploy**. From now on, any change pushed to GitHub — by
   you, or by Johnna through her dashboard — automatically updates
   the live site within about a minute. No more dragging folders.

## Part 3: Turn on the login system (~5 min)

1. In Netlify, go to your site → **Identity** tab (if you don't see
   it, check under **Site configuration**). Click **Enable Identity**.
2. Scroll to **Registration** → set it to **Invite only**. (This
   matters — without it, anyone could sign up and edit the shop.)
3. Scroll to **Services** → **Git Gateway** → click **Enable Git
   Gateway**. This is what lets the dashboard actually save changes
   back to GitHub without Johnna ever seeing GitHub or needing her
   own account there.

## Part 4: Invite Johnna (~2 min)

1. Still in the **Identity** tab, click **Invite users**.
2. Enter Johnna's email (and yours too, if you'd like access as a
   backup). Send the invite.
3. She'll get an email with a link. Clicking it takes her to the
   site, where a box pops up asking her to set a password.
   - If the popup doesn't appear and it just shows the homepage,
     that's OK — have her go to **flynnandphoenix.netlify.app/admin**
     directly and log in with the email + password she just set.
4. Once logged in, that address — **yoursite.com/admin** — is her
   dashboard from now on. Worth bookmarking.

## Part 5: How Johnna uses it day-to-day

- Go to **flynnandphoenix.netlify.app/admin**, log in.
- Click **Shop Items** → she'll see every product listed.
- Click any item to edit its name, price, photos, or mark it sold —
  or click **New Product** style button to add a brand new one from
  scratch, photo upload included.
- Click **Publish** (or **Save**, then **Publish**) when done. The
  live site updates automatically within about a minute — no
  redeploying, no folders, no Sam.
- **Shop Settings** (also in the sidebar) is where the contact email
  lives, if that ever needs to change.

## What still needs Sam (or Claude)

- Changing the site's design, layout, or wording outside the shop
  items (the Philosophy section, colors, fonts, etc.)
- Adding new *kinds* of fields to the dashboard (e.g., if she later
  wants a "size" field for clothing)
- Anything structural like this setup itself

Everything about the actual inventory — adding, pricing, photographing,
selling, marking sold — is fully hers from here on.

## One technical note, for you

Because the site now *loads* its product data (`products.json`) with
a live fetch instead of having it baked into the page, you can no
longer preview it by just double-clicking `index.html` on your
computer — browsers block that kind of file loading when a page is
opened directly from disk rather than a real web address. This only
affects local testing; the live Netlify site works completely
normally. If you ever want to preview changes before Johnna sees
them, use Netlify's **deploy previews** (it makes one automatically
for any change) rather than opening the file locally.

— Sam
