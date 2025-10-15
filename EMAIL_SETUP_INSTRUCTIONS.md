# Email Integration Setup Instructions

## Overview
All forms on the TrailTrustMedia website (Contact Form and Quote Request Form) are now configured to send emails to **mfk8776@gmail.com** whenever someone submits a form.

## Step 1: Install Dependencies

Run the following command to install the EmailJS library:

```bash
npm install
```

This will install `@emailjs/browser` which is already added to package.json.

## Step 2: Create EmailJS Account

1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Click **"Sign Up"** (it's free - 200 emails/month)
3. Sign up using your email (mfk8776@gmail.com)
4. Verify your email address

## Step 3: Connect Your Email Service

1. After logging in, go to **"Email Services"** in the left sidebar
2. Click **"Add New Service"**
3. Choose **"Gmail"** (recommended) or any other email service
4. Click **"Connect Account"**
5. Sign in with your Gmail account (mfk8776@gmail.com)
6. Note the **Service ID** (e.g., `service_abc123`)

## Step 4: Create Email Templates

### Template 1: Contact Form

1. Go to **"Email Templates"** in the left sidebar
2. Click **"Create New Template"**
3. Name it: **"Contact Form Submission"**
4. Set **Template ID**: `template_contact`
5. Use this template content:

**Subject:**
```
New Contact Form Submission from {{from_name}}
```

**Body:**
```html
<h2>New Contact Form Submission</h2>

<p><strong>Submission Date:</strong> {{submission_date}}</p>

<hr>

<h3>Contact Information</h3>
<ul>
  <li><strong>Name:</strong> {{from_name}}</li>
  <li><strong>Email:</strong> {{from_email}}</li>
  <li><strong>Phone:</strong> {{phone}}</li>
</ul>

<h3>Business Information</h3>
<ul>
  <li><strong>Company Name:</strong> {{company_name}}</li>
  <li><strong>Business Type:</strong> {{business_type}}</li>
  <li><strong>Website:</strong> {{website}}</li>
</ul>

<h3>Service Request</h3>
<ul>
  <li><strong>Selected Services:</strong> {{selected_services}}</li>
  <li><strong>Budget Range:</strong> {{budget}}</li>
</ul>

<h3>Message</h3>
<p>{{message}}</p>

<hr>
<p><em>This email was sent from the TrailTrustMedia website contact form.</em></p>
```

6. Set **To Email**: `mfk8776@gmail.com`
7. Click **"Save"**

### Template 2: Quote Request Form

1. Click **"Create New Template"** again
2. Name it: **"Quote Request Submission"**
3. Set **Template ID**: `template_quote`
4. Use this template content:

**Subject:**
```
New Custom Quote Request from {{from_name}}
```

**Body:**
```html
<h2>New Custom Quote Request</h2>

<p><strong>Submission Date:</strong> {{submission_date}}</p>

<hr>

<h3>Contact Information</h3>
<ul>
  <li><strong>Name:</strong> {{from_name}}</li>
  <li><strong>Email:</strong> {{from_email}}</li>
  <li><strong>Phone:</strong> {{phone}}</li>
  <li><strong>Business Name:</strong> {{business_name}}</li>
</ul>

<h3>Service Interest</h3>
<p><strong>Service Requested:</strong> {{service_interested}}</p>

<h3>Details</h3>
<p>{{message}}</p>

<hr>
<p><em>This email was sent from the TrailTrustMedia services page quote form.</em></p>
```

5. Set **To Email**: `mfk8776@gmail.com`
6. Click **"Save"**

## Step 5: Get Your Public Key

1. Go to **"Account"** in the left sidebar
2. Find **"Public Key"** section
3. Copy your public key (e.g., `user_abc123xyz`)

## Step 6: Update the Code

Open the file: `src/app/core/services/email.service.ts`

Replace the following values:

```typescript
private readonly serviceId = 'YOUR_SERVICE_ID_HERE'; // From Step 3
private readonly publicKey = 'YOUR_PUBLIC_KEY_HERE'; // From Step 5
```

For example:
```typescript
private readonly serviceId = 'service_abc123';
private readonly publicKey = 'user_abc123xyz';
```

## Step 7: Test the Integration

1. Run your development server:
```bash
npm start
```

2. Navigate to the Contact page or Services page
3. Fill out and submit a form
4. Check your email (mfk8776@gmail.com) - you should receive an email within seconds!

## Troubleshooting

### Emails not sending?

1. **Check Console Errors**: Open browser DevTools (F12) and check for errors
2. **Verify IDs**: Make sure Service ID and Public Key are correct
3. **Check EmailJS Dashboard**: Go to "Logs" to see delivery status
4. **Email Limits**: Free plan has 200 emails/month - check if you've exceeded

### Getting 403 Errors?

- Make sure your website domain is added to EmailJS allowed domains:
  1. Go to Account → Security
  2. Add your domain (e.g., `localhost` for development, your actual domain for production)

### Template Variables Not Showing?

- Make sure the variable names in the template match exactly with the code
- Variable names are case-sensitive

## Forms Currently Integrated

✅ **Contact Form** (`/contact` page)
- Multi-step form with service selection, business info, and contact details
- Sends to: mfk8776@gmail.com
- Template: `template_contact`

✅ **Custom Quote Form** (`/services` page)
- Single-step form for requesting custom pricing quotes
- Sends to: mfk8776@gmail.com
- Template: `template_quote`

## Email Content

Each form submission will include:
- **Submission timestamp**
- **All form fields** (name, email, phone, business info, etc.)
- **Form type identifier**
- **Professional HTML formatting**

## Monthly Limits (Free Plan)

- **200 emails/month** free
- **2 email services** (you only need 1)
- **Unlimited templates**

If you need more, EmailJS offers paid plans starting at $15/month for 1,000 emails.

## Support

- EmailJS Documentation: [https://www.emailjs.com/docs/](https://www.emailjs.com/docs/)
- EmailJS Support: [https://www.emailjs.com/support/](https://www.emailjs.com/support/)

## Security Notes

- Public key is safe to use in client-side code
- Never expose your Private key
- EmailJS uses CAPTCHA to prevent spam
- All emails are sent through secure EmailJS servers

---

**That's it!** Your forms are now ready to send emails to mfk8776@gmail.com automatically whenever someone submits them.

