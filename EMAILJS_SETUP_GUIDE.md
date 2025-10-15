# 📧 EmailJS Setup Guide for TrailTrustMedia

## Why Email is Failing
The email functionality is integrated but needs EmailJS API keys to work. Currently, it's using placeholder values.

## Quick Setup (5-10 minutes)

### Step 1: Create EmailJS Account
1. Go to [EmailJS.com](https://www.emailjs.com/)
2. Click "Sign Up" and create a free account
3. Verify your email address

### Step 2: Connect Your Gmail
1. In EmailJS dashboard, click "Add New Service"
2. Select "Gmail"
3. Click "Connect Account" and sign in with **mfk8776@gmail.com**
4. Copy the **Service ID** (looks like: `service_xxxxxxx`)

### Step 3: Create Email Templates

#### Template 1: Contact Form
1. Click "Email Templates" → "Create New Template"
2. **Template Name**: Contact Form Submission
3. **Template Content**:

```
Subject: New Contact Form Submission from {{from_name}}

You have a new contact form submission:

From: {{from_name}}
Email: {{from_email}}
Phone: {{phone}}
Company: {{company_name}}
Business Type: {{business_type}}
Website: {{website}}
Services Interested: {{selected_services}}
Message: {{message}}

Submitted: {{submission_date}}
```

4. Click "Save" and copy the **Template ID** (looks like: `template_xxxxxxx`)

#### Template 2: Quote Request
1. Create another template
2. **Template Name**: Quote Request
3. **Template Content**:

```
Subject: New Quote Request from {{from_name}}

Quote Request Details:

From: {{from_name}}
Email: {{from_email}}
Phone: {{phone}}
Business: {{business_name}}
Service: {{service_interested}}
Message: {{message}}

Submitted: {{submission_date}}
```

4. Click "Save" and copy the **Template ID**

### Step 4: Get Your Public Key
1. Go to "Account" → "General"
2. Copy your **Public Key** (looks like a long string)

### Step 5: Update Your Code
Open `src/app/core/services/email.service.ts` and replace:

```typescript
private readonly serviceId = 'YOUR_SERVICE_ID_HERE';
private readonly publicKey = 'YOUR_PUBLIC_KEY_HERE';

private readonly templates = {
  contact: 'YOUR_CONTACT_TEMPLATE_ID_HERE',
  quote: 'YOUR_QUOTE_TEMPLATE_ID_HERE'
};
```

### Step 6: Test
1. Run your app: `npm start`
2. Go to the Contact page
3. Fill out and submit the form
4. Check **mfk8776@gmail.com** for the email

## Free Tier Limits
- 200 emails/month (free)
- Perfect for a small business
- Upgrade if you need more

## That's It! 🎉
Your forms will now send emails directly to mfk8776@gmail.com

