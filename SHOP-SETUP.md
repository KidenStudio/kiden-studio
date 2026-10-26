# Kiden Studio — setting up the shop

Your site is at **kidenstudio.com**, hosted free on GitHub Pages.
The shop runs on **Payhip** (the cart and checkout) and **Gelato** (prints the
prints and ships them). You only pay when you sell something.

---

## Part 1 — Gelato (the prints)

1. Sign up free at **gelato.com**. No monthly fee.
2. Go to **Products → Wall art → Posters (fine art / museum-quality matte)**.
3. Upload one artwork file. Gelato tells you the maximum size it can print at
   that resolution. Start with A4, A3 and A2.
4. Write down the **production cost + shipping to Ontario** for each size.
   This is your cost. Your selling price is usually 2.5–3× that.
5. **Order one sample of each size to yourself before you sell any.**
   Check the colour against the real painting.

### Getting your paintings ready to print
Photograph each painting straight on, in even daylight, in RAW or the largest
JPEG your phone or camera makes. For an A2 print you want roughly 4000 pixels
on the long edge. Crop to the canvas edge. Phone photos taken at an angle or
under warm indoor light will print badly.

---

## Part 2 — Payhip (the cart)

1. Sign up free at **payhip.com**. The free plan takes 5% of each sale.
   There is no monthly fee.
2. **Settings → Payments** — connect Stripe (and PayPal if you want). Payments
   land in your own account.
3. **Settings → Shipping** — create two zones:
   - *Canada* — flat rate for prints, and a higher flat rate for originals
   - *United States* and anywhere else you'll ship
   Use Gelato's shipping cost as your print rate. For originals, price a
   sturdy box and tracked shipping, and don't underestimate it.
4. **Settings → Store** — add your logo, and set currency to **CAD**.

### Adding a product
For each item, go to **Products → Add new product → Physical product**.

**For an original painting:**
- Title, description, photo
- Price
- Under *Inventory*, set the quantity to **1** — Payhip then marks it sold out
  automatically when it sells, so you can never sell the same painting twice

**For a print:**
- Title, description, photo
- Add a variant called **Size** with the options A4 / A3 / A2, each at its
  own price
- Leave inventory unlimited

### Getting the product key
On the Products page, click **Share / Embed** next to a product, then open the
**Embed Button** tab and choose **Add to Cart**. The code it gives you contains
something like `data-key="AbC12"`. That short code is the product key.

---

## Part 3 — Putting it on your site

Open `index.html` on GitHub, click the pencil icon, and find the SHOP section.

Each item has buttons that look like this:

```html
<a href="#" class="btn payhip-buy-button" data-key="REPLACE-ME">Buy the original</a>
```

Replace `REPLACE-ME` with that product's key:

```html
<a href="#" class="btn payhip-buy-button" data-key="AbC12">Buy the original</a>
```

Also fill in each item's real **size** and **prices** — they currently read
`00 × 00 in` and `$000`.

Click **Commit changes**. Wait a minute, then hard-refresh the site
(**Ctrl + Shift + R**, or **Cmd + Shift + R** on a Mac).

### When a painting sells
Change this line:

```html
<span class="status">Original available</span>
```

to:

```html
<span class="status sold">Sold</span>
```

and delete that item's "Buy the original" line.

### Adding a new work later
Copy one whole `<article class="shop-item"> ... </article>` block, paste it
below, and change the image, title, price and product key.

---

## Part 4 — When an order comes in

1. Payhip emails you the order and the customer's address.
2. **Print order:** log in to Gelato, place the order for that size, and paste
   the customer's address as the delivery address. Gelato prints and ships it.
3. **Original:** pack and ship it yourself, then mark the order fulfilled in
   Payhip.

Connecting Gelato to Payhip so this happens automatically is not supported on
the free plan — it is a few minutes of manual work per order. Worth automating
only once you're getting more than about ten print orders a month.

---

## What this costs

| | Cost |
|---|---|
| GitHub Pages hosting | Free |
| Payhip | Free, 5% per sale |
| Stripe / PayPal | about 2.9% + 30¢ per sale |
| Gelato | Only the production cost of prints you actually sell |

Total of about 8% per sale, and **nothing at all in a month with no sales**.

### When to change
If you pass roughly **$600 a month** in sales, Payhip Plus ($29/month, 2% fee)
becomes cheaper than the free plan. Past about **$3,000 a month**, look at
Shopify Basic — it connects to Gelato directly and fulfils print orders without
you touching them.

---

## Two things to sort out before you launch

**Sales tax.** In Canada you generally don't have to register for GST/HST until
your sales pass $30,000 in four consecutive quarters, but Payhip can add tax
once you do register. Worth a short conversation with an accountant before your
first sale. I'm not one.

**Shipping originals.** Pack flat-packed, corner-protected and insured. Decide
up front whether you ship outside Canada — customs on an original artwork is
a hassle you may not want yet.
