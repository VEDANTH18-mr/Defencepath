
# DefencePath — Your Route to Service 🇮🇳

An eligibility-first defence career guidance platform that helps students explore possible routes into the Indian Armed Forces based on their age, education and interests.

DefencePath supports students from Science, Commerce, Arts, ITI, diploma and graduate backgrounds.

🌐 **Live Website:** https://defencepath.vercel.app

## About the Project

Finding the right defence entry route can be confusing, especially for students who are unsure which opportunities match their educational background.

DefencePath brings pathway guidance, preparation resources, exam planning and service information into one platform. Students create an account, complete a profile questionnaire and explore routes relevant to their circumstances.

## Features

- **Email and password authentication** using Supabase Auth.
- **Profile questionnaire** covering date of birth, education, stream, service interests and other planning details.
- **Personalised pathway suggestions** using transparent, rule-based matching.
- **Defence entry guides** covering school-level, ITI, diploma and graduate routes.
- **Preparation resources** including study topics, exam patterns, reference books and official links.
- **Exam calendar** with route filters and downloadable calendar events.
- **Fitness and medical guidance** with links to entry-specific official requirements.
- **Academy discovery** through city-based Google Maps searches.
- **Service journal** covering service benefits, veteran resources and motivational content.
- **Saved shortlists and checklists** for tracking preparation.
- **Printable and downloadable plans**.
- **Responsive design** for desktop and mobile devices.

## Technology Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, JavaScript |
| Backend | Node.js with Fetch API request handling |
| Authentication | Supabase Auth |
| Hosting | Vercel |
| Progress storage | Browser localStorage, scoped per account |
| Testing | Node.js built-in test runner |
| Version control | Git and GitHub |

The current application does not use React, Express or MongoDB.

## How It Works

1. Create an account and confirm your email if required.
2. Log in to access the dashboard.
3. Complete the student profile questionnaire.
4. Explore suggested defence entry routes.
5. Review preparation resources, selection stages and official notices.
6. Save routes and track your preparation.

The recommendation engine uses programmed rules. It does not use AI or machine learning.

## Project Structure

    defencepath/
    ├── api/
    │   └── site.mjs              # Vercel server adapter
    ├── web/
    │   ├── welcome.html          # Signup and login page
    │   ├── index.html            # Dashboard shell
    │   ├── style.css             # Styling and responsive layouts
    │   ├── account.js            # Authentication form handling
    │   ├── app.js                # Dashboard interactions
    │   ├── engine.js             # Pathway matching rules
    │   └── data.js               # Routes, dates and resources
    ├── worker/
    │   └── handler.js            # Authentication and routing
    ├── scripts/                 # Build and development tools
    ├── tests/                   # Automated checks
    ├── .env.example              # Environment variable template
    ├── package.json
    ├── vercel.json
    ├── AUTH-SETUP.md
    ├── VERCEL-DEPLOYMENT.md
    └── PRODUCT-ROADMAP.md

## Requirements

- Node.js 22.x
- npm
- A Supabase project
- A Vercel account for deployment

The application currently has no third-party npm dependencies.

## Getting Started

Clone your GitHub repository and open its project folder.

For a local preview:

    node scripts/build.mjs
    npm run dev

Open:

    http://localhost:5173

The simple local preview supports viewing the entry screens. It does not fully connect the hosted authentication environment or support authentication POST requests. Use a configured Vercel deployment to test the complete account flow.

## Environment Variables

Configure these variables in Vercel:

    SUPABASE_URL=https://your-project.supabase.co
    SUPABASE_PUBLISHABLE_KEY=your-publishable-key

Use `.env.example` as a reference.

Do not commit runtime credentials or use a Supabase service-role key for this authentication flow.

## Supabase Authentication Setup

1. Create or select a Supabase project.
2. Enable email and password authentication.
3. Add the project URL and publishable key to Vercel.
4. Open Supabase Authentication → URL Configuration.
5. Set the Site URL to your deployed website.
6. Add the allowed email confirmation redirect:

       https://your-domain/?mode=login

For the current deployment:

- **Site URL:** https://defencepath.vercel.app
- **Allowed redirect:** https://defencepath.vercel.app/?mode=login

Test signup, confirmation email delivery, login and logout. Configure custom SMTP when needed for wider email delivery.

## Deploying to Vercel

1. Push the project to GitHub.
2. Import the repository into Vercel.
3. Use the following settings:

| Setting | Value |
|---|---|
| Framework preset | Other |
| Build command | `npm run build:vercel` |
| Output directory | `public` |
| Node.js version | 22.x |

4. Add the Supabase environment variables.
5. Deploy the project.
6. Update Supabase authentication URLs for the deployment domain.

The included `vercel.json` routes requests through the server so protected application files require an authenticated session.

## Running Tests

Build the Vercel application and run the test suite:

    npm run build:vercel
    npm test

To run the Vercel adapter checks separately:

    npm run test:vercel

Tests cover pathway logic, authentication behaviour and protected routes.

## Authentication and Privacy

- Supabase manages account credentials.
- Access tokens are stored in Secure, HttpOnly, SameSite cookies.
- The server verifies the current user before serving protected content.
- Sessions last up to one hour, after which users must log in again.
- Preparation progress is stored in the browser and separated by account.
- Progress does not currently sync between devices.

Users should not enter medical records, government identity documents or other sensitive personal information.

## Current Limitations

- Pathway suggestions are broad planning guidance, not official eligibility certification.
- Exact age windows, marks, subject requirements and other conditions must be checked in the latest recruitment notice.
- Exam dates and reference information are maintained manually.
- Academy discovery opens Google Maps searches; it does not provide a verified academy ranking or distance calculation.
- Password recovery and cross-device progress synchronisation are not implemented.
- Background email alerts and push notifications are not active.

## Future Improvements

- Database-backed student profiles and progress.
- Password recovery.
- More precise intake-specific eligibility rules.
- Updated recruitment notifications and reminders.
- Verified academy listings.
- Verified candidate interviews and mentor contributions.
- Administrative tools for maintaining content.

## Disclaimer

DefencePath is an independent educational guidance project. It is not affiliated with the Indian Armed Forces, UPSC or any recruitment authority.

Always verify eligibility, dates, medical standards, service benefits and application procedures through the relevant official sources.

## Author

**M R Vedanth**

B.Tech Computer Science and Engineering  
Marwadi University

GitHub: https://github.com/VEDANTH18-mr
