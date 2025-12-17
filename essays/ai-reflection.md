---
layout: essay
type: essay
title: "Reflections on Using AI in ICS 314"
# All dates must be YYYY-MM-DD format!
date: 2025-12-16
published: true
labels:
  - AI
  - Software Engineering
  - Learning
  - Reflection
---

# Reflections on AI in ICS 314

## I. Introduction

AI tools are quickly becoming essential for developers, giving instant help with errors, explanations, and new ideas that used to take hours of searching through docs or forums. In a course like ICS 314, focused on practical web development with JavaScript/TypeScript, React, Bootstrap, and strong emphasis on clean code through ESLint and timed WODs, AI can speed things up—but only if used thoughtfully.

I used AI quite a bit throughout the semester, mainly **ChatGPT** (GPT-4o) and sometimes **GitHub Copilot**. I leaned on it for debugging tough errors, clarifying confusing messages, and getting ideas for edge cases or tests. That said, I tried to keep it in check—probably using it for about two out of every five problems—so I still got the full benefit of figuring things out myself.

## II. Personal Experience with AI

Here’s a breakdown of where I did (and didn’t) turn to AI:

1. **Experience WODs**  
   I usually tackled Experience WODs—like the BrowserHistory or Bootstrap layout ones—without AI at first. About 40% of the time, though, I’d get stuck on a stubborn error and ask ChatGPT to help diagnose it. For instance, when chaining Underscore functions led to an undefined property error, I pasted the code and asked why it was happening even though the data seemed fine. It pointed out I needed better null checks, which got me unstuck fast without handing me the whole answer.

2. **In-class Practice WODs**  
   I did not use AI during in-class practice WODs. These are all about raw repetition—building speed and muscle memory through trial and error. Pulling up AI would have slowed me down and taken away from the real practice, so I forced myself to work through issues manually, even if it meant finishing fewer reps.

3. **In-class WODs**  
   No AI here either. Timed WODs simulate real pressure situations, like technical interviews, where you can’t pause to query a model. I prepared ahead and relied purely on what I’d practiced.

4. **Essays**  
   I only reached for AI a handful of times, mostly to smooth out phrasing or check if a paragraph flowed well. The ideas and arguments were always mine—I just wanted the writing to come across clearly and professionally.

5. **Final Project**  
   My final project, Study Buddy, is a web app that lets UH students connect with classmates in the same courses to set up study sessions. It has user profiles, course selection, availability scheduling, matching, and invitations. I used AI in roughly 40% of the trickier parts, almost exclusively for debugging and testing. Common prompts were “What’s causing this useEffect infinite loop with these dependencies?” or “Suggest some Jest edge cases for partial availability overlaps in matching.” It caught sneaky issues fast and helped me write more solid tests, but I always tweaked its suggestions to match my actual code.

6. **Learning a concept / tutorial**  
   After screencasts, if something still didn’t click, I’d ask ChatGPT for another angle. For example, I had it break down useMemo versus useCallback with real scenarios where the choice actually impacts performance. Those follow-up explanations often made things clearer than re-reading the official docs.

7. **Answering a question in class or in Discord**  
   Occasionally, before jumping in on Discord, I’d double-check a detail with AI—like how React Strict Mode doubles renders in dev mode—to make sure I wasn’t spreading wrong info.

8. **Asking or answering a smart-question**  
   A few times I refined a question with AI, pasting my draft and asking it to add more context or clarify the error description. That usually got me better, faster help from the community.

9. **Coding example (e.g., using Underscore .pluck)**  
   I wrote examples myself first, then sometimes asked about edge cases—like behavior with missing properties or sparse arrays—to make my understanding more complete.

10. **Explaining code**  
    For dense walkthrough code or my own complicated sections, I’d feed it to ChatGPT and ask for a step-by-step walkthrough. It really helped untangle logic I was struggling to follow.

11. **Writing code**  
    I did almost all my own coding. AI was only a last resort for quick syntax fixes or when an error completely blocked me—never for writing whole functions or components.

12. **Documenting code**  
    I wrote comments and docs myself most of the time. Occasionally I’d ask for phrasing ideas on tricky error-handling parts, but that was rare.

13. **Quality assurance**  
    This was where AI shone for me—probably used it two out of five times for QA. Pasting ESLint warnings, console errors, or asking for test ideas saved tons of time and pushed me to cover corners I might have skipped.

14. **Other uses**  
    AI came in handy for deployment snags (like weird routing issues on Vercel) and extra test brainstorming for things like handling duplicate session requests.

## III. Impact on Learning and Understanding

Using AI selectively really boosted my debugging mindset and made me think harder about edge cases, which translated into cleaner, more reliable code. Quick diagnoses trained me to break down problems systematically. Since I didn’t over-rely on it, I still spent plenty of time wrestling with issues myself, and that struggle is what solidified the concepts for me. Overall, it deepened my practical grasp of software engineering without dulling the critical thinking part.

## IV. Practical Applications

I’ve carried this same balanced approach into personal projects and prep for internships—using AI mainly as a debugging and testing aid. It feels a lot like how pros use Copilot or similar tools: great for speeding up the grunt work while keeping the architecture and decisions firmly in human control.

## V. Challenges and Opportunities

The main hurdles were getting prompts right to avoid bad advice and fighting the urge to use AI too often. Sometimes it suggested fixes that worked but weren’t ideal, forcing me to verify everything. On the flip side, there’s huge potential for courses to teach prompt crafting for debugging or position AI as a specialized assistant—maybe even with guided exercises on using it effectively.

## VI. Comparative Analysis

The classic ICS 314 setup—screencasts, solo practice, timed WODs—forces you to internalize material through effort and repetition, which builds lasting confidence. Layering in moderate AI help accelerates feedback on errors and exposes you to more test scenarios faster. Together, they complement each other well: traditional methods give depth, AI adds breadth and efficiency.

## VII. Future Considerations

As models get better at context and accuracy, AI will probably become a standard sidekick in software engineering classes—maybe even integrated for instant, reliable debugging feedback. The trick will be setting guidelines that promote smart, limited use so students still hone independent skills that employers actually need.

## VIII. Conclusion

My experience with AI in ICS 314 felt like having a helpful junior pair-programmer: great for spotting bugs and brainstorming tests when I needed it, but never taking the wheel. It let me deliver a solid Study Buddy app while preserving the course’s core value of personal mastery. Going forward, I think explicitly teaching targeted AI techniques—like crafting strong debugging prompts—would help everyone strike the right balance between tool assistance and real skill-building.
