# Project Specification

## 1. Background & Problem
**What's the problem?** Fresh graduates struggle to find entry-level jobs that match their qualifications, while employers don't have a focused channel to reach quality graduate talent. Generic job boards mix all experience levels, making it hard for both parties to connect.

**Who has this problem?**
- 2024-2025 fresh graduates entering the Malaysian job market
- HR managers and recruiters looking to hire for junior/entry-level positions

**Current situation:** Graduates spend hours browsing through irrelevant senior-level positions on generic job boards. Employers receive applications from overqualified or underqualified candidates because there's no dedicated graduate hiring funnel.

## 2. Goals & Success Metrics
**Primary Goal:** Create a dedicated landing page that connects fresh graduates with graduate-appropriate job opportunities and drives traffic to Ajobthing's main platform.

**Success looks like:**
- 5,000+ email signups in the first month
- 50+ daily clicks to job posting pages
- 20+ employer referrals to the "Post Jobs" page per week
- 30% click-through rate on featured job cards

## 3. Project Overview
**Project Name:** Ajobthing Graduate Career Launch 2025

**Description:** A campaign landing page promoting Ajobthing's graduate hiring initiative, showcasing featured graduate jobs, and capturing leads from both job seekers and employers.

**Target Users:** Fresh graduates (Class of 2024-2025) and HR managers/recruiters hiring for entry-level positions

## 4. What It Should Do
### Core Features
- [ ] Display campaign benefits for both job seekers and employers
- [ ] Showcase 5-6 featured graduate job listings with company branding
- [ ] Collect email signups for campaign updates and job alerts
- [ ] Show impressive statistics (graduates hired, companies participating, placement rates)
- [ ] Provide clear call-to-action buttons routing to main Ajobthing platform
- [ ] Mobile-responsive design (70% of traffic expected from mobile)

### User Actions
1. User can read about the Graduate Career Launch 2025 campaign
2. User can browse featured graduate job positions with key details
3. User can click "Find Graduate Jobs" → redirects to ajobthing.com/graduate-jobs
4. User can click "Post Graduate Jobs" → redirects to ajobthing.com/employers
5. User can sign up for campaign updates by entering their email
6. When user submits email, system shows success message: "Thanks! We'll keep you updated"
7. User can click on individual job cards to view full job details on main site
8. User can access social media links in footer

## 5. How It Should Look
**Visual Style:** Modern, energetic, and inspiring for young professionals. Clean layout with plenty of white space, bold typography, and aspirational imagery.

