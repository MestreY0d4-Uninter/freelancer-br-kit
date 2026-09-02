---
title: "Google Shopping Product Ratings Feed: generate the XML from your orders CSV"
description: "Generate the Google Product Ratings feed XML from a simple orders + products CSV export. Compatible with Google Merchant Center. No manual XML, no errors — a ready Python script."
---

# Google Shopping Product Ratings Feed — generated from your orders CSV

The star rating next to your product in Google Shopping comes from a **Product Ratings feed** — an XML file that merges three sources: your products (SKU), your orders (who bought), and your reviews (how many stars). Building that file by hand is tedious and error-prone, and one bad tag kills your Merchant Center approval.

This is how to generate it without touching XML.

## Why Product Ratings matter

- Products with ratings in Google Shopping attract **more clicks** than those without
- The stars appear right next to the ad/listing and build trust
- Google requires the feed in a specific **XML structure**, grouped by product

## The structure Google expects

The Product Ratings feed boils down to:

- **Product identification** (GTIN, MPN, or Brand + Name)
- **Multiple reviews per product** — the aggregate of who bought and reviewed
- **Per-review fields**: rating (1-5), title, content, author, date
- Country and currency code (e.g. `BR` / `BRL`)

Each product needs at least **one valid review** for stars to show. The whole feed is re-submitted to Merchant Center periodically.

## The easy way: a Python script

If you already have an **orders CSV** (the one your platform/e-commerce export gives you) and a **products CSV**, the workflow is:

1. **Match** — figure out which orders had reviews and which SKU each maps to
2. **Group** — collect all reviews per product
3. **Generate** — build the XML in the exact format Google expects, in your currency
4. **Submit** — upload to Merchant Center and keep it fresh (recurring run)

No manual XML, no mistyped closing tags, no currency mix-ups.

---

## The ready-made option

The **Google Product Ratings Feed Generator** does exactly this: feed it your orders + products CSVs and get a Google-ready XML feed, in your currency. Built and maintained — not a blank template.

👉 [Download the generator script on Gumroad](https://yodabug.gumroad.com/l/ucbnjz)