# Lil Smoke — One-Page Build Plan (v3 — FINAL DRAFT)

**Mode:** Agent / planning only. **No code written, no website files changed.** Only this planning document (`BUILD_PLAN.md`) was updated.
**Status:** FINAL DRAFT — decisions locked, except 3 confirm notes in §8. **NOT approved to build** (round 2, Q8 = "Wait"). I stay in planning until you say "Approved to build".

**Intent:** A reusable **template to sell to dispensaries**, with **"Lil Smoke"** as the demo business. It ships with `[SQUARE-BRACKET PLACEHOLDERS]` for all business-specific facts; the buyer replaces them. Plain static HTML + one custom CSS file + tiny vanilla JS (age gate only). No frameworks, libraries, backend, external fonts or assets.

---

## 1. Sitemap & purpose

| File | Purpose |
|---|---|
| `index.html` | **Home** — name, location, informational-only positioning; links to Range & Visit. |
| `range.html` | **Range** — honest "no product list yet" copy (see §3). |
| `visit.html` | **Visit** — single location: `[FULL ADDRESS]`, `[SUBURB, CITY]`, `[OPENING HOURS]`, `[PHONE]`, `[EMAIL]`, `[WHATSAPP NUMBER]`; text directions, no embedded map. |
| `about.html` | **About** — `[LEGALLY APPROVED DESCRIPTION]`. |
| `legal.html` | **Legal** — 18+ notice, no medical advice, stock/prices disclaimer, `[LEGAL ENTITY NAME]`, `[PRIVACY NOTICE]`. No licence or medical claims. |
| `404.html` | **Not found** — link back to Home. ✅ Confirmed. |
| `styles.css` | The one custom CSS file. |
| `age-gate.js` | The only JS — the 18+ age gate. |
| `README.md` | Customization guide: which placeholders to replace + demo example values. ✅ Approved (round 2, Q6). A doc, not a page. |

Shared header/footer carry this line on **every** page:
**"18+ only. No medical advice. Stock and prices subject to confirmation."**

---

## 2. Home — maximum 4 sections

1. **Hero** — "Lil Smoke" + `[LEGALLY APPROVED DESCRIPTION]` + `[SUBURB, CITY]`.
2. **What this site is** — informational only; no sales, ordering or delivery.
3. **Visit** — location snippet → `visit.html`.
4. **Compliance note** — the line above → `range.html`.

The 18+ age gate is a JS overlay (not a Home section). No hype copy.

---

## 3. Range page — exact honest wording (no product list exists)

> **Range**
>
> We don't publish a product list on this website yet. Our current range and prices are available in store and may change. For up-to-date information, please visit us in [SUBURB, CITY] or contact us directly.
>
> 18+ only. No medical advice. Stock and prices subject to confirmation.

**Only change from v1:** "Hatfield, Pretoria" → `[SUBURB, CITY]`, because you chose a generalized location (round 2, Q2). The demo/example rendering ("please visit us in Hatfield, Pretoria") is recorded in `README.md`, not in the page.

No rand amounts, strains, categories, THC/CBD values, stock levels, prices or effects appear anywhere until a verified product list is supplied and cleared (§7).

---

## 4. Plain HTML/CSS/JS file tree

```
/
├── index.html
├── range.html
├── visit.html
├── about.html
├── legal.html
├── 404.html
├── styles.css
├── age-gate.js
└── README.md        (customization guide — approved, round 2 Q6)
```

`BUILD_PLAN.md` is this planning document and already exists in the repo.

No images, fonts, icons, analytics or embedded map. Design tokens: off-white bg, dark text, one deep-green accent **`#1F3A2E`**, one system font, max-width 1100px, 1px borders, 6px radius. No gradients, glows, glassmorphism, shadows, scroll effects, carousels, emojis, cannabis-leaf graphics or icon grids.

---

## 5. Placeholders shipped at launch

`[LEGALLY APPROVED DESCRIPTION]`, `[SUBURB, CITY]`, `[FULL ADDRESS]`, `[OPENING HOURS]`, `[PHONE]`, `[EMAIL]`, `[WHATSAPP NUMBER]`, `[PRIVACY NOTICE]`, `[LEGAL ENTITY NAME]`. No product list, no rand amounts.

