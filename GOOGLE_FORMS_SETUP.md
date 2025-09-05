# Google Forms Integration Setup Guide

## Step 1: Create Your Google Form

1. Go to [Google Forms](https://forms.google.com)
2. Create a new blank form
3. Title it: "Cadence Health - Consultation Requests"
4. Add these fields (EXACTLY as shown):
   - **Question 1**: "Full Name" (Short answer, Required)
   - **Question 2**: "Email Address" (Short answer, Required)
   - **Question 3**: "Timestamp" (Short answer, Optional)
   - **Question 4**: "Source" (Short answer, Optional)

## Step 2: Get Your Form IDs

1. Click the three dots menu (⋮) → "Get pre-filled link"
2. Fill in test data:
   - Full Name: "TEST_NAME"
   - Email Address: "TEST_EMAIL"
   - Timestamp: "TEST_TIME"
   - Source: "TEST_SOURCE"
3. Click "Get link" and copy it
4. The URL will look like:
   ```
   https://docs.google.com/forms/d/e/FORM_ID/viewform?usp=pp_url&entry.XXXXX=TEST_NAME&entry.YYYYY=TEST_EMAIL...
   ```

5. Extract these values:
   - **FORM_ID**: The long string after `/d/e/` and before `/viewform`
   - **Name field ID**: The number after `entry.` for TEST_NAME
   - **Email field ID**: The number after `entry.` for TEST_EMAIL
   - **Timestamp field ID**: The number after `entry.` for TEST_TIME  
   - **Source field ID**: The number after `entry.` for TEST_SOURCE

## Step 3: Configure Form Settings

1. Click Settings (gear icon)
2. Under "Responses" tab:
   - ✅ Collect email addresses: OFF (we're collecting it as a field)
   - ✅ Limit to 1 response: OFF
   - ✅ Allow response editing: OFF
3. Under "Presentation" tab:
   - ✅ Show link to submit another response: OFF

## Step 4: Link to Google Sheet

1. Go to "Responses" tab in your form
2. Click the Google Sheets icon (Create spreadsheet)
3. Choose "Create a new spreadsheet"
4. Name it: "Cadence Health - Leads"
5. The sheet will automatically update with new submissions

## Step 5: Make Form Public

1. Click "Send" button
2. Click the link icon (🔗)
3. Shorten URL (optional)
4. Copy the link - this confirms it's publicly accessible

## Step 6: Update Your Website Code

Replace the placeholder values in the JavaScript code:
```javascript
const GOOGLE_FORM_CONFIG = {
  formId: 'YOUR_FORM_ID_HERE',
  fields: {
    name: 'entry.XXXXX',    // Replace with your name field ID
    email: 'entry.YYYYY',   // Replace with your email field ID
    timestamp: 'entry.ZZZZ', // Replace with your timestamp field ID
    source: 'entry.AAAA'     // Replace with your source field ID
  }
};
```

## Step 7: Test the Integration

1. Start local development server: `npm run dev`
2. Fill out the form on your website
3. Check your Google Sheet for the submission
4. You'll see a CORS error in console - this is NORMAL and expected

## Troubleshooting

### Form not submitting?
- Check that all field IDs are correct
- Ensure form is set to public (no sign-in required)
- Verify you're using the correct form ID

### No data in Google Sheet?
- Make sure the sheet is linked to the form
- Check form responses tab in Google Forms
- Verify field IDs match exactly

### Want to add more fields?
1. Add field to Google Form
2. Get pre-filled link again
3. Extract new field ID
4. Add to JavaScript configuration

## Security Notes

- This method is suitable for public forms (no sensitive data)
- For sensitive data, use server-side submission
- Google Forms logs IP addresses by default
- Consider GDPR/privacy policy updates

## Benefits of This Setup

✅ **Free**: No cost for form handling or storage
✅ **Reliable**: Google's infrastructure
✅ **Real-time**: Instant updates in Google Sheets
✅ **Works Locally**: Test forms during development
✅ **Backup**: Redundant data storage (Netlify + Google)
✅ **Analytics**: Use Google Sheets formulas and charts
✅ **Export**: Easy CSV/Excel export from Sheets
✅ **Notifications**: Set up email alerts for new submissions

## Next Steps

1. Set up email notifications in Google Sheets (Tools → Notification rules)
2. Create a dashboard in Google Sheets for lead analytics
3. Set up automatic follow-up emails using Google Apps Script
4. Integrate with CRM via Zapier or Google Apps Script