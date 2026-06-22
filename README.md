# 🌤️ Breeze Weather App

Breeze is a premium, high-performance, hyper-local weather dashboard built with clean web technologies and a gorgeous glassmorphism UI. 

Breeze fetches real-time coordinates natively from your browser's geolocation sensors, converts coordinates into clean location names, and retrieves hyper-local weather data with minimal footprint and maximum loading speeds.

## 🚀 Live Demo
**Production Deployment:** [https://breeze-weather-jees.vercel.app](https://breeze-weather-jees.vercel.app)

---

## ✨ Features

* **🏎️ Zero-Setup High-Speed Load:** Gated weather rendering ensures only **exactly one** API query is fired on load. Geolocation resolves in milliseconds before the weather fetch, eliminating redundant duplicate requests.
* **📍 W3C Geolocation API Integration:** Automatically prompts for location permissions. If blocked or denied, the app falls back to your last-known successfully loaded location stored in `localStorage`.
* **🎯 GPS Manual Locate Button:** A dedicated quick-locate button in the SearchBar allows manual re-location on demand.
* **🔍 OpenStreetMap Photon Autocomplete:** Instant search suggestions as you type (backed by Photon Komoot's Elasticsearch OpenStreetMap index), resolving local suburbs, districts, and villages starting from the first letter.
* **🗺️ 3D Maps Integration:** Real-time Google Maps Vector engine with custom-tuned styling mapping coordinates dynamically, with a responsive "Low Signal Mode" to toggle off maps/animations for data-saving.
* **📊 Vercel Web Analytics & Speed Insights:** Fully integrated tracking for core web vitals, speed scores, and real-user metrics.
* **🎨 Premium Glassmorphism UI:** Tailored CSS custom variables, smooth transitions, CSS safe-area support (`safe-area-inset`), and dynamic dark/light/system theme preferences.

---

## 🛠️ Tech Stack & APIs

| Component | Source / API | Description | License / Terms |
| :--- | :--- | :--- | :--- |
| **Frontend Core** | React 18 (via CDN) | UI Component rendering using classic Babel-standalone preset | MIT |
| **Weather Forecasts** | [Open-Meteo](https://open-meteo.com) | Real-time hourly/daily forecasts, AQI indicators, and UV index | CC BY 4.0 |
| **Location Fetching** | W3C Geolocation API | HTML5 native sensor coordinates query | Browser Native |
| **Search Autocomplete**| [Photon (Komoot)](https://photon.komoot.io) | Elasticsearch autocomplete engine for OpenStreetMap | ODbL |
| **Geocoding** | [OSM Nominatim](https://nominatim.openstreetmap.org) | Reverse-geocodes coordinate values to district/country labels | ODbL |
| **Maps Platform** | [Google Maps API](https://developers.google.com/maps) | Dynamic 3D WebGL vector maps loading | Google Maps Terms |
| **Analytics** | [Vercel Web Analytics](https://vercel.com/analytics) | Real-user analytics and web vitals tracking | Vercel platform |

---

## 🔒 Security & Environment Config

To prevent API key exposure in the public repository, the **Google Maps Platform** API key is loaded dynamically:
1. The client queries a serverless function endpoint: `/api/get-map-key.js`.
2. The serverless function retrieves the key from protected **Vercel Environment Variables** and returns it securely to the client.
3. The maps script is loaded dynamically on runtime.

---

## ⚙️ Development & Testing

Since browser geolocation calls require a **secure context**, the Geolocation API is disabled on non-secure origins (HTTP). 

* **Localhost Testing:** Geolocation will prompt and work normally at `http://localhost:3000`.
* **Mobile Network Testing:** When testing on actual mobile devices over a local Wi-Fi connection, you must access the server over HTTPS, or test using the live Vercel target: `https://breeze-weather-jees.vercel.app`.
* **Resetting Permissions:** If permissions are blocked, click the lock/settings icon next to the URL in your browser's address bar, reset the Location permission to "Allow", and reload the page.
