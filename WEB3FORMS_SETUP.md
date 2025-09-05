# Web3Forms Setup - Quick Start Guide

## Why Web3Forms?
- ✅ **Works locally** - Test on localhost immediately
- ✅ **Free** - Unlimited form submissions
- ✅ **No account** - Just email verification
- ✅ **Simple** - 2-minute setup
- ✅ **Reliable** - Email notifications

## Step 1: Get Your Access Key (1 minute)

1. Go to https://web3forms.com
2. Enter your email address
3. Click "Get Access Key"
4. Check your email for the access key
5. Copy the access key (looks like: `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`)

## Step 2: Add Your Access Key (30 seconds)

1. Open `index.html`
2. Find line 1896: `const WEB3FORMS_ACCESS_KEY = 'YOUR_ACCESS_KEY_HERE';`
3. Replace `YOUR_ACCESS_KEY_HERE` with your actual access key
4. Save the file

Example:
```javascript
const WEB3FORMS_ACCESS_KEY = 'xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx';
```

## Step 3: Test Locally (1 minute)

1. Start your local server:
```bash
npm run dev
```

2. Open http://localhost:3000 in your browser
3. Fill out the consultation form:
   - Enter BMI info
   - Add name and email
   - Submit the form
4. Check your email - you should receive the submission!

## Step 4: Deploy (Optional)

Once tested locally:
```bash
git add .
git commit -m "Add Web3Forms for form handling"
git push origin main
```

If using Netlify, it will auto-deploy. Otherwise:
```bash
netlify deploy --prod
```

## What You'll Receive

Each form submission sends an email with:
- **Subject**: "New Consultation Request - Cadence Health"
- **Name**: The submitted name
- **Email**: The submitted email
- **Timestamp**: When submitted (EST/EDT)
- **Message**: Context about the submission

## Customization Options

You can add more fields in the `submitToWeb3Forms` function:

```javascript
const formData = {
    access_key: WEB3FORMS_ACCESS_KEY,
    name: name,
    email: email,
    phone: phone,  // Add phone field
    bmi: bmi,      // Add BMI data
    age: age,      // Add age
    // Any other fields you want
};
```

## Troubleshooting

### Not receiving emails?
1. Check spam/junk folder
2. Verify access key is correct
3. Make sure you verified your email with Web3Forms
4. Check browser console for errors

### Form not submitting?
1. Check browser console for errors
2. Verify you're connected to internet
3. Make sure access key is in quotes
4. Try in incognito mode (no extensions)

### Want to change notification email?
Get a new access key with different email at https://web3forms.com

## Features

### What's Included:
- ✅ Email notifications for each submission
- ✅ Spam protection (built-in)
- ✅ Works on localhost
- ✅ No CORS issues
- ✅ JSON response with success status
- ✅ Timestamp with each submission

### Limitations:
- No dashboard (email only)
- No CSV export (copy from emails)
- No webhooks on free plan
- No file uploads on free plan

## Next Steps

1. **Add more fields**: Include BMI, age, etc. in submission
2. **Custom thank you**: Redirect to custom success page
3. **Add validation**: Check fields before submitting
4. **Style errors**: Make error messages pretty
5. **Add honeypot**: Extra spam protection (Web3Forms supports this)

## Support

- Web3Forms Docs: https://web3forms.com/docs
- Email: support@web3forms.com
- Status: https://status.web3forms.com

---

That's it! Your form should be working in less than 2 minutes. 🎉