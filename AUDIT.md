# GEO / SEO audit: four Netlify sites

Audited 12 November 2026 from the live sites: home page, `robots.txt`, `sitemap.xml` and `llms.txt` for each. Subpages on lumindra.co were not audited one by one.

## Scorecard

| Site | Netlify project | AI crawlers allowed | llms.txt | Schema | Visible FAQ + FAQPage | Verdict |
|---|---|---|---|---|---|---|
| sunshootersbargrill.com | `sunshooters-bar-grill` | Yes, explicitly | Yes | Restaurant + BarOrPub, full | Yes, 10 Qs, matching | Strong. Polish only |
| lumindra.co | `lumindra` | Yes, explicitly | Yes | Organization + Person + WebSite | Yes, 7 Qs, matching | Strong. Polish only |
| conscioussystemsbali.com | `conscious-systems-bali` | Default only | **404** | Basic, no prices, no Person | **No FAQ** | Biggest gains available |
| bali-ai-consultant.com | `bali-ai-consultant` | Default only | **404** | Basic, no prices, no @id | 4 Qs visible, **no schema** | Clear gaps |

## Issues

| Severity | Where | Issue | Fix (file in `sites/`) |
|---|---|---|---|
| High | conscioussystemsbali.com/llms.txt | Returns 404. AI assistants get no summary of the offers or prices | `conscioussystemsbali.com/llms.txt` |
| High | bali-ai-consultant.com/llms.txt | Returns 404 | `bali-ai-consultant.com/llms.txt` |
| High | bali-ai-consultant.com footer | Visible text says "Draft privacy and legal copy should be reviewed for your jurisdiction." Reads as an unfinished site to visitors and assistants | `bali-ai-consultant.com/body-edits.md` §1 |
| High | conscioussystemsbali.com | No FAQ section. Assistants have no question-and-answer text to quote about prices, format or The Captain's Map | `conscioussystemsbali.com/faq-section.html` (7 visible Qs + matching FAQPage) |
| Medium | bali-ai-consultant.com | Four FAQ items are visible but have no FAQPage schema | `bali-ai-consultant.com/head-snippet.html` |
| Medium | conscioussystemsbali.com schema | Prices are visible (IDR 750k–1.5jt, 5–8jt, 10jt+, 5,000,000) but not in schema. No Person entity for Mark, no address, no email, no link to the Lumindra entity `@id` | `conscioussystemsbali.com/head-snippet.html` |
| Medium | bali-ai-consultant.com schema | Eight visible prices missing from schema. No `@id`, no WebSite entity, founder and parent brand not linked to lumindra.co entities | `bali-ai-consultant.com/head-snippet.html` |
| Medium | bali-ai-consultant.com vs lumindra.co | TikTok handle differs (`@lumindra.co` vs `@lumindrabali`); two YouTube channels linked. Inconsistent profiles weaken entity matching, and one TikTok link is likely dead | `bali-ai-consultant.com/body-edits.md` §3 |
| Medium | conscioussystemsbali.com, bali-ai-consultant.com robots.txt | Allows everyone by default, but does not name AI crawlers the way your other two sites do | `robots.txt` in each folder |
| Medium | conscioussystemsbali.com title | 79 characters, gets cut off in results, and leads with poetry instead of what you offer | `head-snippet.html`: "Conscious Systems Bali \| Clarity Mapping & 5-Session Journey" (60) |
| Low | conscioussystemsbali.com, bali-ai-consultant.com | No `og:site_name`/`og:locale`/`og:image:alt`; CS has no twitter title/description/image | `head-snippet.html` in each folder |
| Low | sitemaps (CS, BAC) | `lastmod` from September, older than the live content | `sitemap.xml` in each folder |
| Low | sunshootersbargrill.com | No favicon or apple-touch-icon declared, so the tab and Google result show a blank icon. No `og:locale`/`og:image:alt` | `sunshootersbargrill.com/head-additions.html` |
| Low | lumindra.co/sitemap.xml | Lists `llms.txt`, which isn't a page | `lumindra.co/sitemap.xml` |
| Low | bali-ai-consultant.com | Location is only "Bali". Your other sites say Kerobokan | `body-edits.md` §4 (optional) |

## Top three changes, in order

1. **Conscious Systems: add the FAQ section, the new head block and llms.txt.** This site has the most paid offers and the least for assistants to quote.
2. **Bali AI Consultant: remove the "draft legal copy" footer line, add the head block (prices + FAQPage) and llms.txt.**
3. **Fix the TikTok handle mismatch** between bali-ai-consultant.com and lumindra.co so the brands resolve as one entity.

## Checks done here

- Every JSON-LD block parses as valid JSON.
- Every price and fact in the new schema and llms.txt is copied from the visible page. No ratings, reviews or review counts were added.
- Conscious Systems FAQ: visible answers and FAQPage answers match exactly (7 of 7). Bali AI Consultant FAQPage matches the four live FAQ answers word for word.
- New titles are 60 and 61 characters; new CS description is 153.
- All sitemaps are valid XML.

## Checks that need you

- Run each home page through Google's **Rich Results Test** and the **Schema.org validator** after deploying.
- In **Google Search Console**, resubmit each `sitemap.xml` and request indexing for the home pages.
- Watch Search Console impressions for "clarity coaching Bali", "AI consultant Bali" and similar over the next 4 to 8 weeks. None of this guarantees rankings or AI citations; it removes the obstacles.
- llms.txt is an emerging convention. No major assistant is known to require it, but it costs nothing and your two strongest sites already have it.
