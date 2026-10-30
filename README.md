# Prudence — Personal and Home Finance

A private web app for running a household's money: daily spending, bills on the 15th and 30th cutoffs, loans and their payoff timeline, salary with payroll deductions, money owed to you, and shared utilities.

Every entry is written as a row in a **Prudence** Google Sheet in your own Google Drive. The app has no server or database of its own; your data goes straight between your browser and Google.

Live site: https://isacad1.github.io/prudence/

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole app |
| `config.js` | Your Google OAuth client ID |
| `sw.js` | Lets the app open offline |
| `manifest.webmanifest`, `icon*.png`, `icon.svg` | Add-to-home-screen name and icons |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## Setup

1. Create a Google Cloud project, enable the **Google Sheets API** and **Google Drive API**, set up the OAuth consent screen (External, add yourself as a test user) and create an **OAuth client ID** of type *Web application* with:
   - Authorized JavaScript origin: `https://isacad1.github.io`
   - Authorized redirect URI: `https://isacad1.github.io/prudence/`
2. Paste the client ID into `config.js`.
3. Upload these files to the `prudence` repository and turn on GitHub Pages (Settings → Pages → Deploy from a branch → `main` / root).
4. Open the site and sign in with Google. Prudence creates the **Prudence** spreadsheet on first sign-in.

## Permissions

Prudence asks only for `drive.file`: it can see and edit files it created itself, nothing else in your Drive.

## Receipts

Bill payments, utility months and work expenses can have receipts attached (photos, screenshots or PDFs). Photos are shrunk before upload. Files are saved in a **Prudence Receipts** folder in your Google Drive and linked from the sheet.

## Daily spending charts

The Daily tab shows **Spending by day**, a bar chart of the week (use ‹ › for earlier weeks) compared with the same days the week before, and **Where it went**, a treemap of the month's daily spending by category. Tap a box to filter your spending log to that category. Bills and loan payments aren't included.

## Owed to me

Each person has a full **History**: their starting balance, every amount lent and paid back, and the running balance after each one. Tap an entry to fix or delete it, and save the history as an image or PDF statement to send them. When you record **Lent** or **Paid back**, choose the account the money left or arrived in (for example GCash) and that account's balance updates. Lending and repayments aren't counted as spending or income.

## Reimbursements

Track work expenses until your employer pays you back: meeting meals (with a per-person cap, ₱150 by default), subscriptions, Grab rides and more. Toggle **Claimed** per item. If a meal goes over the cap and isn't covered, the excess is split equally among everyone who ate and each staff member's share is added to **Owed to me**.

## Housemate billing

On the House tab, **Housemate billing** shows each housemate's share of the month's electricity, water and internet. Tap a name to see the computation (for example ₱2,262.63 ÷ 3 = ₱754.21), copy a ready-to-send message, save the statement as an image or PDF to send (on a phone this opens the share sheet for Messenger, Viber or Photos), and mark it paid. Splits accept fractions like 1/3, so shares match an exact three-way split.

## Transfers

Move money between your own accounts with **Transfer money** (Accounts tab, or from Daily). Transfers don't count as spending; an optional fee is recorded as a Bank fees expense. Prudence remembers the fee for each pair of accounts, so a route with a fee fills it in and a free one stays blank. When you log a payday you can also choose **Then move it to**, for example salary from Landbank to MariBank.

## Savings and investment values

For savings and investment accounts (a VUL, MP2, coop equity), use **Update value** on the Accounts tab with the figure from your statement. Prudence keeps the history and shows how much the fund itself gained or lost, separate from money you added or withdrew. A withdrawal can be sent to one of your accounts so its balance goes up too.

For insurance with an investment fund (a VUL), tap **Track premiums** on that account. Set the monthly premium and the date of your first one, then **Fill in past premiums** to add every month since then in one go. Past premiums aren't taken from any account, so your balances stay right. New premiums can be paid from an account (recorded as an Insurance expense), or link the plan to the bill you already pay on the Bills tab so each payment counts automatically. A chart compares total premiums paid with the fund's value over time.

## The spreadsheet

One tab per area: Transactions, Bills, Loans, Accounts, Owed to me, Owed history, Utilities, Reimbursements, Account values, Premiums, Settings, plus a Read me tab. Older sheets are upgraded automatically: missing tabs and columns are added at the end, and existing rows are left alone. Read, filter and chart freely; don't rename tabs or headings, and make edits in the app so the two stay in step. Download for Excel any time with File → Download → Microsoft Excel (.xlsx).
