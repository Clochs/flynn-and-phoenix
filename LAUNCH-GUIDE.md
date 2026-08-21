# Flynn & Phoenix — How to Launch the Website

Two separate things, both cheap:
1. **Hosting** — putting the files somewhere the internet can see them. Free.
2. **A domain name** (flynnandphoenix.com) — optional, ~$10/year.

You can launch today with just #1 and add #2 later whenever you want.
Nothing below requires knowing how to code.

---

## Part 1: Get the site live (free, ~10 minutes)

We'll use **Netlify** — a hosting company with a genuinely free plan
built for exactly this kind of site, and the easiest setup of any
option: you literally drag a folder onto a webpage.

1. Go to **netlify.com** and click "Sign up." Use your email or sign
   up with Google — either is fine. No credit card required for the
   free plan, and you won't need one unless you outgrow it (you won't,
   at this size).
2. Once you're logged in, look for a page that says something like
   **"Deploys"** or has a big dashed box that says **"Drag and drop
   your site output folder here."** (Netlify sometimes calls this
   "Sites" — there's a drop zone on the main dashboard.)
3. On your computer, unzip the Flynn & Phoenix folder if you haven't.
   Drag the **whole folder** (the one containing `index.html`,
   `products.js`, and the `images` folder) onto that drop zone.
4. Wait about 30 seconds. Netlify gives you a live web address right
   away — something like `random-words-123456.netlify.app`. Click it.
   That's your website, live on the internet, for anyone to visit.

That's it — the site is live. It's currently at a random Netlify
address, which is fine to share, but let's clean that up next.

## Part 2: Get a nicer free web address (still $0)

1. In Netlify, go to **Site settings** → **Change site name** (or
   "Site details" → there's an option to edit the name).
2. Change it to something like `flynnandphoenix` — your address
   becomes **flynnandphoenix.netlify.app**. Free, forever, no catch.

If you're happy sharing a `.netlify.app` address (plenty of small
shops do), you're done — skip to Part 4 for how to update the site later.

## Part 3: Get flynnandphoenix.com (optional, ~$10/year)

This is the only part of launching that costs money — and it's a
genuinely small amount if you buy it in the right place.

1. Go to **porkbun.com**. It's a domain registrar (a place that sells
   domain names) with honest, flat pricing — no "$1 first year, $25
   after" tricks that some others pull.
2. Search for `flynnandphoenix.com`. If it's taken, try `.shop`,
   `.co`, or a small variation. Buy it — should run about $9–12/year.
   Skip every upsell they offer (email hosting, "premium DNS,"
   website builder — you don't need any of it).
3. Back in **Netlify**: go to **Domain settings** → **Add a domain** →
   type in `flynnandphoenix.com` → follow the on-screen steps.
   Netlify will show you 1–2 lines to copy (called "DNS records").
4. Go back to **Porkbun**, find the DNS settings for your domain, and
   paste in what Netlify gave you. This is the only mildly technical
   step, and both sites walk you through it with copy-paste boxes —
   no typing DNS records from memory.
5. Wait — it can take anywhere from 10 minutes to a few hours for the
   domain to "point" correctly. Netlify also gives you free
   HTTPS (the padlock icon) automatically once it's connected, no
   extra step needed.

## Part 4: Updating the site later

Whenever you add products, change prices, or add photos:

1. Make the changes to your local copy of `products.js` / `images`
   (same as always).
2. Go back to Netlify → your site → **Deploys** tab → drag the
   **whole updated folder** onto the drop zone again.
3. It replaces the live site in under a minute. No undo needed, no
   risk of "breaking" anything permanently — old deploys are saved
   and you can roll back with one click if something looks wrong.

## Total cost, plainly

| | Cost |
|---|---|
| Hosting (Netlify free plan) | $0/month, forever, at this size |
| `flynnandphoenix.netlify.app` address | $0 |
| `flynnandphoenix.com` (optional) | ~$10–12/year |
| Stripe (from the selling setup) | $0 until something sells |

So: **$0 to launch today**, or **~$1/month** if you want the real
`.com` address. Nothing here requires a subscription or a contract.

— Sam
