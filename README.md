# GEO fix packs for four Netlify sites

Findings are in [AUDIT.md](AUDIT.md). Each folder in `sites/` holds the files for one site.

| Folder | Netlify project | Site ID |
|---|---|---|
| `sites/conscioussystemsbali.com` | conscious-systems-bali | b7395917-763d-474b-a76c-8168f0102059 |
| `sites/bali-ai-consultant.com` | bali-ai-consultant | 01fbba11-a6ee-4309-bf68-dfb322dcdd0b |
| `sites/sunshootersbargrill.com` | sunshooters-bar-grill | 1a8df480-b85f-4d5f-9141-0cd0898e9fa9 |
| `sites/lumindra.co` | lumindra | 8ebdb198-062a-4694-81f2-13be9b2965b0 |

## File types

- `robots.txt`, `sitemap.xml`, `llms.txt`: **whole files.** Drop them into the site root, replacing any existing file.
- `head-snippet.html`, `head-additions.html`, `faq-section.html`: **pieces to paste** into `index.html`. The comment at the top of each file says what to replace and where.
- `body-edits.md`: small find-and-replace edits.

## How to apply (per site, about 10 minutes)

1. Open the project in Netlify > **Deploys** > the current published deploy > **Download** (ZIP). This gives you the exact live files, so nothing gets lost.
2. Unzip it. Copy in the whole files and make the paste edits in `index.html`.
3. Drag the **folder** (not the ZIP, not the files) onto the **same project's** Deploys page. Check the project name at the top before you drop, so it doesn't land on the wrong site.
4. Open the live site and check: the page looks the same, `/llms.txt` loads, `/robots.txt` shows the AI crawler lines.
5. Run the home page through Google's Rich Results Test, then resubmit the sitemap in Search Console.

Order: Conscious Systems, then Bali AI Consultant, then Sunshooters and Lumindra (small polish).

## Deploy status (12 Nov 2026)

`deployed/` holds the exact files uploaded. All other files on each site were left untouched.

| Site | Netlify deploy | Status |
|---|---|---|
| conscioussystemsbali.com | 6af5184baa3525b8381798c0 | **Live** |
| bali-ai-consultant.com | 6af5184f73844c5b434b6479 | **Live** |
| sunshootersbargrill.com | 6af51871539e3ffd96e41d9e | **Ready, not published.** The site is locked; publish it from the Deploys list |
| lumindra.co | — | Not deployed. Builds from GitHub `Fumaster/lumindra`; apply `sites/lumindra.co/sitemap.xml` there |

Conscious Systems and Bali AI Consultant are linked to Netlify-hosted Git repos. Those repos don't contain these changes yet, so a future Netlify agent run or push there would overwrite them. Copy the `deployed/` files into those repos before your next agent run on those sites.
