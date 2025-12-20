---
layout: project
type: project
image: img/todo/todologo.png
title: "Vanilla JavaScript To-Do List App"
date: 2025-11-15
published: true
labels:
  - HTML
  - CSS
  - JavaScript
  - localStorage
  - GitHub
summary: "Persistent to-do list application built with pure vanilla JavaScript – no frameworks."
---

# Vanilla JavaScript To-Do List App

## Overview
A lightweight, responsive to-do list app that allows users to add, edit, mark as complete, and delete tasks. All tasks are saved automatically to the browser's localStorage, ensuring persistence across sessions. This project demonstrates core front-end skills without relying on external libraries.

## My Contributions
Fully solo-developed:
- Created a clean, mobile-friendly UI with HTML and Bootstrap styling.
- Implemented task CRUD operations entirely in vanilla JavaScript.
- Added features like task editing, completion toggling, and automatic persistence.
- Ensured smooth user experience with instant updates and no page reloads.

## What I Learned
- Mastery of DOM manipulation, event delegation, and dynamic element creation.
- Effective use of **localStorage** for client-side data persistence.
- Structuring maintainable JavaScript code with modular functions.
- Building fully functional apps using only native web technologies – great preparation for framework-based development.

## Technologies Used
HTML, CSS (Bootstrap), Vanilla JavaScript

## Code Highlights

## Snapshot

<img class="img-fluid" src="../img/todo/To-do-list.png">

**Adding a new task:**
```javascript
function addTask(text) {
  const task = { id: Date.now(), text, completed: false };
  tasks.push(task);
  saveTasks();
  renderTasks();
}

