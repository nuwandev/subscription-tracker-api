# 📆 Subscription Tracker API

[![MIT License](https://img.shields.io/badge/license-MIT-green)](./LICENSE) [![Node Version](https://img.shields.io/badge/node-%3E%3D16-brightgreen)]() [![build](https://img.shields.io/github/actions/workflow/status/nuwandev/subscription-tracker/ci.yml)]()

> A production-ready **Node.js + Express API** for managing subscriptions with JWT authentication, automated email reminders, and a modular, scalable folder structure. Perfect for learning backend patterns or building real-world applications.

---

## 🚀 Features

* ✅ JWT-based authentication and session management
* 📅 Full subscription CRUD operations
* 📧 Automated email reminders with Upstash Workflows
* 🔒 Advanced rate-limiting and bot protection via Arcjet
* 🧠 MongoDB & Mongoose schema modeling with validation
* ⚙️ Global error handling, input validation, and logging
* 🧰 Modular and scalable folder structure
* ⚡ Ready for production deployment and future extension

---

## 🛠 Tech Stack

* **Node.js** + **Express.js** (ES modules)
* **MongoDB** + **Mongoose**
* **JWT** for authentication
* **Nodemailer** for email handling
* **Arcjet** for rate limiting and protection
* **Upstash Workflows** for automation
* **dotenv**, **bcryptjs**, **cookie-parser**, and more
* **Development:** `nodemon` for live reload

---

## 📁 Project Structure

```
.
├── app.js                   # Entry point
├── config/                  # Environment, Nodemailer, Arcjet, Upstash setup
├── controllers/             # Business logic for routes
├── database/                # MongoDB connection logic
├── middlewares/             # Auth, validation, error handling
├── models/                  # User & Subscription schemas
├── routes/                  # Express route definitions
├── utils/                   # Helpers, email templates
├── tests/                   # Optional tests
├── package.json             # Dependencies and metadata
└── jsconfig.json            # Path aliases
```

---

## 🔧 Setup & Installation

```bash
# Clone the repository
git clone https://github.com/nuwandev/subscription-tracker.git
cd subscription-tracker

# Install dependencies
npm install

# Configure environment variables
cp env.example .env
# Edit .env locally with your credentials (never commit real secrets)

# Run development server
npm run dev
```

---

## 📦 API Endpoints

### 🔐 Auth (`/api/v1/auth`)

* `POST /register` — Register a new user
* `POST /login` — Authenticate user and return JWT

### 👤 Users (`/api/v1/users`)

* `POST /` — Create user (WIP)
* `PUT /:id` — Update user (WIP)
* `DELETE /:id` — Delete user (WIP)

### 💳 Subscriptions (`/api/v1/subscriptions`)

* `POST /` — Create subscription (protected)
* `GET /` — List subscriptions (protected, WIP)
* `GET /:id` — Get subscription by ID (protected, WIP)
* `PUT /:id` — Update subscription (protected)
* `DELETE /:id` — Delete subscription (protected)
* `PUT /:id/cancel` — Cancel subscription (protected, WIP)
* `GET /upcoming-renewals` — Fetch upcoming renewals (WIP)

### ♻️ Workflows (`/api/v1/workflows`)

* Automate email reminders via Upstash

---

## 🔁 Authentication Flow

1. Register → user created
2. Login → JWT returned
3. Include `Authorization: Bearer <token>` header for protected endpoints

---

## 🔍 Example Requests

**Register user:**

```bash
curl -X POST http://localhost:5500/api/v1/auth/register \
-H "Content-Type: application/json" \
-d '{"name":"Demo","email":"demo@example.com","password":"Pass123!"}'
```

**Login:**

```bash
curl -X POST http://localhost:5500/api/v1/auth/login \
-H "Content-Type: application/json" \
-d '{"email":"demo@example.com","password":"Pass123!"}'
```

**Create subscription:**

```bash
curl -X POST http://localhost:5500/api/v1/subscriptions \
-H "Authorization: Bearer <JWT_TOKEN>" \
-H "Content-Type: application/json" \
-d '{"title":"Netflix","price":9.99,"currency":"USD","renewalDate":"2025-09-01","interval":"monthly","notes":"Family plan"}'
```

---

## 📄 License

[MIT](./LICENSE)

---

## Credits

Built and maintained by [@nuwandev](https://github.com/nuwandev). Inspired by [JavaScript Mastery](https://www.youtube.com/@javascriptmastery).
