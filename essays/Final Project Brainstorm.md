---
layout: essay
type: essay
title: "Final Project Brainstorm"
date: 2025-11-04
labels:
  - Software Engineering
  - Nextjs
---

# Mānoa Resource Compass: A Personalized Basic Needs Navigator

## Overview

### The Problem  
A 2025 UH System survey found that over 40% of UH Mānoa students experience some form of basic needs insecurity — including food, housing, transportation, healthcare, hygiene, technology, or childcare — with off-campus and commuter students disproportionately affected. These challenges correlate with lower GPA, reduced course completion, and higher dropout risk. Despite existing support (e.g., food pantries, emergency aid funds, bus pass subsidies), students report major barriers: **fragmented information**, **lack of personalization**, **no tracking of claims**, and **no proactive alerts**. Many never discover time-sensitive aid, and there’s no unified platform tailored to their evolving needs.

### The Solution  
**Mānoa Resource Compass** is a solo-developed, full-stack web application that empowers UH Mānoa students to discover, claim, and manage basic needs resources through a **personalized, adaptive dashboard**. Built with **Next.js 15**, **React**, **Bootstrap 5**, and hosted on **GitHub Pages**, the app features a **"special sauce"**: after login, each user builds a dynamic *Needs Profile* via an interactive assessment. This profile drives a **smart recommendation engine** (rule-based with lightweight predictive logic) that surfaces hyper-relevant resources, tracks usage history, sends proactive notifications (e.g., “Free laundry detergent tomorrow at Campus Center!”), and gamifies engagement with streaks and achievement badges. The app integrates local Honolulu resources and fosters anonymous peer support — all optimized for mobile use on spotty campus WiFi.

---

## Name of the Proposer  
- **Brandon Nguyen** (Solo Developer & Scribe)

---

## Mockup Page Ideas

1. **Landing Page (Public)**  
   - Hero: UH Mānoa campus backdrop with tagline: *"Never miss the support you need — personalized for you."*  
   - CTA: “Take the 2-Min Needs Assessment” (guest mode) + “Login / Register”  
   - Stats carousel: “1,200+ resources claimed this semester” | “92% found aid faster”

2. **Registration & Login**  
   - UH email-only signup (`.edu` validation)  
   - Post-login: Guided **Needs Assessment Wizard** (5 steps: sliders for insecurity levels, checkboxes for dietary/housing/transport needs)

3. **Personal Dashboard (Core Experience)**  
   - **Profile Card**: Visual progress rings (e.g., “Food: 80% met”, “Housing: 45%”)  
   - **Smart Feed**: Top 5 prioritized recommendations with “Claim Now” buttons  
   - **Streak Tracker**: “7-day resource streak!” + badge unlock  
   - **Notification Center**: Toast alerts for expiring aid or new matches

4. **Resource Explorer**  
   - Filterable list + **interactive map** (Leaflet.js) showing food pantries, laundry, bike repair, etc.  
   - Filters auto-applied from user profile (e.g., “Vegetarian”, “Walking distance”)

5. **Claim History & Tracker**  
   - Timeline of claimed items with status: *Pending → Confirmed → Picked Up*  
   - Exportable PDF summary for financial aid appeals

6. **Anonymous Community Board**  
   - Threaded forum: “Transportation Tips”, “Free Stuff Alerts”  
   - Posts auto-anonymized; replies matched by shared needs (e.g., “I’m a commuter too — try this route”)

7. **Admin Tools (Future-Proof)**  
   - Hidden route for UH staff to add/edit resources (protected by role-based auth)

---

## Use Case Ideas

1. **First-Time User: Food Insecurity**  
   Brandon (a freshman) registers, completes the assessment: *high food insecurity, vegetarian, lives in dorms*.  
   → Dashboard shows:  
   - “Book pantry slot: Tomorrow 3–5 PM” (instant calendar add)  
   - “Free meal swipe at Hale Aloha Café”  
   - “Join Vegetarian Student Group for weekly shares”  
   He claims 2 items → earns “First Step” badge.

2. **Commuter Student: Transportation**  
   A user selects: *no car, relies on TheBus, tight schedule*.  
   → App recommends:  
   - Discounted monthly pass application (pre-filled form)  
   - Carpool group with 3 nearby students  
   - Bike repair pop-up at Sinclair Circle  
   → Push notification: “Bus pass expires in 3 days!”

3. **Parent-Student: Childcare & Hygiene**  
   Profile: *has toddler, needs diapers, laundry access*.  
   → Matches with:  
   - Campus Children’s Center waitlist tool  
   - Free diaper bank pickup (map + directions)  
   - Dorm laundry voucher (claim code sent via email)

4. **End-of-Month Crunch Prediction**  
   App detects pattern: user claims food 3x in last week of month.  
   → Auto-suggests: “Stock up now — pantry restocks Monday” + “Emergency $50 food voucher available”

5. **User Evaluation (Guaranteed Access)**  
   Brandon demos the app in ICS 314 class, at Warrior Recreation Center, and via QR codes in dorm lobbies. Collects 50+ feedback surveys from real UH Mānoa students.

---

## Beyond the Basics

- **Tech Stack Mastery**  
  - **Next.js 15 (App Router)**: SSR for SEO, SSG for static pages, API routes for recommendation engine  
  - **React 19 + Hooks**: Real-time profile sync, optimistic UI updates  
  - **Bootstrap 5 + Custom CSS**: Fully responsive, accessible (ARIA, color contrast), mobile PWA-ready  
  - **GitHub Pages + Actions**: Free hosting, CI/CD, automatic builds on push  

- **Special Sauce: Adaptive User State**  
  - **Persistent Profile**: Stored in **Supabase** (free tier: auth + PostgreSQL)  
  - **Smart Matching Engine**: Combines rule-based logic (`if food_insecurity > 7 → show pantry`) with usage patterns  
  - **Predictive Alerts**: Cron-like API route checks claim history → triggers email (via Resend)  
  - **Gamification**: Badges, streaks, and “Needs Met” score encourage return visits  

- **UH Mānoa & Local Focus**  
  - Curated from official sources: [hawaii.edu/student-basic-needs](https://hawaii.edu/student-basic-needs), UH Food Vault, HART student discounts  
  - Honolulu integration: Hawaii Foodbank, Lanakila Multipurpose Center, Angel Network Charities  
  - Hawaiian/Tagalog language toggle (i18n with next-intl)

- **Evaluation & Impact**  
  - **A/B Testing**: Half of users get generic list, half get smart feed → measure claim rate  
  - **Analytics**: Track resource popularity, peak claim times → share with UH Basic Needs Committee  
  - **Open Source**: GitHub repo public — future ICS classes can extend (e.g., add mental health module)

- **Solo Feasibility**  
  - Scoped MVP: 6 core pages, 1 recommendation engine, Supabase backend  
  - Reusable components, Figma mockups in advance, weekly milestones  
  - Leverage existing APIs (Leaflet, Resend) to avoid backend bloat

---

**Mānoa Resource Compass** isn’t just a directory — it’s a **proactive, personalized lifeline** for UH Mānoa students facing real barriers. By combining modern web development with deep community insight, this solo project delivers meaningful impact, technical excellence, and a scalable foundation for campus-wide adoption.
