# SkillBridge

---

SkillBridge – A Peer-to-Peer Skill Exchange Platform for Students

SkillBridge is a Next.js web platform that enables students to offer, request, and exchange skills with one another in an interactive and collaborative environment.
The platform integrates Firebase for authentication and database management, and SendGrid for OTP-based email verification.
It also includes an admin dashboard to monitor activity, manage users, and view analytics.

Live Demo: https://skbridgesrm.vercel.app/

🚀 Features

User Features:

Email Login (SRM Constraint) – Only users with @srmist.edu.in email can register.

Google Authentication – Quick login via Google account.

OTP Verification – Email-based OTP validation using SendGrid.

Offer Skills – Post details of skills you can teach or share.

Request Skills – Request help or guidance from peers.

Messaging System – Connect and chat with other users.

Profile Section – View and edit user details and activity.

Admin Features:

Admin Dashboard – Dedicated access for admins.

User Management – View and remove users.

Post Management – Review and delete inappropriate skill posts.

Analytics Overview – View basic platform usage insights.

🧰 Tech Stack

Frontend: Next.js
Backend: Firebase
Database: Cloud Firestore
Authentication: Firebase Auth (Email/Password + Google)
Email Service: SendGrid
Hosting: Vercel

⚙️ Setup Instructions

Clone the Repository
git clone https://github.com/ayerna/SkillBridge.git

cd SkillBridge

Install Dependencies
npm install

Configure Firebase

Go to Firebase Console

Create a new Firebase project

Enable Authentication (Email/Password and Google)

Create a Cloud Firestore database

Add a Web App to get your Firebase config credentials

Add these to a .env.local file:

NEXT_PUBLIC_FIREBASE_API_KEY=your_api_key
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_auth_domain
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_storage_bucket
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id
NEXT_PUBLIC_FIREBASE_MEASUREMENT_ID=your_measurement_id

Configure SendGrid (for OTP)

Create an account at SendGrid

Generate an API Key

Add to .env.local:

SENDGRID_API_KEY=your_sendgrid_api_key
SENDGRID_SENDER_EMAIL=your_verified_sender_email

Run the Project Locally
npm run dev
Visit http://localhost:3000

🧑‍💼 Admin Access

Admin accounts are configured within Firebase Authentication or Firestore.
Admins can:

View and delete users or posts

Access analytics dashboard

📊 Future Enhancements

Enhanced chat features (real-time updates)

Skill recommendation algorithm

Advanced analytics dashboard

Certificate or review system for completed exchanges

🧑‍💻 Contributors

Team SkillBridge – SRM Institute of Science and Technology

Gladwin Benjamin – Product Owner

Sai Srikar – Scrum Master

Vijval N – Developer

Aditya – Developer

🪪 License

This project is licensed under the MIT License – feel free to use and improve!

💡 “Empowering students to learn, teach, and grow together.”




