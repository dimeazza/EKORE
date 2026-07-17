# EKORE

**Your AI financial co-pilot for freelance and gig work — built for Spain and Latin America.**

[ekore.app](https://ekore.app)

> This repository is a public showcase. The product is live; the source code is private.

---

## The problem

Freelancers, autónomos, and gig workers juggle income across clients, currencies, and sometimes crypto — with none of the payroll infrastructure an employee gets for free. Tax rules differ by country, invoices pile up unpaid, and "how am I actually doing this month" is a spreadsheet nobody keeps updated.

EKORE replaces that spreadsheet with a financial dashboard that understands your money, talks back in plain language, and knows the tax rules of the country you operate in.

---

## What's live in production

| Feature | Description |
|---|---|
| **AI financial assistant (AIKore)** | Chat-based advisor grounded in your real income/expense data — ask about VAT, deductions, or your best month and get an answer based on your actual numbers. |
| **Financial dashboard** | Income, expenses, balance, and a financial health score, visualized over time. |
| **Multi-country tax engine** | VAT and income tax rules for Spain, Costa Rica, Colombia, Mexico, Argentina, the UK, France, Germany, and Italy. |
| **Invoicing** | Create invoices, track payment status (pending / sent / paid), auto-fill returning clients by tax ID, and convert accepted quotes into invoices with their own numbering series. |
| **Crypto tax calculator** | Capital gains/losses for BTC, ETH, and major tokens under Spanish tax rules. |
| **Statement import** | Upload a bank statement (PDF or screenshot) and AIKore extracts the movements automatically — CSV import and manual entry also supported. |
| **Log expenses via WhatsApp** | Link your number and record income or expenses by sending a WhatsApp message. |
| **Gamification** | Points, ranks, a leaderboard, and a financial trivia mini-game. |
| **Weekly Pulse & Monthly Wrapped** | Periodic AI-generated recaps of your financial activity. |
| **Referral program** | Invite other freelancers and earn rewards when they join. |
| **Public crypto tools** | Standalone exchange fee comparator and crypto tax calculator, embeddable outside the app. |
| **Subscription billing** | Starter and Pro plans, monthly or annual, with self-serve upgrade/downgrade. |
| **Installable PWA** | Add to home screen, works like a native app on mobile. |
| **Privacy mode & themes** | Blur sensitive amounts with one tap; dark and light themes. |
| **Bilingual UI** | Spanish and English, with the tax engine already covering additional jurisdictions ahead of full UI translation. |

## Currently in development

- **Deduction radar** — proactively flags deductible expenses you might be missing before quarter-end.
- **Payment reminders** — automatic nudges to clients when an invoice goes unpaid past its due date.

## On the roadmap

- **Direct bank connection** — import movements straight from your bank, no CSV needed.
- **Full multi-language UI** — French, German, and Italian, extending the tax engine's existing coverage into the interface.

---

## Screenshots

<p align="center">
  <img src="screenshots/dashboard.png" alt="EKORE dashboard" width="80%" />
</p>
<p align="center">
  <img src="screenshots/aikore.png" alt="AIKore AI assistant" width="80%" />
</p>
<p align="center">
  <img src="screenshots/tax-separation.png" alt="Tax separation view" width="80%" />
</p>

---

## Architecture (conceptual)

EKORE is a React + TypeScript progressive web app backed by Supabase (Postgres, Auth, and serverless edge functions) and Stripe for subscription billing. AI features are powered by Claude, called exclusively from server-side functions so no model credentials are ever exposed to the client. The app is deployed on Vercel.

```
React + TypeScript PWA  ─┐
                          ├─→ Supabase (Postgres · Auth · Edge Functions) ─→ Claude (AI)
Stripe (billing)        ─┘
```

---

## Why this repo is private

EKORE handles real financial data for paying users. The source stays private for security reasons; this repository exists to document the product and its progress publicly.

Product: **[ekore.app](https://ekore.app)**
