BIG EATER CHALLENGE: FIREBASE-CONNECTED TWO PORTALS

Firebase config has ALREADY been added to both website pages.

ONE REQUIRED STEP BEFORE DEPLOY:
Open admin/index.html using a text editor and find:
  const ADMIN_LOGIN_EMAIL = "REPLACE_WITH_ADMIN_EMAIL@example.com";
Replace that quoted string with the EXACT email you created in Firebase Authentication > Users.
Do NOT put a password in this file. Admin UI is password-only.

FIRESTORE RULES:
You already published Firestore rules. The rules must grant public READ access to
/participants/{participantId}, and UID-specific admin WRITE access there.
/participantPrivate/{participantId} must be admin READ/WRITE only.
This archive also includes firestore.rules as a more restrictive optional version.
If using that file, replace REPLACE_WITH_ADMIN_UID with your own Authentication UID
and Publish the rules in Firebase Console > Firestore Database > Rules.
Do NOT publish rules containing placeholder UID.

DEPLOY TO VERCEL:
Push index.html AND the entire admin/ folder to your existing static site's
repository, keeping folder structure. Vercel should serve / and /admin/.
If your site is built from a framework or has a custom build, deployment may differ.

TEST:
1. Public URL / should load without logging in.
2. Admin URL /admin/ should show a password-only login.
3. After logging in, create a test participant and adjust bowl count.
4. Verify another device sees live updates.
5. Verify public visitors cannot see phone numbers or modify data.

SECURITY:
Firebase config is public client configuration, NOT an admin password.
Do NOT share the admin password. Login account email is visible in HTML source.
Use a unique strong password and avoid reusing the administrator account elsewhere.
Legacy browser localStorage participant records are NOT migrated automatically.
