# poll-app
README / Project Notes
📌 Project Overview

This is a full-stack web application built using:

Frontend: React.js

Backend: Node.js + Express.js

Database: MySQL

Authentication: JWT-based authentication

Deployment: Render

The system allows users to register, login, and interact with the application securely.

🔒 Fairness / Anti-Abuse Mechanisms
1️⃣ One-Time Action Enforcement (Backend Controlled)

The backend strictly enforces that a user can perform a restricted action (like voting) only once.

Before allowing the action:

The server checks the database.

If the user has already performed the action → request is rejected.

This prevents:

Duplicate voting

Frontend manipulation

API abuse

✅ Controlled fully on backend
✅ Cannot be bypassed via frontend hacks

2️⃣ JWT Authentication + Protected Routes

After login, the server generates a JWT token.

Protected routes require a valid token.

Middleware verifies:

Token validity

Token expiration

User identity

If invalid → access denied.

This prevents:

Unauthorized access

Session tampering

API misuse

⚠️ Edge Cases Handled
✅ 1. Duplicate Registration

If user tries to sign up with existing email/username → error shown.

✅ 2. Invalid Login Credentials

Incorrect password → proper error response.

✅ 3. Unauthorized API Access

If token is missing or invalid → request blocked.

✅ 4. Already Performed Restricted Action

User attempting to repeat restricted action → prevented.

✅ 5. Database Error Handling

Try-catch blocks used.

Server does not crash on DB failure.

Proper error messages returned.

🚧 Known Limitations

❌ No rate limiting implemented (can be improved).

❌ No CAPTCHA for bot prevention.

❌ Basic UI design (can be improved for better UX).

❌ No email verification system.

❌ No password reset functionality.
