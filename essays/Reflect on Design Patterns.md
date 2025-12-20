---
layout: essay
type: essay
title: "Design Patterns That Saved Our Team Project"
date: 2025-12-19
published: true
labels:
  - Software Engineering
  - Design Patterns
  - Team Development
  - JavaScript
  - TypeScript
---
# Design Patterns That Saved Our Team Project

## I. Introduction

As a junior developer still early in my software engineering journey, I used to think design patterns were mostly academic—things professors and interviewers talk about, but rarely something you'd actually need in real code. That changed completely during a recent team project.

Our assignment was to build *Study Buddy*, a real-time web app that helps university students create and join study sessions. Users can post details like course, time, location, and how many people they need, while others join instantly and see live updates. We built it with Next.js and TypeScript, adding features like recurring sessions, location filtering, and notifications—all while working in a small team on a tight deadline.

At first, we coded quickly without much structure. But as features piled up, the code started getting messy: duplicated logic, hard-to-fix bugs, and confusion when multiple people worked on the same files. That's when we turned to design patterns—not because we wanted to sound fancy, but because they solved real problems we were facing. The patterns we ended up using made our lives easier and kept the project from falling apart.

## II. Key Design Patterns We Applied

### 1. Observer Pattern (via RxJS)

Real-time updates are essential: when someone joins or leaves a session, everyone needs to see it immediately.

We used RxJS `BehaviorSubject` for each session and created a custom hook `useSession(sessionId)` that components could subscribe to. Changes pushed automatically—no manual refreshes or complex state management. This made the live collaboration feel smooth and prevented a lot of stale data bugs.

### 2. Command Pattern

Users sometimes accidentally clicked “Leave Session” and then asked to be let back in. Undoing that wasn't easy in our real-time setup.

We turned Join and Leave actions into Command objects with `execute()` and `undo()` methods. Now reversing a mistake is just one line of code. It saved us from constant back-and-forth in our team chat.

### 3. Factory Pattern

We support both one-time sessions and recurring weekly ones, each with different rules.

Instead of checking the type everywhere with `if` statements, we built a `SessionFactory` that creates the right object based on the data. Both types share the same interface, so the rest of the code stays simple and doesn't need to know the details.

### 4. Strategy Pattern

Users want to sort sessions differently—by closest location, earliest time, or shared major.

We created separate `MatchingStrategy` classes and switch between them based on user preference. This kept the sorting logic clean and made it easy to add new options later.

### 5. Singleton Pattern

Our notification system was sending duplicates when someone had multiple tabs open.

By making the notification service a singleton (using JavaScript module scoping), we ensured only one instance runs. The duplicate alerts stopped immediately.

### 6. Facade Pattern

Components were importing too many different hooks and services, making files cluttered and hard to read.

We created a single `useStudyBuddy(sessionId)` facade hook that provides everything a page needs: session data, actions, and status checks. Component code became much shorter and easier to understand.

### 7. Decorator Pattern

Some sessions are “featured” (official tutoring events) or hosted by “verified” users, needing special badges.

Instead of adding flags all over the code, we wrap session objects with decorators at runtime to add the extra display info. This kept the core model clean.

## III. Impact on Our Student Team Project

These patterns had a huge effect on our work as students with limited time and experience:

- **Fewer Bugs and Less Stress**: Problems were isolated, so changes in one area rarely broke something else.
- **Easier Teamwork**: We could divide tasks confidently because the patterns created clear boundaries.
- **Faster Progress**: Adding new features felt like building on solid ground rather than patching a leaky boat.
- **Better Learning**: Seeing patterns solve real issues made them click in a way textbooks never did.

We spent less time fixing messes and more time making the app actually useful.

## IV. Lessons for a Student Developer

This project showed me that design patterns aren't just for senior engineers or big companies. Even in a student team project with a simple app, they help manage complexity and make code more professional.

Modern tools like React hooks and RxJS make many patterns easier to implement than in older languages. The trick is recognizing when a problem matches a pattern and applying it only where it helps—never forcing it.

## V. Conclusion

Before this, design patterns felt distant and theoretical. Now, having used them to rescue our team project from chaos, I see them as practical tools any developer can use to write better, more maintainable code.

Study Buddy turned out far better than I expected for a project, and I credit much of that to these patterns. They didn't just improve the final product; they made the whole development experience less overwhelming and more rewarding. I'm excited to keep using them as I continue learning and building more projects.
