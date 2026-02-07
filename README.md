# Couple Budget — GitHub Pages + Google Sheets (Transaction Entry)

This repo is a tiny dark-themed page (`index.html`) that lets you add transactions with dropdowns.
It writes to your Google Sheet using a Google Apps Script web app.

## 1) Set up the Apps Script inside your Google Sheet
1. Open your spreadsheet.
2. **Extensions → Apps Script**
3. Paste `apps-script/Code.gs` into the editor.
4. Confirm sheet names in CONFIG:
   - `txSheetName` (default: Transactions)
   - `listsSheetName` (default: Lists)

### Optional (recommended): Set a secret token
Apps Script → **Project Settings → Script Properties**
- Key: `API_TOKEN`
- Value: a long random string

## 2) Deploy Apps Script as Web App
Apps Script → **Deploy → New deployment → Web app**
- Execute as: Me
- Who has access: Anyone (or Anyone with the link)
Copy the web app URL (ends with `/exec`).

## 3) Configure index.html
In `index.html`:
- Set `SCRIPT_URL` to your web app URL.
- Set `API_TOKEN` to your token (if used).

## 4) Host on GitHub Pages
- Push this repo to GitHub
- Settings → Pages → Deploy from branch → main / root
- Open the Pages URL and start adding transactions.

## Lists sheet format (dropdown sources)
If you have a tab named `Lists`, columns A–F (from row 2):
- A: People
- B: Types
- C: Payment methods
- D: Categories
- E: Subcategories
- F: Accounts
