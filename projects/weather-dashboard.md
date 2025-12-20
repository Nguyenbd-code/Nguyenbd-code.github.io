---
layout: project
type: project
image: img/weather/weatherlogo.jpg
title: "Weather Dashboard"
date: 2025-6-20
published: true
labels:
  - HTML
  - CSS
  - JavaScript
  - API
  - GitHub
summary: "Dynamic weather app displaying current conditions and 5-day forecasts using OpenWeatherMap API."
---

# Weather Dashboard

## Overview
A single-page web application that allows users to search for any city worldwide and view real-time current weather conditions plus a detailed 5-day forecast. Features include temperature, humidity, wind speed, UV index (color-coded), weather icons, and persistent search history.

## My Contributions
Solo project from concept to deployment:
- Designed responsive layout with Bootstrap cards.
- Integrated asynchronous API calls to OpenWeatherMap's current weather and one-call endpoints.
- Dynamically generated forecast cards with proper date formatting and icons.
- Implemented search history saved to localStorage with clickable recent searches.

## What I Learned
- Working with third-party REST APIs and handling JSON responses.
- Advanced asynchronous JavaScript using **fetch**, **async/await**, and error handling.
- Manipulating dates with JavaScript's Date object and Unix timestamps.
- Creating dynamic, reusable UI components without a framework.

## Technologies Used
HTML, CSS (Bootstrap), Vanilla JavaScript, OpenWeatherMap API

## Snapshot

<img class="img-fluid" src="../img/weather/Weatherimg.png">

## Code Highlights

**Fetching current weather:**
```javascript
async function fetchWeather(city) {
  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${API_KEY}&units=imperial`;
  const response = await fetch(url);
  if (!response.ok) throw new Error('City not found');
  const data = await response.json();
  displayCurrent(data);
}

function renderForecast(dailyData) {
  dailyData.slice(0, 5).forEach(day => {
    const card = createForecastCard(day);
    forecastContainer.appendChild(card);
  });
}
