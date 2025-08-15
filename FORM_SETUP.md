# Contact Form Setup Guide

## Current Status
The contact form is now configured to use Formspree, a free form handling service. However, you need to set up your own Formspree account to receive the form submissions.

## Setup Steps:

### 1. Create Formspree Account
1. Go to https://formspree.io/
2. Click "Get Started" and create a free account
3. Verify your email address

### 2. Create a New Form
1. In your Formspree dashboard, click "New Form"
2. Give it a name like "GTM Kovář Contact Form"
3. Copy the form endpoint URL (it will look like `https://formspree.io/f/xpzgwqjq`)

### 3. Update the HTML
Replace the current form action in `optimized_website.html`:

```html
<!-- Find this line in the contact form section -->
<form id="contact-form" action="https://formspree.io/f/xpzgwqjq" method="POST" class="space-y-6">

<!-- Replace with your actual Formspree endpoint -->
<form id="contact-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST" class="space-y-6">
```

### 4. Test the Form
1. Save the changes
2. Refresh your website
3. Fill out and submit the contact form
4. Check your email - you should receive the form submission

## Alternative Solutions:

### Option 1: Use Netlify Forms (if hosting on Netlify)
If you plan to host on Netlify, you can use their built-in form handling:

```html
<form name="contact" method="POST" data-netlify="true" class="space-y-6">
```

### Option 2: Use EmailJS (Client-side only)
For a completely client-side solution, you can use EmailJS:

1. Sign up at https://www.emailjs.com/
2. Configure your email service
3. Update the JavaScript to use EmailJS instead of Formspree

### Option 3: Simple Email Fallback
If you prefer to keep it simple, you can revert to the email client approach:

```javascript
// In script.js, replace the fetch call with:
const mailtoLink = `mailto:hoblk.tom@gmail.com?subject=Žádost o konzultaci - ${data['first-name']} ${data['last-name']}&body=${encodeURIComponent(emailBody)}`;
window.open(mailtoLink);
```

## Current Form Fields:
- **Jméno** (First Name) - Required
- **Příjmení** (Last Name) - Required  
- **Email** - Required
- **Společnost** (Company) - Optional
- **Vaše cíle a očekávání** (Your goals and expectations) - Optional

## Features:
- ✅ Form validation
- ✅ Loading states
- ✅ Success/error notifications
- ✅ Auto-reset after submission
- ✅ Responsive design
- ✅ Accessibility features

## Next Steps:
1. Set up your Formspree account
2. Update the form action URL
3. Test the form submission
4. Check that you receive emails properly

The form will now actually send you the contact information instead of just opening the user's email client!
