# 🌤️ WeatherTech — Smart Weather Forecasting System

**B.Tech Web Technology Project** | Full-Stack Web Application

---

## 📋 Project Overview

WeatherTech is a modern, full-stack weather forecasting platform built with HTML5, CSS3, JavaScript (ES6), PHP, MySQL, AJAX, and the OpenWeatherMap API. It provides real-time weather data, 7-day forecasts, air quality monitoring, weather alerts, city comparison, and a full admin panel.

---

## 🗂️ Folder Structure

```
weather-tech/
├── index.html              ← Login / Register page
├── dashboard.html          ← Main weather dashboard
├── forecast.html           ← 7-day forecast
├── hourly.html             ← 24-hour forecast
├── compare.html            ← City comparison
├── history.html            ← Search history
├── alerts.html             ← Weather alerts
├── profile.html            ← User profile & settings
├── demo.html               ← Static demo (no API needed)
│
├── admin/
│   └── index.html          ← Admin panel (login + dashboard)
│
├── assets/
│   ├── css/
│   │   ├── main.css        ← Global styles, auth page, toast, theme
│   │   └── dashboard.css   ← Dashboard layout, cards, charts
│   └── js/
│       ├── config.js       ← API keys and constants
│       ├── utils.js        ← Toast, theme, formatting helpers
│       ├── weather-api.js  ← OpenWeatherMap API calls
│       ├── dashboard.js    ← Dashboard controller
│       ├── charts.js       ← Chart.js visualizations
│       └── auth.js         ← Login/Register logic
│
├── php/
│   ├── config.php          ← DB connection, helpers, session
│   ├── auth/
│   │   └── auth.php        ← Login, Register, Logout endpoints
│   ├── api/
│   │   ├── cities.php      ← Favorite cities CRUD
│   │   ├── history.php     ← Search history CRUD
│   │   └── profile.php     ← Profile update, password change
│   └── admin/
│       └── admin-api.php   ← Admin stats, users, logs, notifications
│
└── database/
    └── weather_tech.sql    ← Complete MySQL schema + seed data
```

---

## ⚙️ Installation Guide

### Prerequisites
- PHP 8.0+
- MySQL 5.7+ / MariaDB 10.3+
- Apache / Nginx (XAMPP / WAMP / LAMP)
- OpenWeatherMap API key (free at openweathermap.org)

### Step-by-Step Setup

**1. Place files in web server root**
```bash
# XAMPP example
cp -r weather-tech/ C:/xampp/htdocs/
# or Linux
cp -r weather-tech/ /var/www/html/
```

**2. Create the MySQL database**
```bash
mysql -u root -p < database/weather_tech.sql
```
Or open phpMyAdmin → Import → `database/weather_tech.sql`

**3. Configure database credentials**

Edit `php/config.php`:
```php
define('DB_HOST', 'localhost');
define('DB_USER', 'root');       // your MySQL username
define('DB_PASS', '');           // your MySQL password
define('DB_NAME', 'weather_tech');
```

**4. Add your OpenWeatherMap API key**

Edit `assets/js/config.js`:
```javascript
OPENWEATHER_API_KEY: 'YOUR_ACTUAL_API_KEY_HERE',
```
Get a free key: https://openweathermap.org/api

**5. Start the server and open the app**
```
http://localhost/weather-tech/
```

---

## 🔑 Demo Credentials

| Role  | Email                      | Password     |
|-------|----------------------------|--------------|
| Admin | admin@weathertech.app      | Password@123 |
| User  | rahul@example.com          | Password@123 |
| Guest | (click Guest Mode button)  | —            |

Admin Panel: `http://localhost/weather-tech/admin/`
Admin login: username `admin`, password `admin123`

---

## 🌐 API Used

- **OpenWeatherMap** — Current weather, 5-day forecast, Air Quality Index, Geocoding
  - Free tier: 60 calls/min, 1M calls/month
  - API Docs: https://openweathermap.org/api

---

## ✨ Features Summary

| Feature                  | Status |
|--------------------------|--------|
| User Registration/Login  | ✅     |
| Guest Mode               | ✅     |
| Current Weather          | ✅     |
| 5/7-Day Forecast         | ✅     |
| 24-Hour Hourly Forecast  | ✅     |
| Air Quality Index (AQI)  | ✅     |
| UV Index                 | ✅     |
| Wind Compass             | ✅     |
| Sunrise & Sunset         | ✅     |
| Weather Alerts           | ✅     |
| City Comparison          | ✅     |
| Favorite Cities          | ✅     |
| Search History           | ✅     |
| Interactive Charts       | ✅     |
| Geolocation              | ✅     |
| Dark / Light Theme       | ✅     |
| Responsive Design        | ✅     |
| Toast Notifications      | ✅     |
| Admin Panel              | ✅     |
| User Management          | ✅     |
| Search Logs              | ✅     |
| Password Hashing (bcrypt)| ✅     |
| SQL Injection Prevention | ✅     |
| XSS Protection           | ✅     |
| AJAX Calls               | ✅     |
| Caching (localStorage)   | ✅     |

---

## 🛡️ Security Features

- **Password hashing** — bcrypt (cost 12) via PHP `password_hash()`
- **SQL injection prevention** — PDO prepared statements throughout
- **XSS protection** — `htmlspecialchars()` on all outputs, `escapeHtml()` in JS
- **CSRF** — Session-based auth, same-origin enforcement
- **Input validation** — Server-side + client-side on all forms
- **Session management** — PHP sessions with `session.cookie_httponly`

---

## 📊 Database ER Summary

```
users ──< favorite_cities
users ──< search_history
users ──< weather_logs
users ──< notifications
```

---

## 👨‍💻 Tech Stack

| Layer     | Technology                          |
|-----------|-------------------------------------|
| Frontend  | HTML5, CSS3, JavaScript ES6         |
| Styling   | Custom CSS (no framework dependency)|
| Charts    | Chart.js v4                         |
| Icons     | Font Awesome 6                      |
| Fonts     | Google Fonts (Syne + DM Sans)       |
| Backend   | PHP 8.0+                            |
| Database  | MySQL 5.7+                          |
| API       | OpenWeatherMap REST API             |
| AJAX      | Fetch API (native JS)               |

---

*WeatherTech — B.Tech Web Technology Project*