Demo/example values recorded in `README.md` (not hard-coded in pages): business "Lil Smoke", location "Hatfield, Pretoria", hours "9am–6pm". See §8 note B about the business name.

---

## 6. Decisions log

**Round 1 (v2 §6):** template-for-dispensaries intent; description = `[LEGALLY APPROVED DESCRIPTION]`; hours 9am–6pm; contact = "the important ones"; legal entity N/A → placeholder; `404.html` yes; WhatsApp yes with placeholder; age gate "for that visit"; accent `#1F3A2E`; use placeholders.

**Round 2 answers → interpretation:**

| # | Your answer | Interpretation | Status |
|---|---|---|---|
| 1 | "Placeholders" | Address = `[FULL ADDRESS]`; no invented street address | ✅ Locked |
| 2 | "Generalized" | Location = `[SUBURB, CITY]` placeholders so any dispensary can drop in its own location | ✅ Locked (see §8 A) |
| 3 | "Yes" | ⚠️ Ambiguous (either/or question). Default: `[OPENING HOURS]` placeholder, with "9am–6pm" as an example in README | ⚠️ Confirm (§8 C) |
| 4 | "Yes" | Contact = `[PHONE]` + `[EMAIL]` + WhatsApp link only; no form, no live chat | ✅ Locked |
| 5 | "Yes" | Age gate = session-only `sessionStorage`; re-ask on a new visit; no long-term cookie | ✅ Locked |
| 6 | "Yes" | Add `README.md` customization guide | ✅ Locked |
| 7 | "No" | Nothing supplied for legal checks; all legal items remain placeholders | ✅ Locked |
| 8 | "Wait" | Do **not** build yet. Stay in planning. | ✅ Locked |

---

## 7. Legal checks you must complete (with a qualified South African professional — this plan is not legal advice)

- **Before showing prices:** obtain a verified product list AND written confirmation that publicly advertising these products/prices is lawful; keep the disclaimer; add **no rand amounts** until then.
- **Before describing the business:** get the exact legally reviewed description; remove any "licensed", "lab-tested", "medical-grade", medicinal or health-effect claims; confirm compliance with applicable SA law and advertising standards.
- **Before using WhatsApp:** confirm it is lawful for the business; comply with POPIA (consent, `[PRIVACY NOTICE]`, data handling) and WhatsApp Business terms. The WhatsApp link is **info-only contact, not ordering or sales** — no online sale/ordering. No cookie/consent banner is added (out of scope); if your use case needs one, that is a separate decision.
- **Template-specific:** because the template is resold to cannabis businesses, it ships with **zero** pre-filled legal claims. Each buyer must supply their own approved description, verified product list, and WhatsApp/POPIA compliance. I provide placeholders only.
- **Site-wide, always:** 18+ age gate; "No medical advice"; the full compliance line on every page.

---

## 8. Three things to confirm before build

**A. Generalized location vs the master rule.** You chose `[SUBURB, CITY]` placeholders, while the master rule fixes "Hatfield, Pretoria". My default: use `[SUBURB, CITY]` in the pages and list "Hatfield, Pretoria" as the demo example in `README.md`. Say the word if you'd rather keep "Hatfield, Pretoria" hard-coded.

**B. Business name in a resale template.** The master rule requires the exact name **"Lil Smoke"**. My default: keep "Lil Smoke" in the pages, and note in `README.md` that buyers replace it. If you'd prefer `[BUSINESS NAME]` as a placeholder instead, tell me — that would override the master rule.

**C. Q3 ("Yes") was ambiguous.** My default: `[OPENING HOURS]` placeholder in `visit.html`, with "9am–6pm" shown as an example in `README.md` — nothing hard-coded in the pages. Alternatively, hard-code "9am–6pm" as demo content. Please pick one.

---

## 9. Planned Code-mode file changes (pending your approval)

I will create/modify **only**: `index.html`, `range.html`, `visit.html`, `about.html`, `legal.html`, `404.html`, `styles.css`, `age-gate.js`, `README.md`. Nothing else. Per your process rule, I will re-list these and wait for approval before editing.
