# VantagePoint — Project Tracker

**Client:** VantagePoint (fractional CFO, management consulting, accounting services)
**GitHub:** `ffgroup-8/vantagepoint-sitemap` → https://github.com/ffgroup-8/vantagepoint-sitemap
**Local:** `~/Desktop/Git Repo/VantagePoint/index.html`
**Live:** https://ffgroup-8.github.io/vantagepoint-sitemap/
**Figma FileKey:** `QoY1pbVzshvhmhSMpBFA1F`

---

## Master Rules

Follow all rules in `../_Project Tracker Master/CLAUDE.md`. That file is the source of truth for:
- Box hierarchy (`seo-box` → `content-created-box` as siblings)
- CSS patterns (green seo-box, blue content-created-box, dark mode)
- Status pill system (6 categories)
- SEO standards
- Push-automatically rule
- Content writing standard (actual copy, not design annotations)

**Pipeline:** If you add a new pattern here that isn't in Master, also apply it to `../_Project Tracker Master/index.html` and commit both.

---

## Current Progress (as of last session)

| Category        | Progress |
|-----------------|----------|
| Design          | 100%     |
| Dev             | 0%       |
| SEO             | 100%     |
| Content Input   | 6%       |
| Sanity Dev      | 6%       |
| Content Created | 93%      |

---

## Pages (16 total)

| # | Page | Slug | Content Created |
|---|------|------|-----------------|
| 1 | 🏠 Home | `/` | ⬜ needed |
| 2 | 📂 Services Overview | `/services` | ⬜ needed |
| 3 | 📊 Fractional CFO — FLAGSHIP | `/services/fractional-cfo` | ✅ done |
| 4 | 🧭 Management Consulting | `/services/management-consulting` | ✅ done |
| 5 | 🧮 Accounting Services | `/services/accounting` | ✅ done |
| 6 | 🥃 Adult Beverage | `/industries/adult-beverage` | ✅ done |
| 7 | 🍽️ Hospitality | `/industries/hospitality` | ✅ done |
| 8 | 📦 Consumer Packaged Goods | `/industries/cpg` | ✅ done |
| 9 | 🛍️ Retail | `/industries/retail` | ✅ done |
| 10 | 🤝 Working With Us | `/working-with-us` | ✅ done |
| 11 | 🏆 Success Stories | `/success-stories` | ✅ done |
| 12 | 📝 Resources / Blog | `/resources` | ⬜ needed |
| 13 | 🏢 About VantagePoint | `/about` | ⬜ needed |
| 14 | 📞 Free Consultation | `/contact` | ⬜ needed |
| 15 | 🔍 Fractional CFO Services (National SEO) | `/fractional-cfo` | ⬜ needed |
| 16 | 🔍 Accounting Services (National SEO) | `/accounting-services` | ⬜ needed |

---

## Content Module Template (per page)

Follow the Figma designs for each page. Standard module structure:

```html
<p><strong>📌 Module 1 — Hero</strong></p>
<ul>
  <li><strong>Eyebrow:</strong> ...</li>
  <li><strong>Headline:</strong> ...</li>
  <li><strong>Subheadline:</strong> ...</li>
  <li><strong>Primary CTA:</strong> ...</li>
  <li><strong>Secondary CTA:</strong> ...</li>
</ul>
```

After adding content for a page:
1. Mark the Content Created pill `completed` in both the nav-item AND the sitemap node
2. Update `data-target` on the Content Created progress bar: `(completed pages / 16 * 100).toFixed(0)%`
3. Commit and push

---

## Injection Approach (surgical HTML edits)

Use the page's unique **AEO Targets string** as the anchor for injecting `content-created-box`:

```python
aeo_str = "..."  # unique AEO content for that page
full_aeo_p = f'<p><strong>AEO Targets:</strong> {aeo_str}</p>'
old = full_aeo_p + '\n    </div>\n  </div>'
new = full_aeo_p + '\n    </div>\n' + cc_box + '\n  </div>'
c = c.replace(old, new, 1)
```

Always verify div balance after each injection: `c.count('<div') == c.count('</div>')`.

---

## Service Offerings (for content reference)

- **Fractional CFO** — Part-time CFO leadership, financial strategy, forecasting, investor relations
- **Management Consulting** — Operational efficiency, market expansion, strategic planning
- **Accounting Services** — Bookkeeping, reporting, compliance, month-end close
- **Industries:** Adult Beverage, Hospitality, CPG, Retail

**Brand voice:** Confident, strategic, direct. No fluff. Speaks to founders and operators.
