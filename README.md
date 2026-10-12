🏨 Resort Booking System
A full-featured resort booking and management system built with Next.js, Firebase, and PayMongo.

✨ Features
Area	What you get
🛏️ Rooms	Add, edit, and delete rooms with pricing
📅 Bookings	Real-time booking with date availability checking
💳 Payments	PayMongo payment links and webhook status updates
📧 Notifications	Automated emails for OTP, booking status, contact, and feedback
🔐 Verification	Email OTP and reCAPTCHA to protect bookings
👤 Admin Dashboard	Manage bookings, rooms, messages, feedback, and settings
📊 Analytics	Revenue tracking and booking statistics
🎨 Branding	Customizable logo, colors, and contact info
💬 Guest Feedback	Contact form and feedback with publish/hide controls
📱 PWA	Installable, with offline support and background sync

🧰 Tech Stack
Layer	Technology
Framework	Next.js 14
Database	Firebase Firestore
Authentication	Firebase Auth
Payments	PayMongo API
Email	Nodemailer (Gmail)
Styling	Tailwind CSS with custom components
PWA	Service Worker with offline caching

🚀 Getting Started
Prerequisites
Node.js 18+ and npm or pnpm
A Firebase project with Firestore enabled
A Gmail account with an App Password for sending email
A PayMongo account
reCAPTCHA site and secret keys

Installation
bash
# 1. Clone the repository
git clone https://github.com/Julyanacsy/resort-booking-system.git
cd resort-booking-system
# 2. Install dependencies
npm install        # or: pnpm install
# 3. Create your environment file (see the next section)
touch .env.local
# 4. Start the dev server
npm run dev        # or: pnpm dev
Then open http://localhost:3000.

🔑 Environment Variables
Create a .env.local file in the project root:
env
# Firebase
NEXT_PUBLIC_FIREBASE_API_KEY=your_api_key
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_auth_domain
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_storage_bucket
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id
# Email (one Gmail handles all automated mail)
EMAIL_USER=your_sender@gmail.com
EMAIL_PASSWORD=your_16_char_app_password   # alias: EMAIL_PASS
ADMIN_EMAIL=admin@example.com
# EMAIL_REPLY_TO=frontdesk@example.com     # optional, defaults to EMAIL_USER
# PayMongo
PAYMONGO_SECRET_KEY=your_paymongo_secret_key
PAYMONGO_PUBLIC_KEY=your_paymongo_public_key
NEXT_PUBLIC_PAYMONGO_PUBLIC_KEY=your_paymongo_public_key
# reCAPTCHA
NEXT_PUBLIC_RECAPTCHA_SITE_KEY=your_recaptcha_site_key
RECAPTCHA_SECRET_KEY=your_recaptcha_secret_key
⚠️ Never commit .env.local. Keep it in .gitignore and add these values as environment variables in your hosting platform instead.
The email account is used for OTP, booking status updates, contact and feedback messages, and super-admin approve/reject notices.

📂 Project Structure
├── app/
│   ├── admin/          # Admin dashboard pages
│   ├── api/            # API routes
│   └── page.jsx        # Landing page
├── components/
│   ├── admin/          # Admin components
│   ├── sections/       # Landing page sections
│   └── ui/             # Reusable UI components
├── hooks/              # Custom React hooks
├── lib/                # Utilities and Firebase config
└── public/             # Static assets

⚙️ How It Works
Booking Flow
Guest selects dates and room type.
System checks availability.
Guest fills out the booking form and passes reCAPTCHA.
A 6-digit OTP is sent to the guest's email.
Guest enters the OTP (auto-submits when complete).
Booking is saved to Firestore.
Admin receives an email notification.
Payment Flow
Admin approves a booking.
A PayMongo payment link is generated for the guest.
PayMongo webhook reports the payment result.
Booking status updates automatically on completion.
Admin Dashboard
Section	Purpose
Overview	Revenue charts and booking statistics
Manage Bookings	Approve, decline, or cancel bookings
Manage Rooms	Add, edit, or delete rooms
Contact Messages	View and manage inquiries
Feedback	Publish or hide guest feedback
Brand Settings	Update branding and contact info
PWA Capabilities
Offline support via service worker
Background sync for form submissions
Offline data caching
Installable on mobile and desktop

☁️ Deployment
Vercel (recommended)
Push your code to GitHub.
Import the project in Vercel.
Add your environment variables.
Deploy.

Other platforms
Any host that supports Next.js will work, such as Netlify, AWS Amplify, Railway, or DigitalOcean App Platform.
After deploying, point your PayMongo webhook to your live API route so payment statuses update correctly.

📄 License

Licensed under the MIT License.

💬 Support

Questions or issues? Email magcuhajulianne@gmail.com or open an issue.
