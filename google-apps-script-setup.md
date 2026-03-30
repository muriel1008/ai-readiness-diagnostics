# Google Apps Script — Setup Guide for FPT TNA

## Step 1: Create Google Sheet

1. Go to Google Sheets, create new spreadsheet
2. Name it: "FPT AI Proficiency Assessment — Responses"
3. In Row 1, add these headers:

| A | B | C | D | E | F | G | H | I | J | K | L | M | N | O |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Timestamp | Name | Email | Department | Final Level | Level Name | TOE-T (%) | TOE-O (%) | TOE-E (%) | L1 Score | L2 Score | L3 Score | L4 Score | L5 Score | Raw Answers |

## Step 2: Deploy Apps Script

1. In the spreadsheet, go to **Extensions > Apps Script**
2. Delete any existing code in `Code.gs`
3. Paste the following:

```javascript
function doPost(e) {
  try {
    var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
    var data = JSON.parse(e.postData.contents);

    sheet.appendRow([
      data.timestamp || new Date().toISOString(),
      data.name || '',
      data.email || '',
      data.department || '',
      data.finalLevel || '',
      data.levelName || '',
      data.toeT || '',
      data.toeO || '',
      data.toeE || '',
      data.l1Score || '',
      data.l2Score || '',
      data.l3Score || '',
      data.l4Score || '',
      data.l5Score || '',
      data.rawAnswers || ''
    ]);

    return ContentService
      .createTextOutput(JSON.stringify({ status: 'success' }))
      .setMimeType(ContentService.MimeType.JSON);

  } catch (error) {
    return ContentService
      .createTextOutput(JSON.stringify({ status: 'error', message: error.toString() }))
      .setMimeType(ContentService.MimeType.JSON);
  }
}
```

4. Click **Deploy > New deployment**
5. Type: **Web app**
6. Execute as: **Me**
7. Who has access: **Anyone**
8. Click **Deploy**
9. Copy the **Web app URL**

## Step 3: Connect HTML to Google Sheet

1. Open `fpt-adaptive-tna.html`
2. Find this line near the top of the `<script>`:
   ```javascript
   const GOOGLE_SCRIPT_URL = '';
   ```
3. Paste your Web app URL between the quotes:
   ```javascript
   const GOOGLE_SCRIPT_URL = 'https://script.google.com/macros/s/YOUR_ID/exec';
   ```
4. Save the file

## Step 4: Test

1. Open the HTML file in a browser
2. Fill in name/email/dept and complete the assessment
3. Check Google Sheet — a new row should appear with all data

## Notes

- `mode: 'no-cors'` in the fetch means you won't see success/error in browser console, but data will arrive in the sheet
- If you redeploy the script, the URL changes — update the HTML
- Raw Answers column contains JSON of all individual answer selections for deep analysis
