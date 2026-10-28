# 🛠️ HomeTech Fix
### *On-Demand Doorstep Home Repair & Service Booking Platform with Live GPS Technician Tracking*

[![Node.js](https://img.shields.io/badge/Node.js-18%2B-339933?logo=nodedotjs&logoColor=white)](https://nodejs.org)
[![Express.js](https://img.shields.io/badge/Express.js-5.x-000000?logo=express&logoColor=white)](https://expressjs.com)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-47A248?logo=mongodb&logoColor=white)](https://www.mongodb.com)
[![Leaflet.js](https://img.shields.io/badge/Leaflet.js-OpenStreetMap-199900?logo=leaflet&logoColor=white)](https://leafletjs.com)
[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](https://opensource.org/licenses/ISC)

---

## 📖 Overview

**HomeTech Fix** is a modern, full-stack on-demand home maintenance and technician dispatch application. It connects homeowners with certified repair professionals across plumbing, electrical work, HVAC/AC servicing, and cleaning.

The platform provides a consumer booking flow, simulated **real-time technician GPS tracking** on interactive OpenStreetMap tiles, automated technician assignment, and full CRUD booking management powered by an Express.js and MongoDB Atlas backend.

---

## ✨ Key Features

- ⚡ **Instant Multi-Service Booking:** Book vetted technicians for Electrical, Plumbing, AC Repair, and Cleaning with minimal input.
- 👨‍🔧 **Automated Technician Dispatch:** Intelligently pairs bookings with verified local technicians based on availability, ratings (e.g. ⭐ 4.8), and initial ETAs.
- 📍 **Real-Time GPS Technician Tracking:** Interactive map powered by **Leaflet.js** and **OpenStreetMap** with animated technician location updates and live countdown ETA counters.
- 📞 **Direct Contact Integration:** Direct one-click phone dialing to assigned service specialists.
- 📋 **Booking Management & History:** "My Bookings" dashboard to monitor real-time order status, technician credentials, and manage service requests.
- 🔐 **Authentication & Role-Based Access:**
  - Client-side User Registration & Login system.
  - Dedicated Admin access portal for service oversight.
- 🌐 **RESTful API Backend:** Clean CRUD endpoints built on Express.js with Mongoose ODM integration.

---

## 🛠️ Service Categories

| Service | Icon | Description | Typical ETA |
| :--- | :---: | :--- | :--- |
| **Electrician** | ⚡ | Wiring, circuit troubleshooting, switchboard & appliance installation | 8 – 15 mins |
| **Plumbing** | 🚿 | Leak repairs, pipe fixing, drain unblocking & fixture replacements | 10 – 20 mins |
| **AC Repair** | ❄️ | Cooling diagnostics, gas refilling, filter sanitization & servicing | 15 – 25 mins |
| **Home Cleaning** | 🧹 | Deep cleaning, kitchen/bathroom sanitization & dust extraction | Scheduled |

---

## 🏗️ Architecture & Technology Stack

```
HomeTech Fix Platform
│
├── Frontend (Client)
│   ├── HTML5 (Semantic Structure)
│   ├── CSS3 (Dark/Glassmorphic Modern UI & Animations)
│   ├── Vanilla JavaScript (DOM manipulation & State Management)
│   └── Leaflet.js / OpenStreetMap (Live Geolocation Map)
│
├── Backend (REST API Server)
│   ├── Node.js (Runtime Environment)
│   ├── Express.js 5.x (HTTP Routing & Middleware)
│   ├── CORS (Cross-Origin Resource Sharing)
│   └── bcryptjs (Password & Security Utilities)
│
└── Database (Cloud Persistence)
    ├── MongoDB Atlas (Managed Cloud NoSQL Database)
    └── Mongoose ODM (Data Modeling & Schema Validation)
```

---

## 📡 API Endpoints Specification

| Method | Endpoint | Description | Request Payload / Params |
| :--- | :--- | :--- | :--- |
| **GET** | `/` | Serves main booking application UI | None |
| **POST** | `/book` | Submits new service request & assigns technician | `{ name, service, phone }` |
| **GET** | `/bookings` | Fetches all active & historical bookings | None |
| **PUT** | `/update-status/:id` | Updates status (e.g. "Completed", "In Progress") | `{ status }` (URL Param: `:id`) |
| **DELETE** | `/delete-booking/:id` | Cancels and deletes a booking by ID | URL Param: `:id` |

---

## 🗄️ Database Schema (`Booking`)

```javascript
{
  name: String,            // Customer Name
  service: String,         // Service Type (Electrician, Plumbing, etc.)
  phone: String,           // Customer Contact Number
  status: {
    type: String,
    default: "Technician Assigned"
  },
  technician: String,      // Name of Assigned Technician
  eta: String,             // Estimated Arrival Time (e.g. "15 mins")
  rating: String,          // Technician Rating (e.g. "⭐ 4.8")
  techPhone: String        // Technician Direct Phone Number
}
```

---

## 🚀 Getting Started

### Prerequisites
- [Node.js](https://nodejs.org) (v16.0 or higher)
- [npm](https://www.npmjs.com/) (Node Package Manager)
- MongoDB Database (Local instance or MongoDB Atlas cluster URI)

### Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/akshaysharma2005/HomeTechFix.git
   cd HomeTechFix
   ```

2. **Install project dependencies:**
   ```bash
   npm install
   ```

3. **Configure Environment Variables (Optional):**
   By default, the server connects via `server.js`. You can specify a custom MongoDB URI and Port using environment variables:
   ```bash
   export PORT=3000
   export MONGO_URI="your_mongodb_connection_string"
   ```

4. **Launch the Server:**
   ```bash
   npm start
   ```
   Or run with Node directly:
   ```bash
   node server.js
   ```

5. **Open in Browser:**
   Visit **`http://localhost:3000`** (or open `login.html` / `index.html` directly).

---

## 📂 Repository File Structure

```text
HomeTechFix/
├── index.html        # Main Client Application Dashboard & Booking Interface
├── login.html        # Authentication Portal (Login / Register & Admin)
├── style.css         # Custom Dark Modern Styling & Animations
├── server.js         # Express.js REST API Server & MongoDB Connection
├── package.json      # Node.js Dependencies & Script Manifest
├── package-lock.json # Dependency Version Lockfile
├── logo.png          # Platform Branding Logo
└── README.md         # Comprehensive Project Documentation
```

---

## 🔮 Future Roadmap

- [ ] Real WebSockets / Socket.io live technician location streaming
- [ ] Razorpay / Stripe payment gateway integration for online checkout
- [ ] Push notifications & SMS status alerts via Twilio
- [ ] Customer reviews & photo upload for repair diagnostics
- [ ] Technician mobile companion PWA

---

## 👤 Author

**M Akshay Sharma**
- GitHub: [@akshaysharma2005](https://github.com/akshaysharma2005)

---

## 📄 License

This project is licensed under the [ISC License](https://opensource.org/licenses/ISC).
