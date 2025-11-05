---
layout: essay
type: essay
title: "Final Project Proposal: Mānoa Resource Compass"
date: 2025-11-04
labels:
  - Software Engineering
  - Nextjs
---

# Final Project Proposal: Mānoa Resource Compass  
*A Personalized Lifeline for UH Mānoa Students in Need*

---

## Overview

### The Problem  
In 2025, over **40% of UH Mānoa students** face **basic needs insecurity** — food, housing, transportation, hygiene, technology, or childcare — according to the latest UH System survey. These struggles aren’t just statistics: they translate to **lower GPAs, missed classes, and higher dropout rates**.  

Yet, the resources *do* exist:  
- Free food pantries  
- Emergency housing funds  
- Discounted bus passes  
- Laptop loaners  
- Diaper banks  

But they’re scattered across websites, flyers, and word-of-mouth. Students don’t know **what’s available**, **if they qualify**, or **when it expires**. There’s **no personalization**, **no tracking**, and **no proactive help**. For a commuter relying on TheBus or a parent juggling classes and childcare, missing one resource can mean skipping a meal — or a semester.

### The Solution  
**Mānoa Resource Compass** is a **solo-developed, full-stack web app** that transforms how UH Mānoa students access support. Built with **Next.js 15**, **React**, **Bootstrap 5**, and hosted on **GitHub Pages**, it delivers a **personalized, adaptive experience** powered by a **"special sauce"**:  

> **Every logged-in user has a dynamic Needs Profile that evolves with their input and behavior — unlocking tailored recommendations, proactive alerts, and gamified progress tracking.**

After a 2-minute assessment, the app knows:  
- You’re vegetarian and live in Hale Noelani  
- You commute via TheBus and need parking  
- You have a toddler and need diapers monthly  

It then **curates, prioritizes, and reminds** — turning passive resource lists into an **active support system**.

---

## Name of the Proposer  
- **Brandon Nguyen** (Solo Developer & Scribe)  

---

## Mockup Page Ideas

| Page | Key Features |
|------|--------------|
| **1. Landing Page** | Hero with UH campus photo, tagline: *"Support that finds you."* CTA buttons: “Take Assessment” (guest) + “Login” |
| **2. Registration & Assessment** | UH `.edu` email signup → 5-step wizard: sliders (insecurity level), checkboxes (diet, housing, transport), instant profile save |
| **3. Personal Dashboard** | Progress rings (“Food: 80%”), **Smart Feed** (top 5 matches), streak counter, notification bell |
| **4. Resource Explorer** | Filterable cards + **Leaflet.js map** showing pantries, laundry, bike repair — auto-filtered by profile |
| **5. Claim History** | Timeline: *Claimed → Confirmed → Picked Up*. Export PDF for aid appeals |
| **6. Community Board** | Anonymous threads: “Free Stuff Today”, “Carpool to Kaimuki” — replies matched by shared needs |
| **7. Admin Panel (Hidden)** | Staff-only route to add/edit resources (future-ready) |

---

## Use Case Ideas

1. **Freshman in Crisis**  
   *Jane* (dorm resident, vegetarian, high food insecurity) logs in → sees:  
   - “Pantry slot: Tomorrow 4–6 PM” (book now)  
   - “Free ramen + tofu at Campus Center”  
   - “Join Vegan Warriors group chat”  
   → Claims 2 items → earns **“First Step” badge**

2. **Commuter on a Budget**  
   *Alex* (no car, tight schedule) gets:  
   - Pre-filled HART student pass form  
   - Carpool match with 3 nearby students  
   - Alert: “Free bike tune-up Saturday at Sinclair”

3. **Parent-Student Survival**  
   *Mia* (toddler, needs diapers + laundry) receives:  
   - Diaper bank pickup (map + hours)  
   - Laundry voucher code (texted)  
   - Children’s Center waitlist tracker

4. **Smart Prediction**  
   App sees *you claim food 3x in last week of month* → sends:  
   > “Pantry restocks Monday — stock up now!”  
   > “$50 emergency food voucher available”

5. **User Testing (Guaranteed Access)**  
   I’ll demo in **ICS 314**, **Warrior Rec Center**, and via **QR codes in dorm lobbies** → collect 50+ real student surveys

---

## Beyond the Basics

### Tech Stack Mastery  
- **Next.js 15 (App Router)**: SSR for SEO, API routes for logic  
- **React 19 + Hooks**: Real-time updates, optimistic UI  
- **Bootstrap 5**: Mobile-first, accessible (WCAG 2.1)  
- **GitHub Pages + Actions**: Free, auto-deploy on push  

### Special Sauce: Adaptive User State  
```ts
// Example: Rule-based engine (Next.js API route)
if (profile.foodInsecurity > 7 && profile.diet === 'vegetarian') {
  recommend('UH Food Vault - Vegan Night');
}
