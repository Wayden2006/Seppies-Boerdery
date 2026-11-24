# Seppies Boerdery — setup guide

This is a mobile-friendly web app starter for four private farm users. It uses Firebase Authentication (email/password) and Cloud Firestore. The app does not create public accounts: the administrator creates the four accounts in Firebase.

## What is included
- Animal register for Boer goats, pigs, chickens and sheep
- Breeding records
- Health, vaccination, deworming and treatment records
- Purchases and sales
- Animal weights
- Expenses
- Deaths and losses
- Feed stock movements
- Shared records for all signed-in farm users

## Cost
Use Firebase's no-cost **Spark** plan. Firebase currently lists email/password Authentication among its no-cost features and a Firestore free quota (including 1 GiB stored data, 20,000 writes/day and 50,000 reads/day). If a quota is exceeded on Spark, the affected service can stop until the quota resets. Do not link a billing account if you want to stay on Spark. Check current terms: https://firebase.google.com/docs/projects/billing/firebase-pricing-plans

## Setup (one-time; requires a Google account)

1. Open https://console.firebase.google.com/ and choose **Create a project**. Name it `seppies-boerdery`.
2. In the project, open **Build → Authentication → Get started**.
3. Under **Sign-in method**, enable **Email/Password**. Do not add public sign-up to this app.
4. Open **Authentication → Users** and click **Add user**. Create the four individual email/password accounts. Keep the passwords private and give each person their own login.
5. Open **Build → Firestore Database → Create database**. Choose production mode and a region close to South Africa if available.
6. In Firestore **Rules**, replace the starter rules with the contents of `firestore.rules` in this folder and publish. These rules require a signed-in account.
7. In Project settings (gear icon) → **General** → **Your apps**, add a Web app (`</>`). Register it and copy the Firebase configuration object.
8. Open `index.html` in a text editor. Replace the six `PASTE_...` values in `firebaseConfig` with the matching values from your Firebase web app config. Keep the quotes.
9. Host the folder using Firebase Hosting on the Spark plan (or another static web host). Firebase Hosting setup instructions: https://firebase.google.com/docs/hosting
10. Open the published web address on each phone. On iPhone, use Share → Add to Home Screen. On Android, use the browser menu → Add to Home screen.

## Important access control
- The included app has no account-registration screen.
- Create only the four intended accounts in Firebase Authentication.
- Firestore rules allow signed-in accounts to access the shared farm records. If you later need role-based permissions (e.g. only the owner can delete), the rules and app should be upgraded together.
- Never share the Firebase administrator password or project-owner access with all users.
- Back up important records periodically. This starter does not yet include export/backup automation.

## Current starter limitations
- Records can be added, listed, searched and deleted. Editing existing records, photo uploads, offline sync, report exports, reminders and detailed financial summaries are not included yet.
- All four accounts can currently delete records. Add role-based rules before using it where deletion must be restricted.
- This is a starter implementation, not a fully audited commercial livestock-management system.
