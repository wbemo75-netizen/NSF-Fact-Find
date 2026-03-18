# NSF Client Fact-Find
### National Service Financial — Interactive Client Onboarding Tool

> A self-contained HTML form for capturing client financial data from ADF members, veterans and their families. Designed for use with the NSF Financial Transition Programme and general client onboarding.

---

## Overview

The NSF Client Fact-Find is a single-file HTML application that replaces the traditional paper-based fact-find process. It features a live financial dashboard that auto-calculates as clients fill it in, a clean PDF export via the browser's native print engine, and a pre-filled demo mode for training and demonstrations.

Built to match NSF's navy-and-gold brand identity. No backend required — everything runs in the browser.

---

## Features

| Feature | Detail |
|---|---|
| **Live Financial Dashboard** | Auto-calculates total income, expenses, assets, liabilities, net worth and monthly surplus/deficit as fields are completed |
| **6 Smart Sections** | Personal Details, Income, Living Expenses, Assets, Liabilities, Adviser Notes |
| **Dropdown Menus** | ADF-specific options throughout — super funds, employment status, DVA card types, referral sources |
| **Completion Progress Bar** | Sticky bar shows percentage complete as the form is filled |
| **Owner Attribution** | C1 / C2 / Joint toggle buttons on every asset and liability row |
| **Auto-calculated Totals** | Expense columns sum automatically across Client 1, Client 2 and Joint |
| **Information Valid Until** | Auto-populates 12 months from completion date (ASIC best practice) |
| **PDF Export** | Native browser print — sharp output, black-and-white with gold accents, A4 portrait |
| **Pre-filled Demo Mode** | Loads a fictional ADF client (Matt & Rebecca Harrington) for demonstrations |
| **Clear Form** | Resets all fields with a single click |
| **Zero Backend** | Fully self-contained — no server, no database, no login required |

---

## File Structure

```
NSF_Fact_Find.html    ← Single file — everything is contained here
README.md             ← This file
NSF_Client_Fact_Find.docx  ← Word version for Teams/SharePoint sharing
```

The HTML file is approximately **120KB** and has two external dependencies (both load from CDN):

- **Google Fonts** — Bebas Neue, Source Sans 3, Source Serif 4 (requires internet connection)
- **No other dependencies** — PDF is generated via `window.print()`, no libraries required

> **Offline use:** If the form needs to work without internet access, the Google Fonts link can be removed and replaced with system font fallbacks. Contact your developer.

---

## How to Use

### For Clients (filling in the form)

1. Open `NSF_Fact_Find.html` in any modern browser (Chrome, Edge, Firefox, Safari)
2. Fill in each section — the dashboard updates automatically as you type
3. When complete, click **Save as PDF** — the browser print dialog opens
4. Select **Save as PDF** as the destination and save
5. Email the PDF to **info@nationalservicefinancial.com.au**

### For the NSF Team (sending to clients)

