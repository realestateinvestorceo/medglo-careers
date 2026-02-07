# Google Sheets Setup for MedGlo Applications

## Step 1: Create a Google Sheet

1. Go to [Google Sheets](https://sheets.google.com)
2. Create a new spreadsheet
3. Name it "MedGlo Applications"
4. In Row 1, add these column headers:
   - A1: `id`
   - B1: `firstName`
   - C1: `lastName`
   - D1: `email`
   - E1: `phone`
   - F1: `location`
   - G1: `whyThisRole`
   - H1: `resumeUrl`
   - I1: `voiceUrl`
   - J1: `status`
   - K1: `submittedAt`
   - L1: `notes`

## Step 2: Create Google Apps Script

1. In your Google Sheet, go to **Extensions > Apps Script**
2. Delete any existing code
3. Paste the following code:

```javascript
// Configuration
const SHEET_NAME = 'Sheet1';

function doGet(e) {
  const action = e.parameter.action;

  if (action === 'getAll') {
    return getAllApplications();
  }

  return ContentService.createTextOutput(JSON.stringify({ error: 'Invalid action' }))
    .setMimeType(ContentService.MimeType.JSON);
}

function doPost(e) {
  try {
    const data = JSON.parse(e.postData.contents);

    if (data.action === 'submit') {
      return submitApplication(data);
    } else if (data.action === 'updateStatus') {
      return updateStatus(data.id, data.status);
    } else if (data.action === 'updateNotes') {
      return updateNotes(data.id, data.notes);
    }

    return jsonResponse({ success: false, error: 'Invalid action' });
  } catch (error) {
    return jsonResponse({ success: false, error: error.toString() });
  }
}

function submitApplication(data) {
  const sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName(SHEET_NAME);
  const id = Utilities.getUuid();

  sheet.appendRow([
    id,
    data.firstName,
    data.lastName,
    data.email,
    data.phone,
    data.location || '',
    data.whyThisRole,
    data.resumeUrl || '',
    data.voiceUrl || '',
    'new',
    new Date().toISOString(),
    ''
  ]);

  // Send email notification
  try {
    MailApp.sendEmail({
      to: 'JoshuaDaveMiller@gmail.com',
      subject: 'New MedGlo Application: ' + data.firstName + ' ' + data.lastName,
      htmlBody: `
        <h2>New Application Received</h2>
        <p><strong>Name:</strong> ${data.firstName} ${data.lastName}</p>
        <p><strong>Email:</strong> ${data.email}</p>
        <p><strong>WhatsApp:</strong> ${data.phone}</p>
        <p><strong>Location:</strong> ${data.location || 'Not provided'}</p>
        <p><strong>Why this role:</strong></p>
        <blockquote>${data.whyThisRole}</blockquote>
        <p><a href="YOUR_ADMIN_URL/admin.html">View in Admin Dashboard</a></p>
      `
    });
  } catch (emailError) {
    console.log('Email notification failed: ' + emailError);
  }

  return jsonResponse({ success: true, id: id });
}

function getAllApplications() {
  const sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName(SHEET_NAME);
  const data = sheet.getDataRange().getValues();
  const headers = data[0];

  const applications = [];
  for (let i = 1; i < data.length; i++) {
    const row = data[i];
    const app = {};
    headers.forEach((header, index) => {
      app[header] = row[index];
    });
    applications.push(app);
  }

  // Sort by newest first
  applications.sort((a, b) => new Date(b.submittedAt) - new Date(a.submittedAt));

  return jsonResponse({ success: true, applications: applications });
}

function updateStatus(id, status) {
  const sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName(SHEET_NAME);
  const data = sheet.getDataRange().getValues();

  for (let i = 1; i < data.length; i++) {
    if (data[i][0] === id) {
      sheet.getRange(i + 1, 10).setValue(status); // Column J (status)
      return jsonResponse({ success: true });
    }
  }

  return jsonResponse({ success: false, error: 'Application not found' });
}

function updateNotes(id, notes) {
  const sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName(SHEET_NAME);
  const data = sheet.getDataRange().getValues();

  for (let i = 1; i < data.length; i++) {
    if (data[i][0] === id) {
      sheet.getRange(i + 1, 12).setValue(notes); // Column L (notes)
      return jsonResponse({ success: true });
    }
  }

  return jsonResponse({ success: false, error: 'Application not found' });
}

function jsonResponse(data) {
  return ContentService.createTextOutput(JSON.stringify(data))
    .setMimeType(ContentService.MimeType.JSON);
}
```

4. Click **Save** (Ctrl+S or Cmd+S)
5. Name the project "MedGlo Applications"

## Step 3: Deploy as Web App

1. Click **Deploy > New deployment**
2. Click the gear icon next to "Select type" and choose **Web app**
3. Configure:
   - Description: "MedGlo Applications API"
   - Execute as: **Me**
   - Who has access: **Anyone**
4. Click **Deploy**
5. Authorize the app when prompted (click through the warnings)
6. **Copy the Web App URL** - you'll need this!

The URL will look like:
```
https://script.google.com/macros/s/AKfycbx.../exec
```

## Step 4: Update Your Site

1. Open `index.html` in your MedGlo project
2. Find this line near the bottom (around line 1298):
   ```javascript
   const GOOGLE_SCRIPT_URL = 'YOUR_GOOGLE_SCRIPT_URL_HERE';
   ```
3. Replace `YOUR_GOOGLE_SCRIPT_URL_HERE` with your actual Web App URL

4. Open `admin.html`
5. Find this line near the top of the script:
   ```javascript
   const GOOGLE_SCRIPT_URL = 'YOUR_GOOGLE_SCRIPT_URL_HERE';
   ```
6. Replace it with the same Web App URL

## Step 5: Set Your Admin Password

In `admin.html`, find this line:
```javascript
const ADMIN_PASSWORD = 'medglo2024';
```

Change `medglo2024` to your desired password.

## Step 6: Push to GitHub and Deploy

```bash
cd "/Users/josh/Downloads/AI Projects/MedGlo"
git add -A
git commit -m "Add application form submission and admin dashboard"
git push
```

Vercel will automatically redeploy.

## Testing

1. Visit your site and submit a test application
2. Check your Google Sheet - a new row should appear
3. Check your email for the notification
4. Visit `/admin.html` and log in with your password
5. You should see the application in the dashboard

## File Uploads (Resume & Voice)

For file uploads, the current setup stores them as data URLs (base64). For production with many applicants, consider:

1. **Cloudinary** (free tier available) - for storing files
2. **Google Drive** - can be integrated with Apps Script
3. **Uploadcare** - simple file upload widget

The current implementation works well for small to medium volume.

---

**Your Admin Dashboard URL:** `https://your-vercel-url.vercel.app/admin.html`

**Default Password:** `medglo2024` (change this!)
