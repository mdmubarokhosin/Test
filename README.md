# জামিয়া ইসলামিয়া দারুল উলূম — কওমি মাদরাসা ওয়েবসাইট ও ম্যানেজমেন্ট সিস্টেম

> কুরআন ও সুন্নাহর আলোকে পরিচালিত স্বনামধন্য কওমি মাদরাসার সম্পূর্ণ ওয়েবসাইট ও এডমিন ম্যানেজমেন্ট সিস্টেম। Next.js 16 + Firebase Realtime Database + Cloudflare Pages দিয়ে তৈরি।

---

## সূচিপত্র

- [প্রজেক্ট সম্পর্কে](#-প্রজেক্ট-সম্পর্কে)
- [বৈশিষ্ট্যসমূহ](#-বৈশিষ্ট্যসমূহ)
- [টেকনোলজি স্ট্যাক](#-টেকনোলজি-স্ট্যাক)
- [প্রজেক্ট স্ট্রাকচার](#-প্রজেক্ট-স্ট্রাকচার)
- [ইন্সটলেশন ও সেটআপ](#-ইন্সটলেশন-ও-সেটআপ)
  - [পূর্বশর্তাবলী](#-পূর্বশর্তাবলী)
  - [১. কোড ক্লোন করুন](#১-কোড-ক্লোন-করুন)
  - [২. এনভায়রনমেন্ট ভ্যারিয়েবল সেটআপ](#২-এনভায়রনমেন্ট-ভ্যারিয়েবল-সেটআপ)
  - [৩. Firebase সেটআপ](#৩-firebase-সেটআপ)
  - [৪. রুট ডিরেক্টরিতে ডেভেলপমেন্ট সার্ভার চালু করুন](#৪-রুট-ডিরেক্টরিতে-ডেভেলপমেন্ট-সার্ভার-চালু-করুন)
  - [৫. প্রোডাকশন বিল্ড](#৫-প্রোডাকশন-বিল্ড)
  - [৬. Cloudflare Pages ডিপ্লয়](#৬-cloudflare-pages-ডিপ্লয়)
- [এনভায়রনমেন্ট ভ্যারিয়েবল — সম্পূর্ণ তালিকা](#-এনভায়রনমেন্ট-ভ্যারিয়েবল--সম্পূর্ণ-তালিকা)
  - [A. লোকাল ডেভেলপমেন্ট (.env)](#a-লোকাল-ডেভেলপমেন্ট-env)
  - [B. Cloudflare Pages ড্যাশবোর্ড Environment Variables](#b-cloudflare-pages-ড্যাশবোর্ড-environment-variables)
- [Firebase RTDB রুলস — সম্পূর্ণ](#-firebase-rtdb-রুলস--সম্পূর্ণ)
  - [রুলস কোড](#-রুলস-কোড)
  - [রুলস সেটআপ পদ্ধতি](#-রুলস-সেটআপ-পদ্ধতি)
  - [রুলস ব্যাখ্যা](#-রুলস-ব্যাখ্যা)
- [ডাটাবেস স্ট্রাকচার](#-ডাটাবেস-স্ট্রাকচার)
- [এডমিন প্যানেল](#-এডমিন-প্যানেল)
- [পাবলিক পেজ সমূহ](#-পাবলিক-পেজ-সমূহ)
- [API রাউট](#-api-রাউট)
- [পেমেন্ট সিস্টেম](#-পেমেন্ট-সিস্টেম)
- [আন্তর্জাতিকীকরণ (i18n)](#-আন্তর্জাতিকীকরণ-i18n)
- [প্রোডাকশন ডিপ্লয়মেন্ট](#-প্রোডাকশন-ডিপ্লয়মেন্ট)
- [লাইসেন্স](#-লাইসেন্স)

---

## 📖 প্রজেক্ট সম্পর্কে

এটি একটি সম্পূর্ণ কওমি মাদরাসা ওয়েবসাইট ও ম্যানেজমেন্ট সিস্টেম। এটি মাদরাসার পাবলিক ওয়েবসাইট, এডমিন প্যানেল, শিক্ষার্থী পোর্টাল, অনলাইন পেমেন্ট, পরীক্ষা ব্যবস্থা এবং আরও অনেক ফিচার নিয়ে গঠিত। Next.js 16 এর Static Export (SPA) মোডে তৈরি এবং Cloudflare Pages-এ ডিপ্লয় করা হয়েছে। Firebase Realtime Database ব্যবহার করে রিয়েল-টাইম ডাটা সিঙ্ক করা হয়।

### মূল বৈশিষ্ট্য

- **SPA আর্কিটেকচার**: Next.js Static Export → একটি HTML ফাইল, ক্লায়েন্ট-সাইড রাউটিং
- **ফায়ারবেস RTDB**: রিয়েল-টাইম ডাটাবেস, Anonymous Auth
- **Cloudflare Pages Functions**: সার্ভার-সাইড API (পেমেন্ট webhook, Bohudur proxy)
- **তিনটি ভাষা**: বাংলা (ডিফল্ট), English, العربية (RTL সাপোর্ট)
- **অনলাইন পেমেন্ট**: Bohudur Payment Gateway (বিকাশ, নগদ, রকেট, কার্ড)
- **PWA সাপোর্ট**: Service Worker, Web App Manifest

---

## ✨ বৈশিষ্ট্যসমূহ

### পাবলিক ওয়েবসাইট (২৬টি পেজ)
| পেজ | বিবরণ |
|------|--------|
| হোম | হিরো সেকশন, মারকি, বিভাগ, শিক্ষক, নোটিশ, গ্যালারি ইত্যাদি |
| আমাদের সম্পর্কে | পরিচয়, দৃষ্টিভঙ্গি, লক্ষ্য |
| বিভাগসমূহ | হিফয, নাযেরা, আলিম, ফাজিল, তাকমিল ইত্যাদি |
| শিক্ষক তালিকা | শিক্ষকদের পরিচিতি ও বিবরণ |
| ভর্তি তথ্য | ভর্তির যোগ্যতা, কাগজপত্র, সময়সূচী |
| অনলাইন ভর্তি | ফর্ম পূরণ করে অনলাইনে আবেদন |
| নোটিশ বোর্ড | গুরুত্বপূর্ণ বিজ্ঞপ্তি |
| ইভেন্ট | আসন্ন ও সাম্প্রতিক অনুষ্ঠান |
| গ্যালারি | ফটো গ্যালারি |
| দান ও অনুদান | তহবিল, অনলাইন পেমেন্ট (Bohudur) |
| লেখা ও প্রবন্ধ | ব্লগ ও আর্টিকেল |
| যোগাযোগ | কন্টাক্ট ফর্ম |
| পরীক্ষার ফলাফল | রেজাল্ট দেখুন, মার্কশিট |
| ক্লাস রুটিন | সাপ্তাহিক ক্লাস রুটিন |
| সিলেবাস | পাঠ্যক্রম ও পাঠ্যতালিকা |
| হিফয ব্যবস্থাপনা | কুরআন হিফয রেকর্ড |
| অনলাইন পরীক্ষা | MCQ পরীক্ষা সিস্টেম |
| একাডেমিক ক্যালেন্ডার | বার্ষিক ক্যালেন্ডার |
| প্রাক্তন ছাত্র | অ্যালামনাই তালিকা |
| নামাজের সময়সূচী | প্রাত্যহিক নামাজের সময় |
| হাদীস সংগ্রহ | প্রামাণিক হাদীস |
| পবিত্র কুরআন | কুরআন তিলাওয়াত |
| ফি পেমেন্ট | অনলাইন ফি পরিশোধ |
| ভর্তি ট্র্যাকিং | আবেদনের অবস্থা দেখুন |
| লাইব্রেরি | পুস্তকালয় |
| উপস্থিতি | ছাত্র উপস্থিতি |
| হোস্টেল | ছাত্রাবাস তথ্য |
| দাওয়াত ও তাবলিগ | দাওয়াহ কর্মসূচি |
| পড়াশোনার উপকরণ | নোট, বই, লেকচার |

### এডমিন প্যানেল (৪০টি সেকশন)
ড্যাশবোর্ড, নোটিশ বোর্ড, শিক্ষক, বিভাগ, ছাত্র, পরীক্ষা, রেজাল্ট, ব্লগ, গ্যালারি, ভর্তি, দান, সেটিংস, মেসেজ, ইভেন্ট, আবেদন, অ্যাক্টিভিটি লগ, হিফয, MCQ পরীক্ষা, উপস্থিতি, লাইব্রেরি, ক্যালেন্ডার, ফি, অ্যালামনাই, নামাজ, হাদীস, SMS, ব্যাকআপ, পেমেন্ট হিস্ট্রি, খরচ, বেতন, ফাইন্যান্সিয়াল রিপোর্ট, ভাউচার, সাবস্ক্রিপশন, হোস্টেল, দাওয়াহ, স্টাডি ম্যাটেরিয়াল, রোল, QR পেমেন্ট, রিপোর্ট বিল্ডার।

---

## 🛠 টেকনোলজি স্ট্যাক

| ক্যাটাগরি | টেকনোলজি |
|-----------|-----------|
| **ফ্রন্টএন্ড** | Next.js 16.1, React 19, TypeScript 5 |
| **স্টাইলিং** | Tailwind CSS 4, tailwindcss-animate, tw-animate-css |
| **UI কম্পোনেন্ট** | Radix UI, shadcn/ui, Lucide Icons |
| **স্টেট ম্যানেজমেন্ট** | Zustand 5 |
| **ডাটাবেস** | Firebase Realtime Database |
| **অথেন্টিকেশন** | Firebase Anonymous Auth |
| **পেমেন্ট** | Bohudur Payment Gateway |
| **অ্যানিমেশন** | Framer Motion 12 |
| **ফর্ম** | React Hook Form + Zod |
| **ড্র্যাগ অ্যান্ড ড্রপ** | @dnd-kit/core, @dnd-kit/sortable |
| **চার্ট** | Recharts |
| **PDF জেনারেশন** | html2canvas-pro, jsPDF |
| **ডেট** | date-fns |
| **ডিপ্লয়মেন্ট** | Cloudflare Pages |
| **ফন্ট** | Noto Sans Bengali, Noto Sans Arabic (Google Fonts) |

---

## 📁 প্রজেক্ট স্ট্রাকচার

```
qawmi-madrasa-website/
├── .env                          # লোকাল এনভায়রনমেন্ট ভ্যারিয়েবল
├── .env.example                  # এনভায়রনমেন্ট ভ্যারিয়েবলের উদাহরণ
├── next.config.ts                # Next.js কনফিগারেশন (static export)
├── package.json                  # ডিপেন্ডেন্সি ও স্ক্রিপ্ট
├── tsconfig.json                 # TypeScript কনফিগারেশন
├── scripts/
│   └── build.mjs                 # বিল্ড স্ক্রিপ্ট (API backup/restore)
├── public/
│   ├── _headers                  # Cloudflare Pages security headers
│   ├── _redirects                # Cloudflare Pages SPA routing
│   ├── manifest.json             # PWA Web App Manifest
│   ├── sw.js                     # Service Worker
│   ├── robots.txt                # SEO robots
│   ├── logo.png                  # মাদরাসা লোগো
│   ├── logo.svg                  # SVG লোগো
│   ├── hero-bg.png               # হিরো সেকশন ব্যাকগ্রাউন্ড
│   ├── classroom.png             # ক্লাসরুম ইমেজ
│   ├── islamic-pattern.png       # ইসলামিক প্যাটার্ন
│   └── fonts/
│       └── NotoSansBengali.ttf   # বাংলা ফন্ট (ফলব্যাক)
├── functions/                    # Cloudflare Pages Functions (প্রোডাকশন API)
│   └── api/
│       ├── payment/
│       │   ├── webhook.ts        # Bohudur webhook handler
│       │   └── status.ts         # Payment status query
│       └── bohudur/
│           ├── check.ts          # API Key verification
│           ├── create.ts         # Payment creation proxy
│           ├── execute.ts        # Payment execution proxy
│           └── query.ts          # Payment status query proxy
├── src/
│   ├── app/
│   │   ├── layout.tsx            # Root layout (fonts, meta, PWA)
│   │   ├── page.tsx              # SPA entry point (রাউটার)
│   │   ├── globals.css           # Global styles
│   │   └── api/                  # Dev API routes (বিল্ডে backup হয়)
│   │       ├── payment/
│   │       │   ├── webhook/route.ts
│   │       │   └── status/route.ts
│   │       └── bohudur/
│   │           ├── check/route.ts
│   │           ├── create/route.ts
│   │           ├── execute/route.ts
│   │           └── query/route.ts
│   ├── components/
│   │   ├── madrasa/              # পাবলিক ওয়েবসাইট কম্পোনেন্ট
│   │   │   ├── Header.tsx
│   │   │   ├── Hero.tsx
│   │   │   ├── About.tsx
│   │   │   ├── Departments.tsx
│   │   │   ├── Teachers.tsx
│   │   │   ├── Admission.tsx
│   │   │   ├── OnlineAdmission.tsx
│   │   │   ├── NoticeBoard.tsx
│   │   │   ├── Results.tsx
│   │   │   ├── Gallery.tsx
│   │   │   ├── Donation.tsx
│   │   │   ├── DonatePayment.tsx
│   │   │   ├── Blog.tsx
│   │   │   ├── BlogDetail.tsx
│   │   │   ├── Contact.tsx
│   │   │   ├── Events.tsx
│   │   │   ├── Footer.tsx
│   │   │   ├── IslamicLoader.tsx
│   │   │   ├── PaymentCallback.tsx
│   │   │   └── SectionHeading.tsx
│   │   ├── pages/                # সাব-পেজ কম্পোনেন্ট (২৬টি)
│   │   │   ├── AboutPage.tsx
│   │   │   ├── DepartmentsPage.tsx
│   │   │   ├── TeachersPage.tsx
│   │   │   ├── NoticesPage.tsx
│   │   │   ├── EventsPage.tsx
│   │   │   ├── GalleryPage.tsx
│   │   │   ├── DonationPage.tsx
│   │   │   ├── BlogPage.tsx
│   │   │   ├── ContactPage.tsx
│   │   │   ├── ResultsPage.tsx
│   │   │   ├── AdmissionPage.tsx
│   │   │   ├── ClassRoutinePage.tsx
│   │   │   ├── SyllabusPage.tsx
│   │   │   ├── HifzPage.tsx
│   │   │   ├── OnlineExamPage.tsx
│   │   │   ├── CalendarPage.tsx
│   │   │   ├── AlumniPage.tsx
│   │   │   ├── PrayerTimePage.tsx
│   │   │   ├── HadithPage.tsx
│   │   │   ├── QuranPage.tsx
│   │   │   ├── FeePaymentPage.tsx
│   │   │   ├── AdmissionTrackPage.tsx
│   │   │   ├── LibraryPage.tsx
│   │   │   ├── AttendancePage.tsx
│   │   │   ├── HostelPage.tsx
│   │   │   ├── DawahPage.tsx
│   │   │   ├── MaterialsPage.tsx
│   │   │   ├── PageBanner.tsx
│   │   │   ├── PageSkeleton.tsx
│   │   │   └── BackToTop.tsx
│   │   ├── admin/                # এডমিন প্যানেল কম্পোনেন্ট (৪০টি)
│   │   │   ├── AdminLayout.tsx
│   │   │   ├── AdminLogin.tsx
│   │   │   ├── AdminDashboard.tsx
│   │   │   ├── AdminNotices.tsx
│   │   │   ├── AdminTeachers.tsx
│   │   │   ├── AdminDepartments.tsx
│   │   │   ├── AdminStudents.tsx
│   │   │   ├── AdminExams.tsx
│   │   │   ├── AdminResults.tsx
│   │   │   ├── AdminBlogs.tsx
│   │   │   ├── AdminGallery.tsx
│   │   │   ├── AdminAdmission.tsx
│   │   │   ├── AdminDonation.tsx
│   │   │   ├── AdminSettings.tsx
│   │   │   ├── AdminMessages.tsx
│   │   │   ├── AdminEvents.tsx
│   │   │   ├── AdminApplications.tsx
│   │   │   ├── AdminActivityLog.tsx
│   │   │   ├── AdminHifz.tsx
│   │   │   ├── AdminMCQExams.tsx
│   │   │   ├── AdminAttendance.tsx
│   │   │   ├── AdminLibrary.tsx
│   │   │   ├── AdminCalendar.tsx
│   │   │   ├── AdminFee.tsx
│   │   │   ├── AdminAlumni.tsx
│   │   │   ├── AdminPrayer.tsx
│   │   │   ├── AdminHadith.tsx
│   │   │   ├── AdminSMS.tsx
│   │   │   ├── AdminBackup.tsx
│   │   │   ├── AdminPaymentHistory.tsx
│   │   │   ├── AdminExpenses.tsx
│   │   │   ├── AdminSalary.tsx
│   │   │   ├── AdminFinancialReports.tsx
│   │   │   ├── AdminVouchers.tsx
│   │   │   ├── AdminSubscriptions.tsx
│   │   │   ├── AdminHostel.tsx
│   │   │   ├── AdminDawah.tsx
│   │   │   ├── AdminMaterials.tsx
│   │   │   ├── AdminRoles.tsx
│   │   │   ├── AdminQRPayment.tsx
│   │   │   └── AdminReportBuilder.tsx
│   │   ├── student/
│   │   │   └── StudentPortal.tsx  # শিক্ষার্থী পোর্টাল + মার্কশিট
│   │   └── ui/                   # shadcn/ui কম্পোনেন্ট (৪০+)
│   ├── lib/
│   │   ├── firebase.ts           # Firebase config & auth helpers
│   │   ├── db-service.ts         # RTDB CRUD helpers (dbGet, dbSet, dbPush, etc.)
│   │   ├── i18n.ts               # বাংলা/ইংরেজি/আরবি অনুবাদ (৫০০+ keys)
│   │   ├── i18n-context.tsx      # i18n React Context Provider
│   │   ├── theme-context.tsx     # Dark/Light theme context
│   │   └── utils.ts              # Utility functions (cn helper)
│   ├── store/
│   │   └── app-store.ts          # Zustand store (সম্পূর্ণ স্টেট ম্যানেজমেন্ট)
│   ├── types/
│   │   └── database.ts           # সম্পূর্ণ TypeScript টাইপ ডেফিনিশন
│   └── hooks/
│       ├── use-mobile.ts         # Mobile detection hook
│       └── use-toast.ts          # Toast notification hook
└── out/                          # বিল্ড আউটপুট (static export)
```

---

## 🚀 ইন্সটলেশন ও সেটআপ

### 📋 পূর্বশর্তাবলী

- **Node.js**: v18.17+ (v20+ রেকমেন্ডেড)
- **npm** বা **bun** (প্যাকেজ ম্যানেজার)
- **Firebase প্রজেক্ট**: [Firebase Console](https://console.firebase.google.com/) থেকে তৈরি
- **Cloudflare অ্যাকাউন্ট**: [Cloudflare Pages](https://pages.cloudflare.com/) (ডিপ্লয়মেন্টের জন্য)
- **Bohudur অ্যাকাউন্ট**: [Bohudur](https://bohudur.one/) (পেমেন্ট গেটওয়ের জন্য, ঐচ্ছিক)

---

### ১. কোড ক্লোন করুন

```bash
git clone <your-repo-url>
cd qawmi-madrasa-website
```

---

### ২. এনভায়রনমেন্ট ভ্যারিয়েবল সেটআপ

প্রজেক্ট রুটে `.env` ফাইল তৈরি করুন:

```bash
cp .env.example .env
```

`.env` ফাইলে নিচের ভ্যারিয়েবলগুলো সেট করুন:

```env
# ===== Firebase Configuration =====
# Firebase Console > Project Settings > Your Apps > Web App > Config
NEXT_PUBLIC_FIREBASE_API_KEY=AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXXX
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your-project.firebaseapp.com
NEXT_PUBLIC_FIREBASE_DATABASE_URL=https://your-project-default-rtdb.firebaseio.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your-project-id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your-project.appspot.com
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=123456789
NEXT_PUBLIC_FIREBASE_APP_ID=1:123456789:web:abcdef123456

# ===== Bohudur Payment API (Optional) =====
BOHUDUR_API_KEY=your_bohudur_api_key_here
```

> **গুরুত্বপূর্ণ**: `NEXT_PUBLIC_FIREBASE_DATABASE_URL` অবশ্যই সঠিক RTDB URL হতে হবে। ফরম্যাট: `https://your-project-default-rtdb.firebaseio.com`

---

### ৩. Firebase সেটআপ

#### ৩.১ Firebase প্রজেক্ট তৈরি

1. [Firebase Console](https://console.firebase.google.com/) → **Add Project**
2. প্রজেক্টের নাম দিন
3. Google Analytics বন্ধ করতে পারেন (ঐচ্ছিক)

#### ৩.২ Realtime Database তৈরি

1. Firebase Console → **Build** → **Realtime Database** → **Create Database**
2. Location: **asia-southeast1** (সিঙ্গাপুর, BD থেকে দ্রুত)
3. Start in **Test Mode** (পরে রুলস আপডেট করবেন)

#### ৩.৩ Anonymous Auth সক্রিয় করুন

1. Firebase Console → **Build** → **Authentication** → **Sign-in method**
2. **Anonymous** → **Enable**
3. Save করুন

> এই প্রজেক্ট `signInAnonymously` ব্যবহার করে RTDB রাইট পারমিশন পাওয়ার জন্য।

#### ৩.৪ Web App রেজিস্টার করুন

1. Firebase Console → **Project Settings** → **General** → **Your Apps** → **Add App** → Web (`</>`)
2. অ্যাপের নাম দিন (যেমন: "Madrasa Website")
3. **Firebase Hosting** চেক বক্স বন্ধ করুন (Cloudflare Pages ব্যবহার করব)
4. **Register App**
5. দেখানো `firebaseConfig` অবজেক্ট থেকে ভ্যালু কপি করে `.env` ফাইলে পেস্ট করুন

#### ৩.৫ RTDB Rules সেটআপ

1. Firebase Console → **Realtime Database** → **Rules** ট্যাব
2. নিচের **[RTDB Rules](#-রুলস-কোড)** সেকশন থেকে সম্পূর্ণ JSON কপি করুন
3. পেস্ট করে **Publish** ক্লিক করুন

#### ৩.৬ Database Secret তৈরি (Cloudflare Functions এর জন্য)

1. Firebase Console → **Project Settings** → **Service Accounts** → **Database Secrets** → **New Secret**
2. Secret কপি করুন — এটি Cloudflare Pages Environment Variables-এ লাগবে

---

### ৪. রুট ডিরেক্টরিতে ডেভেলপমেন্ট সার্ভার চালু করুন

```bash
# ডিপেন্ডেন্সি ইন্সটল
npm install

# ডেভেলপমেন্ট সার্ভার চালু (http://localhost:3000)
npm run dev
```

ব্রাউজারে [http://localhost:3000](http://localhost:3000) ওপেন করুন।

---

### ৫. প্রোডাকশন বিল্ড

```bash
# বিল্ড স্ক্রিপ্ট চালান (API routes backup → Next.js build → API restore)
npm run build
```

বিল্ড আউটপুট: `out/` ডিরেক্টরি

বিল্ড প্রসেস:
1. `scripts/build.mjs` স্ক্রিপ্ট `src/app/api/` ডিরেক্টরিকে `.api_backup/` তে সরিয়ে রাখে
2. `next build --webpack` চালিয়ে `out/` ফোল্ডারে static export তৈরি করে
3. API ডিরেক্টরি আবার রিস্টোর করে

---

### ৬. Cloudflare Pages ডিপ্লয়

#### ৬.১ Cloudflare এ কানেক্ট করুন

1. [Cloudflare Pages](https://pages.cloudflare.com/) → **Create a project** → **Connect to Git**
2. GitHub/GitLab রিপো সিলেক্ট করুন

#### ৬.২ বিল্ড সেটিংস

| সেটিং | ভ্যালু |
|--------|--------|
| **Build command** | `npm run build` |
| **Build output directory** | `out` |
| **Root directory** | `/` (ডিফল্ট) |
| **Node.js version** | `20` |

#### ৬.৩ Environment Variables সেট করুন

Cloudflare Pages → Settings → Environment Variables:

| ভ্যারিয়েবল | ভ্যালু | বিবরণ |
|-------------|--------|--------|
| `NEXT_PUBLIC_FIREBASE_API_KEY` | `AIzaSy...` | Firebase API Key |
| `NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN` | `xxx.firebaseapp.com` | Firebase Auth Domain |
| `NEXT_PUBLIC_FIREBASE_DATABASE_URL` | `https://xxx.firebaseio.com` | RTDB URL |
| `NEXT_PUBLIC_FIREBASE_PROJECT_ID` | `xxx` | Firebase Project ID |
| `NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET` | `xxx.appspot.com` | Firebase Storage Bucket |
| `NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID` | `123456789` | Firebase Sender ID |
| `NEXT_PUBLIC_FIREBASE_APP_ID` | `1:123:web:xxx` | Firebase App ID |
| `BOHUDUR_API_KEY` | `your_key` | Bohudur API Key (ঐচ্ছিক) |
| `FIREBASE_DATABASE_URL` | `https://xxx.firebaseio.com` | RTDB URL (server-side) |
| `FIREBASE_DB_SECRET` | `your_db_secret` | Firebase DB Secret (webhook) |

> **গুরুত্বপূর্ণ**: Cloudflare Pages Functions এ `FIREBASE_DB_SECRET` ব্যবহার করে webhook থেকে RTDB লেখার জন্য। এটি ছাড়া payment webhook কাজ করবে না।

#### ৬.৪ ডিপ্লয়

Save করুন → Cloudflare অটোমেটিক বিল্ড ও ডিপ্লয় করবে।

---

## 🔑 এনভায়রনমেন্ট ভ্যারিয়েবল — সম্পূর্ণ তালিকা

### A. লোকাল ডেভেলপমেন্ট (.env)

নিচের ভ্যারিয়েবলগুলো প্রজেক্ট রুটের `.env` ফাইলে থাকে:

| # | ভ্যারিয়েবল | উদাহরণ | প্রয়োজনীয়? | বিবরণ |
|---|-------------|--------|:---:|--------|
| 1 | `NEXT_PUBLIC_FIREBASE_API_KEY` | `AIzaSyD...abc` | ✅ | Firebase Web API Key |
| 2 | `NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN` | `my-project.firebaseapp.com` | ✅ | Firebase Auth Domain |
| 3 | `NEXT_PUBLIC_FIREBASE_DATABASE_URL` | `https://my-project-default-rtdb.firebaseio.com` | ✅ | Firebase RTDB URL (সবচেয়ে গুরুত্বপূর্ণ) |
| 4 | `NEXT_PUBLIC_FIREBASE_PROJECT_ID` | `my-project-id` | ✅ | Firebase Project ID |
| 5 | `NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET` | `my-project.appspot.com` | ❌ | Firebase Storage Bucket |
| 6 | `NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID` | `123456789` | ❌ | Firebase Cloud Messaging Sender ID |
| 7 | `NEXT_PUBLIC_FIREBASE_APP_ID` | `1:123:web:abc` | ❌ | Firebase App ID |
| 8 | `BOHUDUR_API_KEY` | `bohudur_key_xxx` | ❌ | Bohudur Payment API Key |

**কোথায় পাবেন:**
- **#1-7**: Firebase Console → Project Settings → General → Your Apps → Web App → Config
- **#8**: [Bohudur Dashboard](https://bohudur.one/) → API Keys

### B. Cloudflare Pages ড্যাশবোর্ড Environment Variables

Cloudflare Pages → Settings → Environment Variables-এ সেট করতে হবে:

| # | ভ্যারিয়েবল | উদাহরণ | প্রয়োজনীয়? | বিবরণ |
|---|-------------|--------|:---:|--------|
| 1 | `NEXT_PUBLIC_FIREBASE_API_KEY` | `AIzaSyD...abc` | ✅ | (লোকালের মতোই) |
| 2 | `NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN` | `my-project.firebaseapp.com` | ✅ | (লোকালের মতোই) |
| 3 | `NEXT_PUBLIC_FIREBASE_DATABASE_URL` | `https://my-project-default-rtdb.firebaseio.com` | ✅ | (লোকালের মতোই) |
| 4 | `NEXT_PUBLIC_FIREBASE_PROJECT_ID` | `my-project-id` | ✅ | (লোকালের মতোই) |
| 5 | `NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET` | `my-project.appspot.com` | ❌ | (লোকালের মতোই) |
| 6 | `NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID` | `123456789` | ❌ | (লোকালের মতোই) |
| 7 | `NEXT_PUBLIC_FIREBASE_APP_ID` | `1:123:web:abc` | ❌ | (লোকালের মতোই) |
| 8 | `BOHUDUR_API_KEY` | `bohudur_key_xxx` | ❌ | (লোকালের মতোই) |
| 9 | `FIREBASE_DATABASE_URL` | `https://my-project-default-rtdb.firebaseio.com` | ✅ | **Server-side RTDB URL** (Functions দ্বারা ব্যবহৃত) |
| 10 | `FIREBASE_DB_SECRET` | `abcXYZ123def...` | ✅ | **Firebase Database Secret** (webhook auth) |

**কোথায় পাবেন:**
- **#9**: Firebase Console → Realtime Database URL (উপরে #3 এর মতোই)
- **#10**: Firebase Console → Project Settings → Service Accounts → Database Secrets

> **⚠️ সতর্কতা**: `FIREBASE_DB_SECRET` অত্যন্ত সংবেদনশীল। এটি কোনোভাবে ক্লায়েন্ট-সাইডে এক্সপোজ করবেন না। শুধুমাত্র Cloudflare Pages Environment Variables-এ সেট করুন।

---

## 🔒 Firebase RTDB রুলস — সম্পূর্ণ

### রুলস কোড

Firebase Console → Realtime Database → Rules ট্যাবে নিচের JSON পেস্ট করুন:

```json
{
  "rules": {
    ".read": false,
    ".write": false,

    "config": {
      "siteInfo": {
        ".read": true,
        ".write": "auth != null"
      },
      "githubConfig": {
        ".read": true,
        ".write": "auth != null"
      },
      "paymentMethods": {
        ".read": true,
        ".write": "auth != null"
      },
      "classRoutine": {
        ".read": true,
        ".write": "auth != null"
      },
      "syllabus": {
        ".read": true,
        ".write": "auth != null"
      },
      "bohudurApiKey": {
        ".read": true,
        ".write": "auth != null"
      },
      "bohudurConfig": {
        ".read": true,
        ".write": "auth != null"
      },
      "prayerConfig": {
        ".read": true,
        ".write": "auth != null"
      },
      "qrPaymentConfig": {
        ".read": true,
        ".write": "auth != null"
      },
      "adminAuth": {
        ".read": "auth != null",
        ".write": "auth != null"
      }
    },

    "settings": {
      "adminAuth": {
        ".read": "auth != null",
        ".write": "auth != null"
      }
    },

    "notices": {
      ".read": true,
      ".write": "auth != null",
      "$noticeId": {
        ".validate": "newData.hasChildren(['title', 'content', 'date'])"
      }
    },

    "departments": {
      ".read": true,
      ".write": "auth != null",
      "$deptId": {
        ".validate": "newData.hasChildren(['name', 'description'])"
      }
    },

    "teachers": {
      ".read": true,
      ".write": "auth != null",
      "$teacherId": {
        ".validate": "newData.hasChildren(['name', 'designation'])"
      }
    },

    "students": {
      ".read": true,
      ".write": "auth != null",
      "$studentId": {
        ".validate": "newData.hasChildren(['name', 'roll', 'department'])"
      }
    },

    "exams": {
      ".read": true,
      ".write": "auth != null",
      "$examId": {
        ".validate": "newData.hasChildren(['name', 'year'])"
      }
    },

    "results": {
      ".read": true,
      ".write": "auth != null",
      "$resultId": {
        ".validate": "newData.hasChildren(['studentName', 'examId', 'subjects'])"
      }
    },

    "blogs": {
      ".read": true,
      ".write": "auth != null",
      "$blogId": {
        ".validate": "newData.hasChildren(['title', 'content'])"
      }
    },

    "gallery": {
      ".read": true,
      ".write": "auth != null",
      "$itemId": {
        ".validate": "newData.hasChildren(['title', 'imageUrl'])"
      }
    },

    "admission": {
      ".read": true,
      ".write": "auth != null",
      "$admissionId": {
        ".validate": "newData.hasChildren(['year'])"
      }
    },

    "donations": {
      ".read": true,
      ".write": "auth != null",
      "$fundId": {
        ".validate": "newData.hasChildren(['title', 'collected', 'target'])"
      }
    },

    "events": {
      ".read": true,
      ".write": "auth != null",
      "$eventId": {
        ".validate": "newData.hasChildren(['title', 'date'])"
      }
    },

    "contactMessages": {
      ".read": "auth != null",
      ".write": true,
      "$messageId": {
        ".validate": "newData.hasChildren(['name', 'message'])"
      }
    },

    "admissionApplications": {
      ".read": "auth != null",
      ".write": true,
      "$appId": {
        ".validate": "newData.hasChildren(['studentName', 'phone'])"
      }
    },

    "activityLogs": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$logId": {
        ".validate": "newData.hasChildren(['action', 'details', 'timestamp'])"
      }
    },

    "payments": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$paymentId": {
        ".validate": "newData.hasChildren(['paymentkey', 'status'])"
      },
      ".indexOn": ["paymentkey", "createdAt", "status"]
    },

    "hifzRecords": {
      ".read": true,
      ".write": "auth != null",
      "$hifzId": {
        ".validate": "newData.hasChildren(['studentName', 'currentJuz'])"
      }
    },

    "onlineExams": {
      ".read": true,
      ".write": "auth != null",
      "$examId": {
        ".validate": "newData.hasChildren(['title', 'questions'])"
      }
    },

    "examSubmissions": {
      ".read": "auth != null",
      ".write": true,
      "$submissionId": {
        ".validate": "newData.hasChildren(['examId', 'studentRoll', 'answers'])"
      }
    },

    "libraryBooks": {
      ".read": true,
      ".write": "auth != null",
      "$bookId": {
        ".validate": "newData.hasChildren(['title', 'author', 'category'])"
      }
    },

    "calendarEvents": {
      ".read": true,
      ".write": "auth != null",
      "$eventId": {
        ".validate": "newData.hasChildren(['title', 'date'])"
      }
    },

    "alumni": {
      ".read": true,
      ".write": "auth != null",
      "$alumniId": {
        ".validate": "newData.hasChildren(['name', 'passingYear'])"
      }
    },

    "feeConfigs": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$configId": {
        ".validate": "newData.hasChildren(['class', 'amount'])"
      }
    },

    "feePayments": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$feeId": {
        ".validate": "newData.hasChildren(['studentName', 'amount', 'month'])"
      }
    },

    "expenses": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$expenseId": {
        ".validate": "newData.hasChildren(['title', 'amount', 'date'])"
      }
    },

    "expenseCategories": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$catId": {
        ".validate": "newData.hasChildren(['name'])"
      }
    },

    "salaryRecords": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$salaryId": {
        ".validate": "newData.hasChildren(['teacherName', 'netSalary', 'month'])"
      }
    },

    "donationSubscriptions": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$subId": {
        ".validate": "newData.hasChildren(['donorName', 'amount', 'frequency'])"
      }
    },

    "vouchers": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$voucherId": {
        ".validate": "newData.hasChildren(['voucherNumber', 'type', 'amount'])"
      }
    },

    "hostelRooms": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$roomId": {
        ".validate": "newData.hasChildren(['roomNumber', 'capacity'])"
      }
    },

    "hostelAllocations": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$allocId": {
        ".validate": "newData.hasChildren(['studentName', 'roomId'])"
      }
    },

    "hostelMeals": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$mealId": {
        ".validate": "newData.hasChildren(['day', 'date'])"
      }
    },

    "dawahPrograms": {
      ".read": true,
      ".write": "auth != null",
      "$programId": {
        ".validate": "newData.hasChildren(['title', 'date', 'type'])"
      }
    },

    "dawahJamats": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$jamatId": {
        ".validate": "newData.hasChildren(['name', 'leaderName'])"
      }
    },

    "studyMaterials": {
      ".read": true,
      ".write": "auth != null",
      "$materialId": {
        ".validate": "newData.hasChildren(['title', 'category', 'fileUrl'])"
      }
    },

    "adminRoles": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$roleId": {
        ".validate": "newData.hasChildren(['name', 'permissions'])"
      }
    },

    "adminUsers": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$userId": {
        ".validate": "newData.hasChildren(['username', 'password', 'name', 'roleId'])"
      }
    }
  }
}
```

### রুলস সেটআপ পদ্ধতি

1. **Firebase Console** → আপনার প্রজেক্ট খুলুন
2. **Build** → **Realtime Database** → **Rules** ট্যাব
3. উপরের সম্পূর্ণ JSON পেস্ট করুন (পুরানো রুলস মুছে ফেলুন)
4. **Publish** বাটনে ক্লিক করুন

### রুলস ব্যাখ্যা

**Auth মডেল**: প্রজেক্ট `signInAnonymously` ব্যবহার করে। তাই:
- `auth != null` = কেউ সাইটে এসেছে এবং anonymous sign-in হয়েছে (যেকেই সাইট ভিজিট করুক না কেন)
- `.write: true` = কেউ লিখতে পারে, auth ছাড়াই (পাবলিক ফর্মের জন্য)

**পাবলিক রিড (.read: true)** — যেগুলো সবাই পড়তে পারে:
- `/config/*` (সাইট তথ্য, রুটিন, সিলেবাস, পেমেন্ট মেথড, নামাজের সময়, QR কনফিগ)
- `/notices`, `/departments`, `/teachers`, `/students`, `/exams`, `/results`
- `/blogs`, `/gallery`, `/admission`, `/donations`, `/events`
- `/hifzRecords`, `/onlineExams`, `/libraryBooks`, `/calendarEvents`
- `/alumni`, `/dawahPrograms`, `/studyMaterials`

**অথেন্টিকেটেড-অনলি রিড (.read: auth != null)** — এডমিন প্যানেল এক্সেস প্রয়োজন:
- `/config/adminAuth` (পাসওয়ার্ড)
- `/contactMessages`, `/admissionApplications`
- `/activityLogs`, `/payments`, `/examSubmissions`
- `/feeConfigs`, `/feePayments`, `/expenses`, `/expenseCategories`
- `/salaryRecords`, `/donationSubscriptions`, `/vouchers`
- `/hostelRooms`, `/hostelAllocations`, `/hostelMeals`
- `/dawahJamats`, `/adminRoles`, `/adminUsers`

**পাবলিক রাইট (.write: true)** — পাবলিক ইউজার লিখতে পারে:
- `/contactMessages` — কন্টাক্ট ফর্ম সাবমিশন
- `/admissionApplications` — ভর্তি আবেদন
- `/examSubmissions` — অনলাইন পরীক্ষার উত্তর

**Server-side Access**: Cloudflare Pages Functions `FIREBASE_DB_SECRET` ব্যবহার করে, যা সব RTDB রুল বাইপাস করে। তাই webhook ও Bohudur API-তে কোনো সমস্যা হয় না।

**ইনডেক্স**: `/payments` এ `paymentkey`, `createdAt`, `status` ইনডেক্স আছে — webhook-এর `orderBy="paymentkey"` কোয়েরি দ্রুত কাজ করে।

---

## 🗄 ডাটাবেস স্ট্রাকচার

Firebase RTDB তে ডাটা নিচের গঠনে সংরক্ষিত:

```
{
  "config": {
    "siteInfo": { name, nameAr, slogan, address, phone, email, ... },
    "adminAuth": { password: "admin123" },
    "githubConfig": { token, owner, repo, branch },
    "paymentMethods": [ { name, number, type } ],
    "classRoutine": [ { time, subject, teacher, duration } ],
    "syllabus": [ { name, year } ],
    "bohudurApiKey": "key_string",
    "bohudurConfig": { enabled, apiKey, currency, redirectUrl, ... },
    "prayerConfig": { fajr, dhuhr, asr, maghrib, isha, jummah },
    "qrPaymentConfig": { enabled, bkashNumber, bkashQR, nagadNumber, ... }
  },
  "notices": { "-id": { title, content, date, important, createdAt } },
  "departments": { "-id": { name, nameAr, description, icon, imageUrl, order } },
  "teachers": { "-id": { name, nameAr, designation, qualification, department, imageUrl, order } },
  "students": { "-id": { name, roll, department, class, fatherName, admissionYear, imageUrl, createdAt } },
  "exams": { "-id": { name, year, department, class, date, createdAt } },
  "results": { "-id": { studentId, studentName, studentRoll, registrationNumber, examId, examName, department, class, subjects: [{name, fullMarks, obtainedMarks}], totalMarks, obtainedTotal, grade, createdAt } },
  "blogs": { "-id": { title, content, category, date, imageUrl, createdAt } },
  "gallery": { "-id": { title, category, imageUrl, createdAt } },
  "admission": { "-id": { year, requirements, documents, schedule } },
  "donations": { "-id": { title, titleAr, description, collected, target, type } },
  "events": { "-id": { title, description, date, time, location, type, important, createdAt } },
  "contactMessages": { "-id": { name, email, phone, message, date, isRead, createdAt } },
  "admissionApplications": { "-id": { studentName, fatherName, motherName, dateOfBirth, phone, address, previousEducation, desiredDepartment, desiredClass, bloodGroup, guardianPhone, imageUrl, status, createdAt } },
  "activityLogs": { "-id": { action, details, timestamp } },
  "payments": { "-id": { full_name, email, phone, amount, paymentkey, fund_title, status, createdAt, updatedAt } },
  "hifzRecords": { "-id": { studentId, studentName, studentRoll, department, currentJuz, currentSurah, currentAyah, totalMemorized, status, startDate, lastUpdated, createdAt } },
  "onlineExams": { "-id": { title, subject, department, class, duration, totalMarks, questions: [{question, options, correctAnswer}], status, createdAt } },
  "examSubmissions": { "-id": { examId, studentRoll, studentName, answers, obtainedMarks, totalMarks, submittedAt } },
  "libraryBooks": { "-id": { title, author, category, isbn, totalCopies, availableCopies, shelfLocation, status, addedBy, createdAt } },
  "calendarEvents": { "-id": { title, description, date, type, isHoliday, createdAt } },
  "alumni": { "-id": { name, studentRoll, passingYear, department, currentOccupation, phone, email, address, imageUrl, status, createdAt } },
  "feeConfigs": { "-id": { class, department, amount, type, description, createdAt } },
  "feePayments": { "-id": { studentId, studentName, studentRoll, feeConfigId, amount, month, year, status, paidAmount, paymentMethod, paymentDate, createdAt } },
  "expenses": { "-id": { title, category, amount, date, description, createdBy, approvedBy, status, createdAt } },
  "expenseCategories": { "-id": { name, description, budget, createdAt } },
  "salaryRecords": { "-id": { teacherId, teacherName, designation, department, basicSalary, allowance, deduction, netSalary, month, year, status, paidAmount, paidDate, paymentMethod, notes, createdAt } },
  "donationSubscriptions": { "-id": { donorName, donorPhone, donorEmail, amount, frequency, fundId, startDate, endDate, status, lastPaidDate, nextDueDate, totalPaid, createdAt } },
  "vouchers": { "-id": { voucherNumber, type, title, description, amount, date, category, relatedTo, createdBy, createdAt } },
  "hostelRooms": { "-id": { roomNumber, floor, capacity, currentOccupants, type, status, createdAt } },
  "hostelAllocations": { "-id": { studentId, studentName, studentRoll, roomId, roomNumber, bedNumber, allocationDate, status, releasedDate, createdAt } },
  "hostelMeals": { "-id": { day, date, breakfast, lunch, dinner, createdAt } },
  "dawahPrograms": { "-id": { title, description, date, location, coordinatorName, coordinatorPhone, participantCount, type, status, createdAt } },
  "dawahJamats": { "-id": { name, leaderName, memberCount, currentLocation, departureDate, returnDate, status, report, createdAt } },
  "studyMaterials": { "-id": { title, description, category, department, class, fileUrl, fileType, downloadCount, addedBy, createdAt } },
  "adminRoles": { "-id": { name, description, permissions, createdAt } },
  "adminUsers": { "-id": { username, password, name, roleId, roleName, isActive, lastLogin, createdAt } }
}
```

> সম্পূর্ণ TypeScript টাইপ ডেফিনিশন `src/types/database.ts` ফাইলে পাওয়া যাবে।

---

## 🔐 এডমিন প্যানেল

- **URL**: আপনার ওয়েবসাইটে হেডারে "এডমিন" বাটনে ক্লিক করুন, অথবা সরাসরি URL-এ `/admin` যান
- **ডিফল্ট পাসওয়ার্ড**: `admin123`
- **পাসওয়ার্ড পরিবর্তন**: এডমিন প্যানেল → Settings → নতুন পাসওয়ার্ড সেট করুন
- **পাসওয়ার্ড সেভ হয়**: Firebase RTDB `/config/adminAuth` বা `/settings/adminAuth` পথে

---

## 🌐 পাবলিক পেজ সমূহ

প্রতিটি পেজ ক্লায়েন্ট-সাইড রাউটিং দিয়ে কাজ করে (SPA আর্কিটেকচার):

| রাউট | পেজ | রাউট | পেজ |
|------|------|------|------|
| `/` | হোম | `/hifz` | হিফয ব্যবস্থাপনা |
| `/about` | আমাদের সম্পর্কে | `/exam` | অনলাইন পরীক্ষা |
| `/departments` | বিভাগসমূহ | `/calendar` | একাডেমিক ক্যালেন্ডার |
| `/teachers` | শিক্ষক তালিকা | `/alumni` | প্রাক্তন ছাত্র |
| `/admission` | ভর্তি তথ্য | `/prayer` | নামাজের সময় |
| `/notices` | নোটিশ বোর্ড | `/hadith` | হাদীস সংগ্রহ |
| `/events` | ইভেন্ট | `/quran` | পবিত্র কুরআন |
| `/gallery` | গ্যালারি | `/feePayment` | ফি পেমেন্ট |
| `/donation` | দান ও অনুদান | `/admissionTrack` | ভর্তি ট্র্যাকিং |
| `/blog` | লেখা ও প্রবন্ধ | `/library` | লাইব্রেরি |
| `/contact` | যোগাযোগ | `/attendance` | উপস্থিতি |
| `/results` | পরীক্ষার ফলাফল | `/hostel` | হোস্টেল |
| `/classRoutine` | ক্লাস রুটিন | `/dawah` | দাওয়াত ও তাবলিগ |
| `/syllabus` | সিলেবাস | `/materials` | পড়াশোনার উপকরণ |
| `/student` | শিক্ষার্থী পোর্টাল | — | — |

---

## 🔌 API রাউট

### ডেভেলপমেন্ট (Next.js API Routes)
`src/app/api/` ফোল্ডারে থাকে, শুধু `npm run dev` এ কাজ করে:

| মেথড | এন্ডপয়েন্ট | বিবরণ |
|--------|-------------|--------|
| POST | `/api/bohudur/check` | Bohudur API Key যাচাই |
| POST | `/api/bohudur/create` | পেমেন্ট তৈরি (proxy) |
| POST | `/api/bohudur/execute` | পেমেন্ট এক্সিকিউট (proxy) |
| POST | `/api/bohudur/query` | পেমেন্ট স্ট্যাটাস কোয়েরি (proxy) |
| POST | `/api/payment/webhook` | পেমেন্ট webhook (dev mode, log only) |
| GET | `/api/payment/status` | পেমেন্ট স্ট্যাটাস চেক |

### প্রোডাকশন (Cloudflare Pages Functions)
`functions/api/` ফোল্ডারে থাকে, Cloudflare Pages-এ ডিপ্লয় হয়:

| মেথড | এন্ডপয়েন্ট | বিবরণ | Environment Variables |
|--------|-------------|--------|----------------------|
| POST | `/api/bohudur/check` | API Key যাচাই | `BOHUDUR_API_KEY` |
| POST | `/api/bohudur/create` | পেমেন্ট তৈরি | `BOHUDUR_API_KEY` |
| POST | `/api/bohudur/execute` | পেমেন্ট এক্সিকিউট | `BOHUDUR_API_KEY` |
| POST | `/api/bohudur/query` | পেমেন্ট স্ট্যাটাস | `BOHUDUR_API_KEY` |
| POST | `/api/payment/webhook` | **Bohudur webhook → RTDB update** | `FIREBASE_DATABASE_URL`, `FIREBASE_DB_SECRET` |
| GET | `/api/payment/status` | পেমেন্ট স্ট্যাটাস (Bohudur proxy) | `BOHUDUR_API_KEY` |

> **গুরুত্বপূর্ণ**: প্রোডাকশনে webhook ফাংশন `FIREBASE_DB_SECRET` ব্যবহার করে Firebase RTDB আপডেট করে। এটি ছাড়া দানের অর্থ RTDB-তে আপডেট হবে না।

---

## 💳 পেমেন্ট সিস্টেম

### পেমেন্ট ফ্লো

```
ইউজার দান ফর্ম পূরণ →
Next.js (bohudur/create) →
Bohudur Payment Gateway →
ইউজার পেমেন্ট সম্পন্ন →
Bohudur Webhook →
Cloudflare Function (payment/webhook) →
Firebase RTDB (payments/ আপডেট + donations/ increment)
```

### পেমেন্ট স্ট্যাটাস

| স্ট্যাটাস | বিবরণ |
|-----------|--------|
| `pending` | পেমেন্ট তৈরি হয়েছে, অপেক্ষমান |
| `success` | পেমেন্ট সফল (webhook দ্বারা RTDB আপডেট) |
| `cancel` | ইউজার পেমেন্ট বাতিল করেছে |
| `failed` | পেমেন্ট ব্যর্থ |

### Webhook কনফিগারেশন

Bohudur Dashboard → Webhook Settings:
- **Success URL**: `https://your-domain.com/api/payment/webhook`
- **Cancel URL**: `https://your-domain.com/api/payment/webhook`

---

## 🌍 আন্তর্জাতিকীকরণ (i18n)

প্রজেক্ট তিনটি ভাষা সাপোর্ট করে:

| ভাষা | কোড | দিক | ফন্ট |
|------|------|------|------|
| বাংলা | `bn` | LTR | Noto Sans Bengali |
| English | `en` | LTR | System font |
| العربية | `ar` | **RTL** | Noto Sans Arabic |

- ৫০০+ অনুবাদ কী রয়েছে
- অনুবাদ ফাইল: `src/lib/i18n.ts`
- ডিফল্ট ভাষা: বাংলা (`bn`)
- হেডারে ভাষা সুইচার আছে
- RTL সাপোর্ট: আরবি ভাষায় layout স্বয়ংক্রিয়ভাবে RTL হয়

---

## 📦 প্রোডাকশন ডিপ্লয়মেন্ট

### বিল্ড কমান্ড

```bash
npm run build
```

বিল্ড প্রসেস:
1. `src/app/api/` → `.api_backup/` (temporarily moved)
2. `next build --webpack` → `out/` (static export)
3. `.api_backup/` → `src/app/api/` (restored)

### Cloudflare Pages সেটিংস

| সেটিং | ভ্যালু |
|--------|--------|
| Build command | `npm run build` |
| Build output directory | `out` |
| Root directory | `/` |
| Node.js version | `20` |
| Framework preset | None |

### SPA রাউটিং

`public/_redirects` ফাইলটি Cloudflare Pages-এ SPA রাউটিং নিশ্চিত করে:
```
/*  /index.html  200
```

### ক্যাশিং

`public/_headers` ফাইলটি:
- Static assets (`/_next/static/*`): ১ বছর immutable cache
- ইমেজ: ১ দিন cache
- HTML: no-cache (must-revalidate)
- Security headers: X-Frame-Options, X-Content-Type-Options, ইত্যাদি

---

## 📄 লাইসেন্স

Private Project — জামিয়া ইসলামিয়া দারুল উলূম।
