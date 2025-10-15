# EmailJS Quick Setup Guide

## ✅ What's Done

✅ Email service created (`src/app/core/services/email.service.ts`)  
✅ Contact form integrated with email service  
✅ Services quote form integrated with email service  
✅ Loading states and error handling added  
✅ EmailJS package installed  
✅ Professional email templates ready

## 🚀 Quick Setup (5 minutes)

### 1. Create EmailJS Account
- Go to: https://www.emailjs.com/
- Sign up with **mfk8776@gmail.com**
- Verify your email

### 2. Connect Gmail
- Dashboard → Email Services → Add New Service
- Choose **Gmail**
- Sign in with mfk8776@gmail.com
- Copy the **Service ID** (example: `service_abc123`)

### 3. Create Templates

**Template 1 - Contact Form:**
- Email Templates → Create New Template
- Template ID: `template_contact`
- To Email: `mfk8776@gmail.com`
- Subject: `New Contact Form Submission from {{from_name}}`
- Body: Use the template from `EMAIL_SETUP_INSTRUCTIONS.md`

**Template 2 - Quote Request:**
- Create New Template
- Template ID: `template_quote`
- To Email: `mfk8776@gmail.com`
- Subject: `New Custom Quote Request from {{from_name}}`
- Body: Use the template from `EMAIL_SETUP_INSTRUCTIONS.md`

### 4. Get Your Public Key
- Account → Copy **Public Key** (example: `user_xyz789`)

### 5. Update Code

Edit: `src/app/core/services/email.service.ts`

```typescript
private readonly serviceId = 'YOUR_SERVICE_ID_HERE'; // Replace with your Service ID
private readonly publicKey = 'YOUR_PUBLIC_KEY_HERE'; // Replace with your Public Key
```

### 6. Test It!

```bash
npm start
```

Go to http://localhost:4200/contact and submit the form.  
Check mfk8776@gmail.com - you should receive an email! 🎉

## 📧 What Gets Sent

### Contact Form Email Includes:
- Name, Email, Phone
- Company Name, Business Type, Website
- Selected Services
- Budget Range
- Message
- Submission Timestamp

### Quote Request Email Includes:
- Name, Email, Phone
- Business Name
- Service Interested In
- Message Details
- Submission Timestamp

## 🔧 Troubleshooting

**No emails arriving?**
1. Check browser console for errors (F12)
2. Verify Service ID and Public Key are correct
3. Check EmailJS dashboard → Logs
4. Add `localhost` to allowed domains (Account → Security)

**403 Forbidden?**
- Add your domain to EmailJS allowed domains

**Wrong template?**
- Template IDs must match exactly: `template_contact` and `template_quote`

## 📊 Free Plan Limits

- ✅ 200 emails/month (free forever)
- ✅ 2 email services
- ✅ Unlimited templates
- ✅ No credit card required

## 🎯 Quick Test

After setup, test both forms:
1. `/contact` page - Multi-step contact form
2. `/services` page - Scroll down to "Get Custom Quote" section

Both will send emails to **mfk8776@gmail.com**!

---

For detailed setup with screenshots and troubleshooting, see `EMAIL_SETUP_INSTRUCTIONS.md`

