<a name="readme-top"></a>

Lingo - A Language Learning Platform
Table of Contents
<details> <summary>Expand</summary>
Folder Structure
</details>
Folder Structure
Below is the project's folder organization:

~~~bash
Copy code
lingo/  
  |- actions/  
    |- challenge-progress.ts  
    |- user-progress.ts  
    |- user-subscription.ts  
  |- app/  
    |-- (main)/  
        |--- courses/  
        |--- leaderboard/  
        |--- learn/  
        |--- quests/  
        |--- shop/  
        |--- layout.tsx  
    |-- (marketing)/  
        |--- footer.tsx  
        |--- header.tsx  
        |--- layout.tsx  
        |--- page.tsx  
    |-- admin/  
        |--- challenge/  
        |--- challengeOption/  
        |--- course/  
        |--- lesson/  
        |--- unit/  
        |--- app.tsx  
        |--- page.tsx  
    |-- api/  
        |--- challengeOptions/  
        |--- challenges/  
        |--- courses/  
        |--- lessons/  
        |--- units/  
        |--- webhooks/stripe/  
    |-- lesson/  
        |--- [lessonId]/  
        |--- card.tsx  
        |--- challenge.tsx  
        |--- footer.tsx  
        |--- header.tsx  
        |--- layout.tsx  
        |--- page.tsx  
        |--- question-bubble.tsx  
        |--- quiz.tsx  
        |--- result-card.tsx  
    |-- apple-icon.png  
    |-- favicon.ico  
    |-- globals.css  
    |-- icon1.png  
    |-- icon2.png  
    |-- layout.tsx  
  |- components/  
    |-- modals/  
    |-- ui/  
    |-- feed-wrapper.tsx  
    |-- mobile-wrapper.tsx  
    |-- mobile-sidebar.tsx  
    |-- promo.tsx  
    |-- quests.tsx  
    |-- sidebar-item.tsx  
    |-- sidebar.tsx  
    |-- sticky-wrapper.tsx  
    |-- user-progress.tsx  
  |- config/  
    |-- index.ts  
  |- db/  
    |-- drizzle.ts  
    |-- queries.ts  
    |-- schema.ts  
  |- lib/  
    |-- admin.ts  
    |-- stripe.ts  
    |-- utils.ts  
  |- public/  
  |- scripts/  
    |-- prod.ts  
    |-- reset.ts  
    |-- seed.ts  
  |- store/  
    |-- use-exit-modal.ts  
    |-- use-hearts-modal.ts  
    |-- use-practice-modal.ts  
  |- types/  
    |-- canvas.ts  
  |- .env  
  |- .env.example  
  |- .eslintrc.js  
  |- .gitignore  
  |- .prettierrc.json  
  |- components.json  
  |- constants.ts  
  |- drizzle.config.ts  
  |- environment.d.ts  
  |- middleware.ts  
  |- next.config.mjs  
  |- package-lock.json  
  |- package.json  
  |- postcss.config.js  
  |- tailwind.config.ts  
  |- tsconfig.json
~~~
Getting Started
Prerequisites:
Ensure Git and Node.js are installed on your machine.
Clone this repository to your local system.
Create an .env file in the project root directory with the following content:
plaintext
Copy code
# Disable Next.js telemetry  
NEXT_TELEMETRY_DISABLED=1  

# Clerk authentication keys  
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX  
CLERK_SECRET_KEY=sk_test_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX  

# Neon database URI  
DATABASE_URL="postgresql://<user>:<password>@<host>:<post>/lingo?sslmode=require"  

# Stripe API key and webhook secret  
STRIPE_API_SECRET_KEY=sk_test_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX  
STRIPE_WEBHOOK_SECRET=whsec_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX  

# Public app URL  
NEXT_PUBLIC_APP_URL=http://localhost:3000  

# Clerk admin user IDs (comma-separated for multiple admins)  
CLERK_ADMIN_IDS="user_xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"  
# Example for multiple admins: "user_xxxxxxxxxxxxxxxxxxxxxxxxxxxxx, user_xxxxxxxxxxxxxxxxxxxxxx"  
Configuration Steps
1. Obtain Clerk Authentication Keys:
Source: Clerk Dashboard
Steps:
Log in to your Clerk account.
Navigate to the dashboard or settings.
Locate the authentication keys section and copy the NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY and CLERK_SECRET_KEY.
2. Retrieve Neon Database URI:
Source: Neon Database Dashboard
Steps:
Access your Neon account and navigate to the connection details.
Replace <user>, <password>, <host>, and <port> in the URI with your credentials.
3. Fetch Stripe API Keys:
Source: Stripe Dashboard
Steps:
Log in to Stripe and locate the API settings.
Copy the STRIPE_API_SECRET_KEY and STRIPE_WEBHOOK_SECRET.
4. Update Public App URL:
Replace http://localhost:3000 with the deployed app’s URL.
5. Set Clerk Admin IDs:
Retrieve admin user IDs from the Clerk dashboard and add them to CLERK_ADMIN_IDS.
Installation and Setup
Install project dependencies:

bash
Copy code
npm install --legacy-peer-deps  
Seed the database:

bash
Copy code
npm run db:push && npm run db:prod  
Start the development server:

bash
Copy code
npm run dev  
Verification
Verify the database is seeded with challenges.
Test authentication and API integrations.
NOTE: Keep all sensitive information (e.g., API keys and .env content) secure and do not expose it publicly.
