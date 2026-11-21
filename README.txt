BIG EATER TWO-PORTAL WEBSITE

Public: / (index.html)
Staff: /admin/ (admin/index.html)

SETUP
1. Firebase Console > Create Project > Register Web App.
2. Firestore Database > Create Database (production mode).
3. Authentication > Sign-in method > Email/Password Enable.
4. Authentication > Users > Add user with your chosen admin email and strong password. Copy UID.
5. Set identical firebaseConfig values in BOTH index.html and admin/index.html.
   In admin/index.html, set ADMIN_LOGIN_EMAIL to the admin email created in step 4.
   This email will be used internally. Staff only see a password field.
6. In firestore.rules replace REPLACE_WITH_ADMIN_UID with the UID of your admin user.
7. Firestore Database > Rules > paste rules > Publish.
8. Upload this folder contents to your Vercel static-site repo, commit, deploy.
9. Visit /admin/ to log in; visit / to check live leaderboard.

SECURITY
Do not share admin password. Firebase web app config is not a secret.
Never store phone numbers in public participants collection.
The public page does not load firebase-auth or admin functionality.
The admin page requires Authentication, and Security Rules enforce writes.

NOTE
Data in previous localStorage is not migrated automatically.
The site has placeholders until YOUR firebaseConfig and UID are supplied.

PASSWORD CHANGES
Change the admin account password in Firebase Authentication. Never hardcode the password into HTML or JavaScript.
