# 🌤️ Breeze Weather App

Breeze is a hyper-local weather dashboard designed for high performance and visual clarity. This project was developed with the assistance of **Artificial Intelligence** to ensure optimized logic and a refined user interface.

## 🚀 Live Demo
https://breeze-weather-jees.vercel.app/

## ✨ Features
* **Hyper-local Accuracy:** Leverages the Open-Meteo API for precise, real-time weather data.
* **Interactive Maps:** Deep integration with Google Maps JavaScript API, featuring a custom-tuned Night Mode for better visibility.
* **Privacy & Security:** Securely handles sensitive information by using dynamic key loading via Vercel Serverless functions.
* **Responsive Design:** A fluid "glassmorphism" interface that adapts perfectly to mobile and desktop screens.

## 🛠️ Built With
* **HTML5:** Semantic structure for the core application.
* **CSS3:** Custom styling, including an advanced material system with blur effects and animations.
* **JavaScript:** Pure JS logic for API integration, geocoding, and map rendering.
* **Vercel:** Cloud hosting and secure Serverless backends.
* **AI Assistance:** Leveraged for advanced debugging, UI refinement, and architectural planning.

## 🔒 Security
The Google Maps API key is managed through Vercel Environment Variables. The frontend fetches this key dynamically from a protected backend route (`/api/get-map-key.js`), ensuring the key is never hardcoded in the public source code.
