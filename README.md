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

## The spreadsheet

One tab per area: Transactions, Bills, Loans, Accounts, Owed to me, Owed history, Utilities, Settings, plus a Read me tab. Read, filter and chart freely; don't rename tabs or headings, and make edits in the app so the two stay in step. Download for Excel any time with File → Download → Microsoft Excel (.xlsx).
