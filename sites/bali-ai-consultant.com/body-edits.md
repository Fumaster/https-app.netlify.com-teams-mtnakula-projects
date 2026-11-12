# Bali AI Consultant: body edits (index.html)

Small find-and-replace edits. Do them in a text editor; nothing else on the page needs to change.

## 1. Remove the placeholder legal line from the footer (High)

The live footer says *"Draft privacy and legal copy should be reviewed for your jurisdiction."* Visitors and AI assistants read this as an unfinished site.

Find:
```html
<p class="copyright">Copyright <span data-year>2026</span> Bali AI Consultant. Draft privacy and legal copy should be reviewed for your jurisdiction.</p>
```
Replace with:
```html
<p class="copyright">Copyright <span data-year>2026</span> Bali AI Consultant, a Lumindra company. Founded by Mark Tulloch. Bali, Indonesia. Prices in Indonesian Rupiah. WhatsApp +62 821 4402 9645.</p>
```

## 2. Add three answer-first FAQ items (Medium)

The current FAQ covers technical scope only. Add these inside `<div class="faq-list">`, before the first `<details>`. Then add the matching three questions to the FAQPage block in `head-snippet.html` (copy the question and answer text exactly).

```html
<details class="reveal">
  <summary>What does Bali AI Consultant do?</summary>
  <p>Bali AI Consultant builds practical AI systems for Bali businesses: AI training, WhatsApp automation, websites and custom AI-powered business operating systems for staff, rosters, SOPs, daily operations and dashboards. It is a Lumindra company founded by Mark Tulloch.</p>
</details>
<details class="reveal">
  <summary>How much does it cost?</summary>
  <p>Prices are starting estimates in Indonesian Rupiah. AI Starter training is Rp 2,000,000, WhatsApp automation and websites start at Rp 5,000,000, and business operating systems start at Rp 10,000,000. Final scope is confirmed after discovery.</p>
</details>
<details class="reveal">
  <summary>How long does a build take?</summary>
  <p>A Foundation operating system typically launches in 2 to 3 weeks. Operations Pro takes 3 to 5 weeks and Connected Intelligence 5 to 8 weeks.</p>
</details>
```

## 3. Make social handles consistent across your sites (Medium)

AI assistants link entities by matching profiles. These differ today:

| Profile | bali-ai-consultant.com | lumindra.co |
|---|---|---|
| TikTok | `@lumindra.co` | `@lumindrabali` |
| YouTube | `@LumindraBali` and `@BaliAiConsultant1` | `@lumindrabali` |

Pick the correct TikTok handle and use it on both sites (one of the two links is likely broken).

## 4. Optional: say where you are (Low)

The page says "Bali" but never the town. If you're happy for it to appear, add "Kerobokan, Bali" to the footer line above and add `"addressLocality": "Kerobokan"` to the schema address. It matches lumindra.co and conscioussystemsbali.com.
