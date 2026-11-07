# Haraka Loans — Render deployment

This project recreates a Haraka Loans-style black-and-gold application site with a customer form and a password-protected admin dashboard.

## Included
- Swahili customer loan application form
- Application reference number after submission
- PostgreSQL storage
- Admin login and application review/status controls
- Mobile-friendly black-and-gold layout

## Important safety notes
- This is an independent loan application portal, not an official HaloPesa website or endorsement.
- The form deliberately does **not** collect OTPs, SIM PINs, banking PINs, passwords, or verification codes.
- An application is not a loan approval. Publish your real lender identity, terms, fees, privacy notice, and contact details before accepting real applications.
- Do not put real secrets in source code or commit them to GitHub.

## Deploy on Render
1. Create a PostgreSQL database in Render.
2. Create a new **Web Service** and connect the GitHub repository containing these files.
3. Runtime: Node. Build command: `npm install`. Start command: `npm start`.
4. In the web service's **Environment** settings add:
   - `DATABASE_URL`: the PostgreSQL **Internal Database URL** from your Render database (if the database and service are in the same region).
   - `ADMIN_PASSWORD`: a long, unique password for the admin dashboard.
   - `SESSION_SECRET`: a long random secret (at least 32 random characters).
   - `NODE_ENV`: `production`
5. Deploy. Render will provide your public `https://....onrender.com` address.
6. Open that address and use the **Admin** section to sign in.

## Existing GitHub repository
If your repository is named `Haraka-loans`, upload/replace its files with the contents of this project while keeping the folder structure (`public/index.html` must remain inside `public`).

## Database persistence
Applications are stored in PostgreSQL, not in browser storage or a temporary local file. Keep the Render database active and backed up.