**Colors:**
- Primary: Ajobthing blue (#0066FF or similar brand color)
- Accent: Bright orange (#FF6B35) for CTAs and highlights
- Background: White (#FFFFFF) with light blue (#F0F7FF) sections for contrast
- Text: Dark gray (#333333) for body, white for hero text

**Layout:**
- Fixed/sticky navigation bar with logo and CTA button
- Full-width hero section with centered text and dual CTAs
- Alternating white/light blue background sections
- Grid layout for statistics (4 columns desktop, 2 columns mobile)
- Card grid for featured jobs (3 columns desktop, 1 column mobile)
- Centered email signup form with visual emphasis
- Simple footer with link columns

### Key Pages/Sections

**Hero Section:**
- Headline: "Launch Your Career in 2025"
- Subheading: "Join 10,000+ graduates who found their dream job with Malaysia's top employers"
- Background: Gradient overlay on image of diverse young professionals
- Two prominent buttons:
  - "Find Graduate Jobs →" (primary/orange)
  - "I'm Hiring Graduates" (secondary/outline)

**Statistics Section:**
- Background: Light blue
- 4 key numbers displayed prominently:
  - "10,000+ Graduates Hired"
  - "500+ Top Companies"
  - "95% Placement Rate"
  - "RM 2,500+ Average Starting Salary"
- Each with icon above number

**Why Join Section:**
- Headline: "Why Graduates Choose Ajobthing"
- 4 benefit cards with icons:
  - ✓ Access 500+ graduate-friendly companies
  - ✓ Personalized job recommendations
  - ✓ Career resources & interview tips
  - ✓ Free CV review for fresh graduates

**Featured Jobs Section:**
- Headline: "Hot Graduate Opportunities"
- Subheading: "Start your career with these amazing companies"
- 6 job cards in grid layout, each showing:
  - Company logo
  - Job title
  - Location (city)
  - Salary range
  - "View Job →" link
- Each card is clickable and links to actual job posting

**Email Signup Section:**
- Background: Gradient blue
- Headline: "Get Graduate Job Alerts Weekly"
- Subheading: "Be the first to know about new opportunities"
- Email input field (placeholder: "Enter your email")
- "Subscribe Now" button
- Small privacy text: "No spam, just opportunities. Unsubscribe anytime."

**Footer:**
- Logo on left
- Three columns:
  - About (About Us, How It Works, Contact)
  - For Job Seekers (Find Jobs, CV Tips, Career Guide)
  - For Employers (Post Jobs, Pricing, Success Stories)
- Social media icons (LinkedIn, Facebook, Instagram)
- Bottom bar: "© 2025 Ajobthing. All rights reserved."

## 6. Technical Details
**Framework:** React with Vite (or Next.js for better SEO)

**Deployment:** Vercel (for easy deployment and preview URLs)

**Data Storage:**
- Featured jobs: Hardcoded in the page as JSON data or imported from separate data file
- Email signups: Formspree (free tier) or Netlify Forms integration
- No backend database required

**Responsive:** Mobile-first approach. Breakpoints at 640px (mobile), 768px (tablet), 1024px (desktop)

**Key Libraries:**
- React
- Tailwind CSS (for styling)
- React Hook Form (for email validation)
- Lucide React or Heroicons (for icons)

**Performance:**
- Images optimized and lazy-loaded
- Target load time under 2 seconds
- Lighthouse score > 90

## 7. Example Scenarios

**Scenario 1 - Graduate Job Seeker:**
- Sarah, a recent marketing graduate, clicks on Facebook ad
- Lands on hero section, reads "Launch Your Career in 2025"
- Scrolls down to see statistics (feels encouraged by 95% placement rate)
- Browses featured jobs section
- Clicks on "Marketing Executive at Shopee" job card
- Gets redirected to full job posting on ajobthing.com/jobs/12345
- Applies for the job on main platform

**Scenario 2 - HR Manager/Employer:**
- David, an HR manager, receives email about graduate hiring campaign
- Opens landing page from email link
- Reads campaign benefits and sees statistics about graduate talent pool
- Clicks "I'm Hiring Graduates" button in hero
- Gets redirected to ajobthing.com/employers/post-job
- Signs up and posts a Management Trainee position

**Scenario 3 - Email Signup:**
- Alex, a fresh graduate, explores the page
- Interested but not ready to apply yet
- Scrolls to email signup section
- Enters email "alex.tan@example.com"
- Clicks "Subscribe Now"
- Form validates email format
- Shows green checkmark and message: "Thanks! Watch your inbox for graduate opportunities"
- Email is captured in Formspree dashboard
- Alex receives welcome email (automated by Formspree)

**Scenario 4 - Mobile User:**
- Lisa accesses page on mobile phone during commute
- Hero section displays with stacked buttons (full width)
- Statistics show in 2-column grid instead of 4
- Featured jobs display as single column cards
- Email form is thumb-friendly with large input and button
- All interactions work smoothly on touch screen

## 8. Content & Copy

**Key Headlines:**
- Hero: "Launch Your Career in 2025"
- Hero Sub: "Join 10,000+ graduates who found their dream job with Malaysia's top employers"
- Featured Jobs: "Hot Graduate Opportunities"
- Email Section: "Get Graduate Job Alerts Weekly"

**Call-to-Action Buttons:**
- Primary CTA: "Find Graduate Jobs →"
- Secondary CTA: "I'm Hiring Graduates"
- Job Cards: "View Job →"
- Email Form: "Subscribe Now"

**Statistics:**
- "10,000+ Graduates Hired"
- "500+ Top Companies"
- "95% Placement Rate"
- "RM 2,500+ Average Starting Salary"

**Benefits (Why Join):**
- ✓ Access 500+ graduate-friendly companies
- ✓ Personalized job recommendations
- ✓ Career resources & interview tips
- ✓ Free CV review for fresh graduates

**Sample Featured Jobs (Placeholder):**
1. Management Trainee Program - Maybank | KL | RM 3,000-3,500
2. Software Engineer Graduate - Grab | Cyberjaya | RM 4,000-5,000
3. Marketing Executive - Shopee | PJ | RM 2,800-3,200
4. Data Analyst - AirAsia | Sepang | RM 3,200-3,800
5. HR Executive - Petronas | KL | RM 3,000-3,500
6. Sales Executive - Maxis | Multiple Locations | RM 2,500-3,000

**Privacy/Legal:**
- Email form: "No spam, just opportunities. Unsubscribe anytime."
- Footer: "© 2025 Ajobthing. All rights reserved."

## 9. Out of Scope (Not Included)
- No user login/authentication system (redirects to main site for that)
- No actual job posting creation on landing page (links to main Ajobthing platform)
- No payment processing or subscription features
- No live chat or messaging system
- No job application functionality (handled on main site)
- No admin dashboard or CMS (static campaign page with hardcoded content)
- No job search or filtering (just featured listings)
- No user profiles or saved jobs
- No multi-language support (English only for MVP)
- No A/B testing or analytics dashboard (use Google Analytics externally)
