# Flynn & Phoenix — How to Start Selling

**Update:** once the dashboard from `ADMIN-DASHBOARD-SETUP.md` is
set up, do all of this — pricing, adding items, marking things sold —
through Johnna's login at `yoursite.com/admin` instead of editing
files by hand. Everything below about Stripe still applies exactly
the same; only *where* you paste the Payment Link changes (into the
dashboard's "Stripe Payment Link" field on that item, instead of a
text file).

The short version below is still useful if you're setting up Stripe
itself, or if you ever want to edit `products.json` directly as a
backup method.

---

## The setup (do this once, about 15 minutes)

1. Go to **stripe.com** and click "Start now." Sign up as a
   business (sole proprietor is fine if that's what you are).
2. Stripe will ask for basic info: your name, address, bank
   account (where your money gets deposited), and a description
   of what you sell ("vintage clothing, art, and collectables").
3. That's it — no monthly fee. Stripe only takes a small cut
   (2.9% + $0.30) when something actually sells. If nothing
   sells this month, you pay nothing.

## Listing an item (do this for every item you want to sell)

1. In your Stripe dashboard, go to **Payment links** → **+ New**.
2. Give it the item name and price, and upload the photo if you
   want. Save it.
3. Stripe hands you a link like `https://buy.stripe.com/abc123`.
4. Open **products.json** (in this same folder) in any plain text
   editor — Notepad, TextEdit, or even Google Docs saved as
   plain text works.
5. Find that item in the list, and paste the link between the
   quotes next to `stripeLink:`.
6. Save the file. Refresh the website. The "Inquire" button on
   that item is now a "Buy Now" button.

Until you paste a link in, the site automatically shows an
"Inquire" button instead, so nothing looks broken — people can
just email you.

## Adding a brand new item that isn't on the site yet

1. Open **products.json**.
2. Copy one whole item block (the part between `{` and `},`)
   and paste it right above the closing `];` at the bottom.
3. Change the name, price, category, and image filename.
4. Save your photo into the **images** folder using that exact
   filename.
5. Save the file, refresh the site — the new item appears.

## Marking something sold

In **products.json**, find the item and change `"sold": false` to
`sold: true`. It'll show a "Sold" ribbon and gray out the button.
Don't delete sold items — better to leave them up for now.

## Where orders go

Stripe emails you (and the buyer) a receipt the moment something
sells. You'll pack and ship it yourself, same as you would with
any handmade or vintage sale — this setup doesn't manage
inventory or shipping labels automatically. For 10–50 items,
that's genuinely the easiest way to run this by hand without
paying for software to do it for you.

## If this ever gets too big for this setup

If you're regularly selling 50+ items a month and juggling
Payment Links feels like too much, the next cheapest step up is
**Big Cartel** (free for 5 products, $9.99–$15/mo beyond that,
0% commission) — it adds a real shopping cart and inventory
tracking. Sam can move everything over in an afternoon whenever
that day comes. No rush.

— Sam