1. Email the file directly as an attachment — clients double-click to open in their browser
2. Or host it publicly (see [Hosting](#hosting) below) and share the URL
3. The pre-filled demo version loads automatically — clients can clear it with the **Clear Form** button and enter their own details

### For Demonstrations

The form loads pre-filled with a fictional ADF client profile:

- **Matt Harrington** — Sergeant (E7), Australian Army, 14 years service
- **Rebecca Harrington** — Registered Nurse (part-time)
- Location: Townsville QLD | 2 dependants
- Income: $91,500 + $42,000 pa
- Assets: $625k property, $142k ADF Super, $38.5k civilian super, $18.5k ETFs
- Liabilities: $398k home loan (CBA), $18.5k vehicle loan, $3.2k credit card

Use this for workshop demonstrations, training, and client education sessions.

---

## PDF Output

The PDF is produced using the browser's native print engine — **not** a third-party library. This gives:

- Sharp, correctly-fonted text at any zoom level
- Proper A4 page sizing with 12mm margins
- Black-and-white base with gold accents on headers and section numbers
- Dark section headers with white text for clear visual hierarchy
- All empty fields print as clean input boxes
- Inactive financial flags fade to 20% opacity; active flags (surplus, deficit, warnings) remain full colour

**To save as PDF:** Click **Save as PDF** in the form → browser print dialog → Destination: **Save as PDF** → Print.

---

## Sections

| # | Section | Contents |
|---|---|---|
| 01 | **Personal Details** | Names, contact, DVA/PMKeys, DOB, housing, employment, dependants, goals |
| 02 | **Income** | Salary, DVA pension, Centrelink, rental, investment, other income |
| 03 | **Living Expenses** | 13 expense categories across C1, C2 and Joint — auto-totalled |
| 04 | **Assets** | Property, savings, vehicles, superannuation, investments, DVA lump sum |
| 05 | **Liabilities** | Home loans, vehicle loans, credit cards, BNPL, other debt |
| 06 | **Adviser Notes** | Meeting notes, DVA/claims status, action items, risk profile, referral source |

---

## Financial Dashboard

The live dashboard at the top of the form displays six KPIs that update in real time:

| KPI | Calculation |
|---|---|
| **Total Income** | Sum of all income inputs, annualised |
| **Total Expenses** | Sum of all expense inputs, monthly |
| **Monthly Surplus/Deficit** | Income ÷ 12 minus monthly expenses |
| **Total Assets** | Sum of all asset value inputs |
| **Total Liabilities** | Sum of all balance owing inputs |
| **Net Worth** | Assets minus liabilities |

**Smart flags** activate automatically:
- ⚠ Cash Flow Deficit / ✓ Positive Cash Flow
- ⚑ High Debt-to-Asset Ratio (triggers when liabilities exceed 60% of assets)
- ↓ Negative Net Worth
- ◈ Superannuation Recorded
- ⌂ Property Owner

---

## Hosting

The file can be shared in several ways:

### Option 1 — Email Attachment
Send `NSF_Fact_Find.html` directly. Recipients open it in their browser. Works offline except for Google Fonts.

### Option 2 — Netlify Drop (Recommended for quick sharing)
1. Go to [netlify.com/drop](https://netlify.com/drop)
2. Drag `NSF_Fact_Find.html` onto the page
3. Rename it to `index.html` before dropping
4. Get a public URL instantly (e.g. `https://nsf-factfind.netlify.app`)

### Option 3 — GitHub Pages (Recommended for permanent hosting)
1. Create a GitHub repository named `nsf-factfind`
2. Upload `NSF_Fact_Find.html` renamed as `index.html`
3. Settings → Pages → Source: main branch
4. Live at `https://yourusername.github.io/nsf-factfind`

### Option 4 — NSF Website
Ask your web developer to upload to `nationalservicefinancial.com.au/factfind`

---

## Browser Compatibility

| Browser | Status |
|---|---|
| Chrome / Edge (Chromium) | ✅ Full support |
| Firefox | ✅ Full support |
| Safari (macOS / iOS) | ✅ Full support |
| Internet Explorer | ✗ Not supported |

---

## Privacy & Data

- **No data is transmitted** — all form data stays in the browser session
- **No cookies, no tracking, no analytics**
- Completed data only leaves the browser when the client saves the PDF and emails it
- Compliant with the Privacy Act 1988 (notice displayed on the form)
- Form data is **not saved** between sessions — clients must complete and export in one sitting, or use their browser's form autofill

---

## Compliance Notes

- Information Valid Until auto-calculates 12 months from completion date, consistent with ASIC RG 175 requirements for fact-find currency
- The form includes a Privacy Notice referencing the Privacy Act 1988
- Footer displays: ABN 58 622 673 330 · Corp Authorised Representative 1281192 · Shartru Wealth Management ABN 46 158 536 871 · AFSL 422409
- The document states it is for information collection purposes only and does not constitute financial advice

---

## Version History

| Version | Date | Notes |
|---|---|---|
| 1.0 | March 2026 | Initial release — 6 sections, live dashboard, PDF export |

---

## Contact

**National Service Financial**  
Suite 302, 1 Bryant Drive, Mariners Centre of Excellence, Tuggerah NSW 2259  
T: 02 4347 9444  
E: info@nationalservicefinancial.com.au  
W: nationalservicefinancial.com.au

*Veteran-Owned · ADF Financial Specialists*
