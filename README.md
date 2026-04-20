# nametagstudio
My First Business



# NameTag Studio – Complete Setup Guide

## What You Have
- `index.html` → Customer website (order page)
- `admin.html` → Your private admin dashboard
- `SETUP.md` → This guide

---

## STEP 1: Set Up Razorpay Payment Gateway (Free)

### A) Create Your Razorpay Account
1. Go to **https://razorpay.com** and click "Sign Up"
2. Enter your business details (you can use personal PAN if no business PAN)
3. Complete KYC: Aadhaar + PAN + Bank Account
4. Wait for approval (usually 1–2 business days)

### B) Get Your API Keys
1. Login → Go to **Settings → API Keys**
2. Click "Generate Key" (choose Live mode after testing)
3. You'll get:
   - `Key ID`: rzp_live_XXXXXXXXXX  ← This is public (safe in website)
   - `Key Secret`: Keep this PRIVATE, never put in HTML

### C) Add Key to Website
Open `index.html`, find this line:
```
key: 'YOUR_RAZORPAY_KEY',
```
Replace `YOUR_RAZORPAY_KEY` with your actual Key ID.

Also uncomment this line at the bottom of index.html:
```html
<script src="https://checkout.razorpay.com/v1/checkout.js"></script>
```

### D) Test First
- Use Key ID: `rzp_test_XXXXXXX` (test mode) before going live
- Test card: 4111 1111 1111 1111 / Any future date / Any CVV
- Test UPI: success@razorpay

---

## STEP 2: Host Your Website (Free Options)

### Option A: GitHub Pages (Recommended – Free Forever)
1. Create account at **https://github.com**
2. Create a new repository named `nametagstudio`
3. Upload both `index.html` and `admin.html`
4. Go to Settings → Pages → Source: "main" branch
5. Your website: `https://yourusername.github.io/nametagstudio`

### Option B: Netlify (Easiest – Free)
1. Go to **https://netlify.com**
2. Drag and drop your folder onto their dashboard
3. Get a URL like `https://nametagstudio.netlify.app`
4. Can connect custom domain for ₹500–800/year

### Option C: Custom Domain
- Buy domain at **GoDaddy / Namecheap / BigRock**: `nametagstudio.in` (~₹600/year)
- Point it to your GitHub Pages or Netlify site

---

## STEP 3: Receive Order Notifications

### WhatsApp Business (Recommended)
1. Install **WhatsApp Business** on your phone
2. Add your number to the website's WhatsApp link
3. In admin.html Settings, enter your WhatsApp number
4. Orders will show up in your admin dashboard

### Email Notifications (Optional – Free via Formspree)
1. Go to **https://formspree.io** and create a free account
2. Create a form and get a Form ID
3. Add to your order form action (requires minor HTML edit)

---

## STEP 4: Manage Templates (Admin Dashboard)

### Access Admin
- Open `admin.html` in your browser
- Bookmark it – this is your control panel
- **IMPORTANT**: Don't share this URL publicly. Protect with a password (see below)

### Add Templates
1. Go to Admin → Templates tab
2. Click "+ Add Template"
3. Give it a name, pick background and accent colors
4. Set status to "Live" or "Draft"
5. Live templates appear in the customer order form automatically

### Manage Orders
1. Go to Admin → Orders tab
2. Click any row to see full order details
3. Use "→ Processing" / "→ Dispatched" buttons to update status
4. Customer gets notified via WhatsApp (when integrated)

---

## STEP 5: Protect Your Admin Panel

### Simple Password Protection (Free – via Netlify)
If using Netlify, create a `_headers` file:
```
/admin.html
  Basic-Auth: admin:YourPassword123
```

### Or use a different URL / rename the file
- Rename `admin.html` to something hard to guess: `mgmt-panel-2025.html`

---

## STEP 6: Order Fulfilment Workflow

```
Customer Orders → Payment via Razorpay
       ↓
You get WhatsApp notification
       ↓
Open Admin → Check order details
       ↓
Print the slip (use any home printer + art paper)
OR send to local print shop
       ↓
Update status to "Processing"
       ↓
Pack and ship via India Post / Delhivery
Enter tracking number
       ↓
Update status to "Dispatched"
       ↓
Customer receives → Mark "Delivered"
```

---

## Printing Tips

### Materials Needed
- **Paper**: 200 GSM art paper / glossy photo paper (available at stationery shops)
- **Printer**: Any inkjet printer works well for color
- **Lamination**: Optional, adds durability (local print shops: ₹5–10 per sheet)
- **Cutter**: Guillotine cutter for clean edges

### Sizing
- Each slip: 8.5 cm × 5.5 cm
- A4 sheet fits 10 slips (2 columns × 5 rows)
- 50 slip order = 5 A4 sheets

---

## Pricing Suggestion (to edit in website)

| Quantity | You Charge | Your Cost | Profit |
|----------|-----------|-----------|--------|
| 20 slips | ₹50 + ₹30 + ₹40 = ₹120 | ~₹30 | ~₹90 |
| 50 slips | ₹100 + ₹30 + ₹40 = ₹170 | ~₹50 | ~₹120 |
| 100 slips | ₹150 + ₹30 + FREE = ₹180 | ~₹80 | ~₹100 |

*Costs include ink, paper, packing, and shipping estimate.*

---

## Customise the Website

### Change Business Name
Search for `NameTag Studio` in both HTML files and replace with your name.

### Change Phone/WhatsApp
Search for `XXXXXXXXXX` and replace with your 10-digit number.
WhatsApp link format: `https://wa.me/91XXXXXXXXXX`

### Change Contact Email
Search for `hello@nametagstudio.in` and replace.

### Change City
Search for `Chandigarh` and replace.

---

## Future Features to Add

- [ ] Multiple student bulk upload (CSV)
- [ ] Template image upload (actual design files)
- [ ] Order tracking page for customers
- [ ] SMS notifications via Twilio
- [ ] Admin login/password system
- [ ] Google Sheets integration for order log

---

## Support Resources
- Razorpay Docs: https://razorpay.com/docs
- GitHub Pages: https://pages.github.com
- Netlify: https://docs.netlify.com
- WhatsApp Business API: https://business.whatsapp.com
