# cabglass.co.nz – rebuilt static site

Plain static HTML/CSS (no build step, no JavaScript, no external fonts, trackers or secrets).
Publish the repository root as-is on Netlify (`netlify.toml` sets `publish = "."`; redirects are in `_redirects`).

## Business details used
Cab Glass (cabglass.co.nz) · 133c Pilkington Road, Panmure, Auckland 1072 · **0800 321 800** · machglass@gmail.com ·
Open 7am to 11pm, 7 days · direct bills all insurers · mobile and in-store glass **replacement**.
The business does not do chip repairs: wherever the old site talked about "repair", the pages now say we replace glass and refer
stone-chip repairs to **Quality Windscreen Repair on 0800 202 888** (the word "repair" is kept in headings/URLs for search).

## What the original site was
A WordPress/WooCommerce (Flatsome theme) site. It went through three phases in the Internet Archive:
1. **2023** – an unconfigured theme demo ("CabGlass", +47 phone number, fashion demo text) – nothing used.
2. **2024 (Mar–Apr)** – the real **CabGlass** machinery site: "Auckland's Best 7 Day Cab Glass Service", 51 "Manufacturer Brands"
   (Ahlmann … Zetor) with 309 machinery model "products", 290 area/suburb pages in 6 regions, 25 insurer pages.
3. **Late 2024 – Feb 2026** – the same generic car catalogue used on the sibling sites (73 car makes, ~1,350 car-model pages,
   34 insurer pages, footer "Windscreen-World"), still titled "Cab Glass".

The rebuild uses the 2024 machinery content as the site's own identity (that is what "cab glass" means and what made the site
different from the sibling sites), and keeps the 2025/26 service text, insurer list and car makes as secondary content.

## Wayback captures used
| Content | Original URL | Capture(s) |
|---|---|---|
| Home page (latest): service boxes, Services Offered list, Request for Service form options, insurer drop-down | `/` | `20260205080652` (also checked `20260120211106`, `20260126203935`) |
| Home page (machinery era): hero + "Large Stock / Mobile Service / Professional Service / Quality Guaranteed" boxes | `/` | `20240325195718` |
| Manufacturer Brands index | `/manufacturer-brands/` | `20240424151834` |
| 51 brand pages with all 309 model names (e.g. JCB `20240424165006`, Caterpillar `20240424151629`, Volvo `20240424164033`) | `/<brand>/` | 2024-04-24 (`20240424143630` – `20240424165038`) |
| Model page template (JCB 1CX) | `/1cx/` | `20240425140502` |
| Areas Serviced + 6 region pages (290 suburbs) | `/areas-serviced/`, `/auckland-central-areas/` etc. | `20240424163659`, `20240424164215`, `20240505133315`, `20240424154517`, `20240424164701`, `20250129200416`, `20240424153735`, `20240424152616`, `20240424152728`, `20250129200717` |
| Suburb page template (Albany) | `/albany-auto-glass-windscreen-replacement/` | `20240412173943` |
| Insurance Glass Claims index (machinery era) | `/insurance-glass-claims/` | `20240424155613` |
| Insurer page template | `/windscreen-insurance-with-aa-…/`, `/windscreen-insurance-with-protecta-…/` | `20240423113509`, `20250321163528` |
| Windscreen Replacement / Windscreen Repair pages | `/windscreen-replacement/`, `/windscreen-repair/` | `20240915163106`, `20240914231425` |
| Car model page template (for wording only) | `/chrysler-300c-windscreen-glass-replacement/` | `20260114193512` |
| URL list (for redirects) | CDX API `url=cabglass.co.nz/*`, status 200, text/html | fetched 2026-10-26 |

## Page list (101 pages + 404)
`/`, `/cab-glass/`, `/windscreen-replacement/`, `/windscreen-repair/`, `/manufacturer-brands/` + 51 brand pages at their
original URLs (`/jcb/`, `/caterpillar/` …; Daewoo moved from `/daew-oo/` to `/daewoo/`), `/vehicle-make/`, `/insurance-glass-claims/`
+ 34 pages at `/insurance/<insurer>/`, `/areas-serviced/` + 6 region pages at their original URLs, `/about/`, `/contact/`
(Netlify Forms), `/thanks/` (noindex), `/404.html`.

## Changes from the original
- Header number 0800 757-985 removed everywhere; only 0800 321 800 is used. No other company's numbers or branding
  (e.g. "Windscreen-World", theme demo text) were kept.
- "auto glass repair(s)" wording changed to replacement wording, with the chip-repair referral above.
- Machinery model names cleaned lightly: brand prefix removed, obvious typos fixed ("ONW ARDS", "WORLDW IDE", "GLAEO",
  "SER6IES", "W H609", "D65W X"), duplicate entries/duplicate names inside a list removed (309 → 307 rows).
- Car make spelling fixed: "Bently" → Bentley, "Lamborgini" → Lamborghini. **Ram removed** (American pick-ups).
- Individual model pages (309 machinery, ~1,350 car) and suburb pages (290) are not recreated – they were thin template pages.
  Every captured old URL 301-redirects to its brand page, region page or `/vehicle-make/` (see `_redirects`, ~2,100 lines).
- Old insurer URLs redirect to `/insurance/<insurer>/`; www redirects to the apex domain.
- Original images (logo PNG, product image) were not reused; a text logo and an SVG machine illustration are used.

## Added by rebuild – needs owner check
- The list of machine types on `/cab-glass/` and the home page (excavators/diggers, backhoe loaders, wheel loaders, skid steers,
  dozers, dump trucks, rollers, telehandlers, tractors) – inferred from the model catalogue, not stated on the old site.
- "door, side, rear and roof glass" for machinery, and "we can come to your site or farm".
- "Quality Guaranteed" box text ("We only use the best quality materials… guarantee our workmanship") – taken from the
  old insurer/service template, as the 2024 box had a heading only.
- Some long model names were already cut off in the original catalogue; they end with "…" (JCB Fastrac, JCB 528.70 Series 2,
  Komatsu Galeo/Dash 5, Fendt). Owner may want to complete them.
- Whether GMC/Hummer/Dodge/Chevrolet should stay in the car make list (kept because they are makes, not only pick-ups).
- The insurer list (34) is from 2025/26; check all are still current (e.g. Star, Swan, GT, IAG are old names).
- The "life you own the vehicle" workmanship guarantee and WINZ Quotes wording come from the old site – confirm still offered.
- Contact form fields (make & model, rego/serial, glass required, insurer, location) are a rebuild choice based on the old form.

## Netlify notes
- The contact form uses Netlify Forms (`data-netlify="true"`). Turn on form notifications to machglass@gmail.com in the Netlify UI.
- Set the custom domain to `cabglass.co.nz` (www redirects to the apex via `_redirects`).
