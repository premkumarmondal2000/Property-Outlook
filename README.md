    # Property Value Outlook

A sales-conversation tool that shows a prospect the projected value of a home after **X years**, where X is whatever the prospect asks for. Built as a product prototype for Godrej Properties projects in **Thane, Navi Mumbai and South Mumbai (SoBo)**.

**Live demo:** https://premkumarmondal2000.github.io/Property-Outlook/

> This is an independent prototype made for a product-management exercise. It is not an official Godrej Properties product, and the Godrej name and logo belong to their owners. All prices in the demo are placeholders.

## The problem

When a prospect asks "What will this be worth in 5 years?", a salesperson usually answers from gut feel ("prices always go up") or opens a spreadsheet, which kills momentum. The answer is vague, hard to trust, and arrives at the moment the buyer is deciding.

## What the tool does

1. Salesperson picks a **project** (9 Godrej projects across three regions).
2. Picks a **typology** (2 / 3 / 4 BHK) and enters the **current price range** in rupees lakh.
3. Sets the prospect's **horizon in years** with a slider or by typing (1 to 30 years).
4. Reads out a **conservative / base / optimistic** projection, shown as a range, with gain in percent and a growth chart.
5. Opens the **"Why this region?"** panel to talk through the major developments behind the market (with a status tag on each: operational, under construction, in development, planned).
6. Taps **Copy summary for prospect** to paste an illustrative summary into WhatsApp.

Growth-rate assumptions are visible and editable on screen, each with its source note.

## How the projection works

```
Future value = Current price x (1 + g) ^ X
```

`g` is the annual growth rate for the project's micro-market, with three scenarios:

| Scenario | Logic |
|---|---|
| Conservative | Recent observed pace of ANAROCK quoted prices (about 3% a year in Worli, Lower Parel and Kolshet Road; about 5.5% in Panvel) |
| Base | Near the MMR average growth of about 4% a year (ANAROCK, Q2 2026). Placeholder |
| Optimistic | Trailing multi-year trend where sourced (Thane about 13% a year over three years, ANAROCK); otherwise base plus a spread. Placeholder |

Where a micro-market has no separate price line in the ANAROCK reports (Vashi, Sanpada, Ghodbunder Road, Bhayandarpada, Mahalaxmi, Wadala), the tool uses a nearby proxy and says so in the assumptions panel.

## Design choices

- **Ranges, not a single number**, so a salesperson cannot present one figure as a promise.
- **Permanent disclaimer** on screen and in the shared summary: illustrative projection, not a guarantee.
- **Visible assumptions** with a source for each rate, so the numbers can be challenged and defended.
- **Different assumptions per region**, because Thane, Navi Mumbai and SoBo are different buyer markets.

## Data sources

- ANAROCK Residential Market Viewpoints, MMR Q2 2025 and Q1 2026 (micro-market quoted prices; growth rates computed from the two reports).
- ANAROCK Q2 2026 coverage (MMR average price growth of about 4% year on year).
- ANAROCK data on Thane (46% price growth over three years), as reported by Storyboard18.
- Infrastructure statuses from Indian Infrastructure, Airport Technology, Free Press Journal, Address Advisors, LAEX and developer blogs. Statuses were checked in October 2026 and should be re-verified before use.

## Known limitations

- **Prices are placeholders.** The price ranges are region-level dummy bands, not Godrej's actual project prices.
- Base and optimistic rates for some markets are placeholder assumptions, not research findings.
- ANAROCK figures are quoted (asking) prices, not registered transaction prices.
- Compounding a high rate over a long horizon produces large numbers; a cap or warning is planned.
- Infrastructure supports demand but does not guarantee price growth.
- RERA and advertising norms for showing projections to buyers need review by a legal or compliance team before real use.

## Roadmap

- **v2:** live price sheet per project, FD / equity comparison, rental yield, PDF summary, a cap on the optimistic case.
- **v3:** CRM integration (log what was shown to each lead), registration-data feeds, analytics linking tool usage to conversion.

## Tech

A single static `index.html` file with no build step and no dependencies other than a Google Fonts stylesheet. To run it locally, open the file in a browser.

## Author

Prem Kumar Mondal
https://www.linkedin.com/in/prem-kumar-mondal-736bb2229

    
