# ♻️ E-RECYCLO v2.0
### Next-Gen AI-Powered E-Waste Recycling & Logistics Ecosystem
*Transforming electronic waste management through automated AI classification, double-layer OTP-secured logistics, and seamless Razorpay financial clearing.*

---

[![Django](https://img.shields.io/badge/Django-4.2.7-092E20?style=for-the-badge&logo=django&logoColor=white)](https://www.djangoproject.com/)
[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Razorpay](https://img.shields.io/badge/Razorpay-Gateway-02042B?style=for-the-badge&logo=razorpay&logoColor=blue)](https://razorpay.com/)

---

## 🏗️ Project Overview

**E-RECYCLO** is a user-friendly, full-stack online platform built to make electronic waste (e-waste) disposal and recycling simple, secure, and rewarding. 

Instead of letting old, hazardous electronics end up in standard landfills, E-RECYCLO provides a complete digital ecosystem where household users can upload their e-waste, certified vendors can purchase and recycle it, and collection agents can handle the door-to-door logistics securely. Every step of the recycling journey is fully tracked online—from automated image recognition when you upload a photo of your device, to OTP-secured handovers during pickup and delivery, and instant online payments via Razorpay.

> **BE Project**  
> 🎓 **Department of Computer Engineering**  
> 🏫 **Dr. D. Y. Patil College of Engineering and Innovation, Varale, Pune**

---

## 👥 How It Works (Role-Based Dashboards)

The platform connects four key groups of users, each having a custom-tailored online dashboard:

### 📱 Clients (Household Recyclers)
*   **Simple Uploads:** Just upload a photo of your e-waste (like a broken phone, laptop, or charger) along with your pickup address.
*   **Instant AI Estimation:** The platform automatically identifies the device category, estimates its condition, and calculates a fair pricing tier.
*   **Eco Points & Wallet:** Earn cash directly in your online wallet when vendors accept your e-waste, or collect eco appreciation points for zero-value items to unlock green rank badges (from *Casual Recycler* up to *Eco Legend*).
*   **Easy Payouts:** Withdraw your wallet balance directly to your bank account or UPI address at any time (minimum ₹50).

### 🏭 Certified Vendors (Recyclers)
*   **Compliant Onboarding:** Register securely by uploading government-mandated documents (like GSTIN, PAN, and SPCB/CPCB e-waste authorization details) for admin verification.
*   **Smart Pricing & Bids:** Review assigned e-waste posts, dispatch pickup agents, evaluate received devices, and submit final purchasing offers online.
*   **Instant Wallet Top-Up:** Load funds securely using Razorpay (minimum ₹10) to cover e-waste purchases, processing, and transaction fees.

### 🚴 Collectors (Logistics Partners)
*   **Logistics Dashboard:** View nearby scheduled pickups, plan pickup dates, and track active trips on your map.
*   **OTP-Secured Handshakes:** Safe and fraud-proof deliveries. You must verify a 6-digit OTP from the client at the doorstep to start the pickup, and enter another OTP from the vendor upon successful delivery to finish the trip.
*   **Automated Earnings:** Receive automated fare settlements directly into your earnings wallet after each successful trip, calculated based on travel distance.

### 🔐 Administrators (Control Panel)
*   **Compliance Verification:** Review and approve pending vendor and collector profiles to maintain platform safety.
*   **Financial Approvals:** Review and clear pending wallet withdrawal requests via secure payouts, or trigger automatic refunds on rejections.
*   **Ecosystem Analytics:** Access visual charts showing monthly signup trends, e-waste upload volumes, and total processing values across the system.

---

## 🔄 Core E-Waste Lifecycle Path

```
 [CLIENT]                      [AI ENGINE]                [SYSTEM/ADMIN]              [COLLECTOR]                 [VENDOR]
    │                               │                            │                         │                         │
    │── 1. Uploads E-Waste Photo ──▶│                            │                         │                         │
    │                               │── 2. Analyzes Category ───▶│                         │                         │
    │                               │   & Estimated Value        │                         │                         │
    │                                                            │── 3. Assigns Post ───────────────────────────────▶│
    │                                                            │                                                   │── 4. Accepts Bid
    │                                                            │◀── Dispatches Collector ──────────────────────────│
    │                                                            │
    │◀─ 5. Receives pickup_otp ──────────────────────────────────│
    │                                                            │
    │── 6. Hands E-Waste + OTP ───────────────────────────────────────────────────────────▶│
    │                                                                                      │── 7. Verifies OTP & Starts Trip
    │                                                                                      │── 8. Arrives & Enters delivery_otp
    │                                                                                      │◀── (Generated by Vendor) ───────│
    │                                                                                      │
    │                                                                                      │── 9. Completed Trip & Paid ────▶│
    │                                                                                                                        │── 10. Evaluates Post
    │                                                                                                                        │── 11. Submits Offer
    │◀─ 12. Receives Final Payout Bid ───────────────────────────────────────────────────────────────────────────────────────│
    │── 13. ACCEPTS OFFER ──────────────────────────────────────────────────────────────────────────────────────────────────▶│
    │                                                                                                                        │── 14. Wallet Debited
    │◀─ 15. Wallet Credited & Request Payout ────────────────────────────────────────────────────────────────────────────────│
```

---

## 📂 System Folder Structure

```
E-RECYCLO/
├── apps/                         # Core Django application modules
│   ├── accounts/                 # Custom user authentication (Email OTP, Profile management)
│   ├── admin_custom/             # Custom analytics dashboard, profile review, & generic CRUD
│   ├── ai_services/              # AI classification engine for e-waste photo posts
│   ├── certificates/             # Certification generation for green recycling credits
│   ├── client/                   # Client upload portal, post lifecycle, & wallet dashboard
│   ├── collector/                # Collector pickup logs, OTP verification, & trip tracking
│   ├── notifications/            # Transactional system email logs & dispatch
│   ├── pages/                    # Public pages (Home, Privacy, Terms, Contact)
│   ├── payments/                 # Financial layer (Razorpay top-up, Payouts, Wallet ledger)
│   └── vendor/                   # Vendor pricing evaluation & e-waste inventory control
├── config/                       # Settings and routing configuration
│   ├── settings/                 # Modular settings (base, development, production)
│   │   ├── base.py               # Shared settings
│   │   ├── development.py        # Local settings
│   │   └── production.py         # Supabase & Vercel deployment settings
│   ├── urls.py                   # Global system URL patterns
│   └── validators.py             # Aadhaar, GSTIN, PAN, and phone formats
├── static/                       # Custom CSS, JS, and image assets
│   ├── css/                      # Structured Vanilla CSS styling
│   │   ├── unified-cards.css     # Unified dashboard styling
│   │   └── custom-forms.css      # Custom input fields styling
│   ├── images/                   # UI graphics & icons
│   └── js/                       # Interactive page behaviors
├── templates/                    # Dynamic HTML templates (organized by role)
│   ├── accounts/                 # OTP verification and authentication forms
│   ├── admin_custom/             # Custom analytics and approval layouts
│   ├── client/                   # Client-specific pages
│   ├── collector/                # Collector-specific pages
│   ├── payments/                 # Wallet, top-up, & withdrawal views
│   └── vendor/                   # Vendor-specific dashboards & forms
├── build_files.sh                # Vercel deployment shell script
├── manage.py                     # Django CLI gateway
├── requirements.txt              # Standard system dependencies
├── vercel.json                   # Vercel serverless functions configuration
└── .env-sample                   # Sample environment configuration template
```

---

## 🚀 Setup & Installation Guide

### 📋 Prerequisites
- Python 3.10 or higher installed.
- PostgreSQL database running (locally or on Supabase).
- Git installed.

### 💻 Step-by-Step Instructions

#### 1. Clone the repository
```bash
git clone https://github.com/beprojectdyp15/E-RECYCLO.v02.O.git
cd E-RECYCLO
```

#### 2. Create and activate a Virtual Environment
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

#### 3. Install core dependencies
```bash
pip install -r requirements.txt
```

#### 4. Configure local environment variables
Copy the sample environment configuration file:
```bash
# Windows
copy .env-sample .env

# macOS / Linux
cp .env-sample .env
```
Open the newly created `.env` file and enter your actual local values:
- Generate a unique Django `SECRET_KEY`.
- Set local PostgreSQL database credentials or paste your live Supabase connection string.
- Provide a valid Gmail account and a 16-character **Gmail App Password** for OTP delivery.
- Input your **Razorpay Test Keys** for sandboxed payment operations.

#### 5. Apply Database Migrations
```bash
python manage.py migrate
```

#### 6. Create a Superuser / Administrator
```bash
python manage.py createsuperuser
```

#### 7. Launch the Development Server
```bash
python manage.py runserver
```

Open your browser and navigate to: [http://127.0.0.1:8000/](http://127.0.0.1:8000/)

---

## 🔐 Advanced Security Features

### 🍯 The Honeypot Dashboard
E-RECYCLO uses a strict **honeypot security strategy** to block unauthorized access to the admin interface:
- Visiting the default Django `/admin/` path displays a **fake, authentic-looking login page**.
- Any login attempts made on this honeypot are flagged, automatically terminated, and logged in the system security reports.
- The **real, authorized administrative gateway** is routed privately under `/securelogin/`.

### 🛡️ Real-Time Regulatory Validation
To ensure full SPCB compliance, all registration forms run regex validation checks:
- **GSTIN Number:** Verified against standard `^[0-9]{2}[A-Z]{5}[0-9]{4}[A-Z]{1}[1-9A-Z]{1}Z[0-9A-Z]{1}$` formats.
- **PAN Number:** Validated against alphanumeric `^[A-Z]{5}[0-9]{4}[A-Z]{1}$` patterns.
- **Aadhaar Number:** Evaluated under length-specific `^\d{12}$` constraints.
- **Phone Fields:** Enforced to strictly matching Indian ten-digit formats.

### 💳 Double-Verification Payment Protection
- **HMAC Signature Check:** Client-side payment approvals are verified on the backend using server-side HMAC-SHA256 signature calculations to protect against client tampering.
- **Idempotent Webhooks:** Razorpay webhook triggers are tracked using custom `RazorpayOrder` models to prevent double-crediting wallets on network delays.

---

## 🛠️ CLI Management Commands

The platform features a custom Django administrative CLI utility to manage database cleanup and sandboxed payment configurations:

```bash
python manage.py mark_system_transactions [flags]
```

### 💡 Available Options:
*   **Dry-run (default):**  
    Running the command without any parameters scans the database, lists current records, and previews transaction updates without altering the database:
    ```bash
    python manage.py mark_system_transactions
    ```
*   **Apply Changes (`--apply`):**  
    Applies the changes, converting old development transactions into system-archived tags for testing clean Razorpay payment loops:
    ```bash
    python manage.py mark_system_transactions --apply
    ```
*   **Archive PhotoPosts (`--reset-posts`):**  
    Pairs with `--apply` to archive all old finished `PhotoPosts`, clearing out dashboard clutter:
    ```bash
    python manage.py mark_system_transactions --apply --reset-posts
    ```

---

## 👨‍💻 Primary Developer

**Aayan Mulla**  
🎓 BE Computer Engineering  
🏫 Dr. D. Y. Patil College of Engineering and Innovation, Varale, Pune.


