---
layout: essay
type: essay
title: "Design Patterns I Actually Used in ICS 314 (and why they matter)"
date: 2025-12-4
labels:
  - ICS 314
  - Software Engineering
  - Design Patterns
  - Team Project
---

# Design Patterns I Actually Used in ICS 314  
(and why they matter)

Before this class I thought design patterns were just something you memorize for interviews.  
Three weeks into our team project Study Buddy (a site that lets UH students create and join real-time study sessions), I now know better. They’re the reason our code didn’t turn into complete spaghetti.

We’re building a Next.js + TypeScript app where students can post “ICS 314 tomorrow 6pm Sinclair Library, need 3 people” and others can join instantly. Real-time updates, notifications, recurring sessions, location filtering—the usual ICS 314 chaos.

Here are the patterns we actually ended up using in our real codebase.

### Observer
When someone joins or leaves a session, every participant needs to see the change immediately.  
We made each session a RxJS `BehaviorSubject` and wrapped it in a `useSession(sessionId)` hook. Every client subscribes once. No polling, no stale data, no manual state passing. It just works.

### Command
People kept accidentally clicking “Leave” and begging to be added back.  
We turned Join/Leave into Command objects with `execute()` and `undo()`. Now undoing a mistake is literally one line. Saved us so many Slack messages.

### Factory
We have one-time study sessions and recurring weekly groups. Instead of checking `if (session.type === 'recurring')` everywhere, we use a `SessionFactory` that returns the correct class (both implement the same interface). The rest of the code doesn’t care.

### Strategy
Users want sessions sorted different ways: closest location, same major, earliest time.  
We wrote three `MatchingStrategy` classes and swap them with a single setting. Clean separation, easy to extend.

### Singleton
Our notification service was firing twice when someone had multiple tabs open.  
Made it a module-scoped singleton. Problem gone.

### Facade
Our components were importing five different hooks and services. We created one `useStudyBuddy(sessionId)` facade that returns everything a page needs: session data, join/leave functions, host status, etc. Component files got way shorter and way more readable.

### Decorator
Official tutoring-center sessions get a “featured” badge, power users get a “verified host” checkmark.  
We wrap the base session object with decorators at runtime instead of adding flags everywhere.

These aren’t theoretical. They’re in our actual repo, solving real problems we hit while building Study Buddy.

ICS 314 showed me design patterns aren’t about sounding smart.  
They’re tools that make three people on a tight deadline able to add features instead of just fixing bugs.

