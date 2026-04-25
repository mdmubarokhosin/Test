# ShighroPay - Payment Gateway & CRM System

A complete payment gateway management system with enterprise-level CRM admin panel, built with HTML, Tailwind CSS, and Firebase Realtime Database.

## Features

### Admin Panel (`admin.html`)
- **Login System** - Password-protected with role-based access (Super Admin, Manager, Support)
- **Dashboard** - Real-time revenue charts, gateway usage, live transaction monitor
- **Transaction Management** - Search, filter, bulk actions, CSV export, status management
- **Customer CRM** - Full customer profiles, tags, notes, history tracking
- **Invoice System** - Create, send, track invoices (unpaid/paid/overdue)
- **Support Tickets** - Priority-based ticket system with status management
- **Dispute Management** - File, track, and resolve payment disputes
- **Merchant Management** - Add merchants, set commissions
- **Gateway Control** - Enable/disable payment methods, set commissions
- **Settlement Management** - Process merchant payouts
- **Announcements** - Create and publish system announcements
- **Reports** - Daily, monthly, gateway, customer reports with CSV export
- **Admin User Management** - Role-based admin accounts
- **Email Templates** - Trigger-based email template system
- **Settings** - System settings, maintenance mode, transaction limits, fraud detection
- **API & Webhooks** - API key generation, webhook configuration, IP whitelist
- **Coupon Management** - Create/manage discount coupons
- **Audit Logs** - Complete admin action logging
- **Backup & Restore** - Full data export/import, reset functionality
- **Dark Mode** - Full dark mode support

### User Dashboard (`dashboard.html`)
- Real-time transaction stats with 5 stat cards
- 7-day payment history chart (amount/count toggle)
- Payment method & status breakdown
- Recent activity timeline
- Transaction history with search, filter, pagination, date range
- CSV, JSON, PDF export
- Profile modal with user stats
- Notification center
- Quick action grid
- Dark mode support

### Checkout (`index.html`)
- Multi-step form (Customer Info -> Payment -> Processing)
- Bangladesh phone number validation (01XXXXXXXXX)
- 5 payment methods (bKash, Nagad, Rocket, Upay, SureCash)
- Coupon/discount code support
- Dynamic gateway loading from Firebase
- Order summary with discount display
- Transaction reference/note field
- Maintenance mode support
- SSL security indicators

### Success Page (`success.html`)
- Animated confetti celebration
- Detailed receipt card
- QR code for verification
- Share via WhatsApp, Email, SMS, Print, PDF
- Copy transaction ID
- Customer rating system (1-5 stars, saved to Firebase)
- Pending payment status support

### Failed Page (`failed.html`)
- Auto-retry with 30-second countdown
- Error details and troubleshooting tips
- Alternative payment method suggestions
- FAQ section
- Support ticket creation (saved to Firebase)
- Error logging to Firebase

### Additional Pages
- `contact.html` - Contact form with FAQ
- `terms.html` - Terms of Service
- `privacy.html` - Privacy Policy
- `merchants.html` - Merchant registration portal
- `404.html` - Custom error page

## Tech Stack

- **Frontend**: HTML5, Tailwind CSS (CDN)
- **Icons**: Bootstrap Icons (CDN)
- **Font**: Inter (Google Fonts)
- **Database**: Firebase Realtime Database
- **Auth**: Firebase Anonymous Authentication
- **No backend required** - Pure frontend with Firebase

## Firebase Configuration

The project uses Firebase Realtime Database with the following structure:

```
/transactions     - All payment transactions
/customers        - Customer profiles
/merchants        - Merchant accounts
/invoices         - Invoice records
/tickets          - Support tickets
/disputes         - Payment disputes
/settlements      - Settlement records
/announcements    - System announcements
/admin_users      - Admin user accounts
/email_templates  - Email template configs
/gateway_settings - Payment gateway configs
/system_settings  - System configuration
/admin_logs       - Audit trail
/api_settings     - API keys and webhooks
/coupons          - Discount coupons
/error_logs       - Error tracking
```

## Default Admin Credentials

| Role | Email | Password |
|------|-------|----------|
| Super Admin | admin@shighropay.com | admin123 |
| Manager | manager@shighropay.com | manager123 |
| Support | support@shighropay.com | support123 |

## Quick Start

1. Clone the repository
2. Open any HTML file in a browser
3. Login to admin panel with default credentials
4. Start processing payments!

No build process or server setup required - all files are standalone HTML.

## Payment Methods

| Method | Status | Description |
|--------|--------|-------------|
| bKash | Active | Mobile Banking |
| Nagad | Active | Digital Finance |
| Rocket | Active | DBBL Banking |
| Upay | Active | UCB Banking |
| SureCash | Active | Digital Payment |

## License

All rights reserved. ShighroPay 2025.
