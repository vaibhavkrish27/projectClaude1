# Workflow — E-Commerce Price & Offer Comparison

Purpose: compare the price, offers, and key details of products across e-commerce platforms and produce a written comparative summary.

- Data source: **the user provides the data.** I do not scrape or fetch live listings.
- Products are identified by **direct listing URLs** where available, and by **product name / variant** where not.
- Final output: a **Markdown summary** in `output/`.
- Platforms: Amazon, Flipkart, and Myntra are the usual set, but **any platform named in the request is accepted** (Nykaa, Ajio, Meesho, Croma, brand sites, etc.).

---

## Comparison modes

The user chooses the mode per run. If the mode is not stated, **ask — do not assume.**

### Mode A — Same product, multiple platforms
- One product, listed on several platforms.
- Example: *the price of a newly launched mobile across Amazon, Flipkart, and Croma.*
- The item is identical, so the comparison is purely **price and offers**.
- Verdict: **which platform is cheapest on effective price.**

### Mode B — Different products, same or different platforms
- Two or more different products, on the same site or across sites.
- Example: *comparing 2–3 laptops, whether listed on one site or spread across several.*
- The items are **not identical**, so price alone does not decide it — specifications matter.
- Verdict: **value for money**, stated against the specs — never a bare "cheapest wins".

### Mode C — Combination
- Several different products, each priced across several platforms.
- Example: *3 laptops, each checked on Amazon, Flipkart, and Croma.*
- Run Mode A within each product to find its best platform, then run Mode B across the products.

---

## Step 1 — Intake

- The user places a request in `inputs/`, based on `inputs/request-template.md`.
- Each request states:
  - **The comparison mode** (A, B, or C).
  - The products (URL and/or name + variant).
  - The platforms.
  - The date the data was captured.
- The user attaches the source data: pasted page text, screenshots, or an exported price sheet.

## Step 2 — Confirm scope (before any analysis)

- Restate back to the user:
  - The mode, the products, the platforms, the variant / configuration.
  - Currency and date of capture.
  - For Mode B and C: **which specifications matter to the decision** (e.g. RAM, processor, battery, screen). Ask if not stated.
- **Every gap is a question to the user — never an assumption.**
- Do not begin the comparison until the user confirms the scope.

## Step 3 — Normalise into a comparison table

### Pricing columns (all modes)

One row per **product × platform**:

| Column | Notes |
| --- | --- |
| Product | As named in the request |
| Variant / configuration | Size, colour, storage, quantity, model number |
| Platform | Amazon, Flipkart, Myntra, … |
| Seller | Seller / fulfiller name |
| MRP | Listed price before discount |
| Selling price | Price shown on the listing |
| Discount % | Derived from MRP and selling price |
| Coupon / bank offer | Stated coupons, card offers, cashback |
| Exchange / bundle offer | Trade-in value, bundled accessories |
| Delivery fee | Shipping charge, if any |
| **Effective price** | Selling price − applicable offers + delivery fee |
| Rating | Star rating and review count |
| Delivery time | Estimated days |
| Stock status | In stock / out of stock |
| Source link | Listing URL |
| Date checked | Date the data was captured |

### Specification columns (Mode B and C only)

A second table, one row per **product**, with the specs the user named in Step 2.
Example for laptops: Processor, RAM, Storage, Display, Graphics, Battery, Weight, Warranty.

- Any field not present in the user's data is recorded as **"Not available"**.
- Never estimate, infer, or fill a missing price, offer, or specification.

## Step 4 — Compare and flag

### Mode A
- Rank platforms by **effective price**.
- Name the cheapest platform and state why (base price, coupon, bank offer, exchange).
- Flag if any listing is **not like-for-like**: different variant, seller, region, or a bundled item that inflates the price.

### Mode B
- Present price **alongside** the specifications — never in isolation.
- State what each extra rupee buys (e.g. *"₹8,000 more for double the RAM and a better processor"*).
- Give a **value-for-money view**, and say plainly which product suits which need.
- Flag where products are **not in the same class** and a direct comparison would mislead.

### Mode C
- First, per product: the best platform (Mode A logic).
- Then, across products: the value comparison at each product's best price (Mode B logic).

## Step 5 — Write the summary

- Save to `output/` as: `price-comparison_<product-or-category>_<YYYY-MM-DD>.md`
- The summary contains:
  - **Scope** — mode, products, platforms, date of data.
  - **Pricing table** — the normalised table from Step 3.
  - **Specification table** — for Mode B and C.
  - **Key findings** — bullet points, not paragraphs.
  - **Offer highlights** — notable coupons, bank offers, exchange and bundle deals.
  - **Recommendation** — cheapest platform (Mode A) or best value (Mode B / C).
  - **Data gaps** — every field marked "Not available", listed so the user can fill them.
  - **Caveats** — any non-comparable listings flagged in Step 4.

## Step 6 — Review and confirm

- Show the summary to the user **before** writing or overwriting any file in `output/`.
- Wait for explicit confirmation to save.
- Tone throughout: **formal and warm**; **points over paragraphs**.
