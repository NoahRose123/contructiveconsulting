# Email Setup Guide for Constructive Consulting Services

## Overview
I've implemented EmailJS to handle contact form submissions. This will send all form data to **rosewebc@gmail.com** when someone fills out the contact form.

## Setup Instructions

### Step 1: Create EmailJS Account
1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Sign up for a free account
3. Verify your email address

### Step 2: Add Email Service
1. In your EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Choose "Gmail" as your email service
4. Connect your Gmail account (rosewebc@gmail.com)
5. Note down the **Service ID** (you'll need this)

### Step 3: Create Email Template
1. Go to "Email Templates" in your dashboard
2. Click "Create New Template"
3. Use this template content:

**Subject:** New Contact Form Submission - Constructive Consulting Services

**Content:**
```
New contact form submission from Constructive Consulting Services website:

Name: {{from_name}}
Email: {{from_email}}
Phone: {{phone}}
Service Needed: {{service}}
Message: {{message}}

---
This email was sent from the Constructive Consulting Services contact form.
```

4. Save the template and note down the **Template ID**

### Step 4: Get Public Key
1. Go to "Account" in your EmailJS dashboard
2. Find your **Public Key** (also called User ID)

### Step 5: Update the Website
Replace these placeholders in your `index.html` file:

1. Replace `YOUR_PUBLIC_KEY` with your actual public key
2. Replace `YOUR_SERVICE_ID` with your Gmail service ID  
3. Replace `YOUR_TEMPLATE_ID` with your template ID

**Example:**
```javascript
// Initialize EmailJS
(function() {
    emailjs.init("user_abc123def456"); // Your actual public key
})();

// In the form submission:
emailjs.send('service_gmail123', 'template_contact456', templateParams)
```

### Step 6: Test the Form
1. Save your changes
2. Open your website
3. Fill out the contact form
4. Submit it
5. Check rosewebc@gmail.com for the email

## What Information Will Be Sent
The email will include:
- **Name** (required)
- **Email** (required) 
- **Phone** (optional)
- **Service Needed** (optional)
- **Project Details/Message** (required)

## Troubleshooting
- If emails aren't being sent, check the browser console for error messages
- Make sure all IDs are correctly replaced in the code
- Verify your Gmail account is properly connected in EmailJS
- Check your spam folder for test emails

## Free Tier Limits
EmailJS free tier includes:
- 200 emails per month
- Perfect for most small business websites

## Security Note
The public key is safe to include in your website code - it's designed to be public-facing.
