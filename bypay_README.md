# 🏦 Bypay Bank — Mobile Banking App

> **Smart Banking. Secure Future.**
> CEO: Daniel Christopher Wilson
> 📞 +1 (303) 555-0147 · ✉️ support@bypaybank.com
> 1700 Lincoln Street, Denver, CO 80203
> **FDIC Insured**

A full US mobile banking app — installs on Android & iPhone like a real banking app.

---

## 📁 Upload These 4 Files to GitHub

```
bypay-bank/
├── index.html       ← Complete mobile banking app
├── manifest.json    ← Makes app installable on phone
├── sw.js            ← Offline support
└── README.md        ← This file
```

> ⚠️ All 4 files must be in the **same folder**.

---

## 🚀 Go Live in 5 Minutes

### Step 1 — Create GitHub Repo
1. Go to [github.com](https://github.com) → **New repository**
2. Name: `bypay-bank` → **Public** → **Create**

### Step 2 — Upload Files
1. Click **"uploading an existing file"**
2. Drag all 4 files → **Commit changes**

### Step 3 — Enable GitHub Pages
1. **Settings** → **Pages** → Branch: **main** → **Save**
2. Wait 2 minutes → live at:
```
https://YOUR-USERNAME.github.io/bypay-bank/
```

### Step 4 — Install on Phone
- **Android:** Chrome → ⋮ → **"Add to Home screen"**
- **iPhone:** Safari → Share → **"Add to Home Screen"**

Opens full screen — no browser bar — exactly like a real banking app!

---

## 🔑 Demo Login Credentials

| Role | Email | Password |
|------|-------|----------|
| Client (Verified) | sarah@mail.com | 1234 |
| Client (Pending KYC) | marcus@mail.com | 1234 |
| Client (Verified) | emily@mail.com | 1234 |

> **Demo PIN** for transfers: `1234`

---

## 🔐 Admin Login (Hidden from Public)

Two secret ways to access admin:

**Method 1 — URL:**
```
https://your-site.com/?admin
```

**Method 2 — Logo Tap:**
Tap the **"B" logo 7 times quickly** on the login screen → Admin login unlocks

**Admin credentials:**
| Email | Password |
|-------|----------|
| admin@bypaybank.com | admin123 |

---

## 📱 Full Feature List

### Client App
| Feature | Details |
|---------|---------|
| 🏠 Home | Balance card, quick actions, savings goals, transactions |
| ⚡ Zelle Transfer | Instant transfers to any US bank |
| 🏦 ACH / Wire | 1–3 business day transfers |
| 🧾 Pay Bills | 12 bill types: Electric, Gas, Water, Internet, Phone, Insurance, Mortgage, Credit Card, Streaming, Auto Loan, Student Loan, Other |
| 📷 Check Deposit | Mobile check deposit with availability schedule |
| 💳 Virtual Card | 3D flip VISA debit card with CVV |
| 🏛️ Personal Loans | $1,000–$50,000 at 8.99% APR |
| 🐖 Savings Goals | High-yield 4.50% APY |
| 📋 History | Search, filter, receipts |
| 🪪 KYC Profile | Full US identity verification |

### KYC Profile (4 sections)
| Section | Fields |
|---------|--------|
| Personal | First/Last Name, Date of Birth, Phone, Email, Tax ID |
| Address | Street, City, State (all 50), ZIP Code |
| ID & Passport | Passport/Driver's License/State ID/Military ID, ID Number, Expiry, SSN last 4 |
| Financial | Employment Status, Employer, Annual Income |

### Admin App
| Section | Details |
|---------|---------|
| 📊 Dashboard | KPIs, total deposits, savings, loans, client count |
| 👥 Clients | View full profile, verify KYC, freeze/unfreeze |
| 📋 Transactions | Full ledger for all clients |
| 🔔 Notifications | All alerts, mark as read |
| 👤 Client Detail | Complete profile including DOB, SSN, ID, address, income |

---

## 🔥 Connect Firebase (Real Database)

### Step 1 — Create Firebase Project
1. Go to [console.firebase.google.com](https://console.firebase.google.com)
2. **Add project** → name: `bypay-bank` → **Create**

### Step 2 — Enable Authentication
1. **Authentication** → **Get started** → **Email/Password** → Enable → **Save**

### Step 3 — Enable Firestore
1. **Firestore Database** → **Create database** → **Start in test mode** → **Done**

### Step 4 — Get Your Config
1. **⚙️ gear** → **Project settings** → **"</>"** (Web)
2. Register app → copy the config

### Step 5 — Paste into index.html
Find and replace:
```javascript
const FB_CONFIG={
  apiKey:"PASTE_YOUR_API_KEY_HERE",
  authDomain:"PASTE_YOUR_AUTH_DOMAIN_HERE",
  projectId:"PASTE_YOUR_PROJECT_ID_HERE",
  storageBucket:"PASTE_YOUR_STORAGE_BUCKET_HERE",
  messagingSenderId:"PASTE_YOUR_MESSAGING_SENDER_ID_HERE",
  appId:"PASTE_YOUR_APP_ID_HERE",
};
```

### Step 6 — Firestore Security Rules
Firebase Console → Firestore → **Rules** → replace all → **Publish**:
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.auth != null;
    }
  }
}
```

### Step 7 — Create Admin in Firebase
1. **Authentication** → **Users** → **Add user**
   - Email: `admin@bypaybank.com`
   - Password: your choice
   - Copy the **UID**
2. **Firestore** → **admin_users** collection → new document
   - Document ID: paste the UID
   - Fields: `name`, `email`, `role` (superadmin), `status` (active)

---

## 💬 Add Customer Chat (Crisp — Free)

1. Sign up at [crisp.chat](https://crisp.chat) (free)
2. Get your **Website ID**
3. In `index.html`, find:
```javascript
var CRISP_WEBSITE_ID="PASTE_YOUR_CRISP_WEBSITE_ID_HERE";
```
4. Replace with your ID → save → re-upload

---

## 🛠 Customise Bank Details

Open `index.html`, find the `BANK` constant:
```javascript
const BANK={
  name:"Bypay Bank",
  ceo:"Daniel Christopher Wilson",
  phone:"+1 (303) 555-0147",
  email:"support@bypaybank.com",
  address:"1700 Lincoln Street, Denver, CO 80203",
  routing:"102000076",
  fdic:"FDIC Insured",
  ...
};
```

---

## 🔒 Security Checklist

- [ ] Connect Firebase and update Firestore Rules
- [ ] Replace demo PIN (1234) with real OTP via Twilio/Vonage
- [ ] Replace demo SSN verification with real Socure/Stripe Identity API
- [ ] Enable Firebase App Check
- [ ] Set Firebase budget alerts
- [ ] Enable HTTPS (GitHub Pages does this automatically)
- [ ] NMLS registration for lending features

---

## 📞 Support

| | |
|--|--|
| **Bank** | Bypay Bank |
| **CEO** | Daniel Christopher Wilson |
| **Address** | 1700 Lincoln Street, Denver, CO 80203 |
| **Phone** | +1 (303) 555-0147 |
| **Email** | support@bypaybank.com |
| **FDIC** | Insured — Deposits protected up to $250,000 |

---

© 2026 Bypay Bank. All rights reserved. FDIC Insured.
