# 📆 Subscription Tracker API

[![MIT License](https://img.shields.io/badge/license-MIT-green)](./LICENSE) [![Node Version](https://img.shields.io/badge/node-%3E%3D16-brightgreen)](https://nodejs.org/)

> A production-ready **Node.js + Express API** for managing subscriptions with JWT authentication, automated email reminders, and a modular, scalable folder structure. Perfect for learning backend patterns or building real-world applications.

---

## 🚀 Features

- ✅ JWT-based authentication and session management
- 📅 Full subscription CRUD operations
- 📧 Automated email reminders with Upstash Workflows
- 🔒 Advanced rate-limiting and bot protection via Arcjet
- 🧠 MongoDB & Mongoose schema modeling with validation
- ⚙️ Global error handling, input validation, and logging
- 🧰 Modular and scalable folder structure
- ⚡ Ready for production deployment and future extension

---

## 🛠 Tech Stack

- **Node.js** + **Express.js** (ES modules)
- **MongoDB** + **Mongoose**
- **JWT** for authentication
- **Nodemailer** for email handling
- **Arcjet** for rate limiting and protection
- **Upstash Workflows** for automation
- **dotenv**, **bcryptjs**, **cookie-parser**, and more
- **Development:** `nodemon` for live reload

---

## 📁 Project Structure

```plaintext
.
├── app.js                   # Entry point
├── config/                  # Environment, Nodemailer, Arcjet, Upstash setup
├── controllers/             # Business logic for routes
├── database/                # MongoDB connection logic
├── middlewares/             # Auth, validation, error handling
├── models/                  # User & Subscription schemas
├── routes/                  # Express route definitions
├── utils/                   # Helpers, email templates
├── tests/                   # (Not implemented; only test-user-info.json exists)
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

- `POST /sign-up` — Register a new user
- `POST /sign-in` — Authenticate user and return JWT

### 👤 Users (`/api/v1/users`)

- `POST /` — Create user (WIP)
- `PUT /:id` — Update user (WIP)
- `DELETE /:id` — Delete user (WIP)

### 💳 Subscriptions (`/api/v1/subscriptions`)

- `POST /` — Create subscription (protected)
- `GET /` — List subscriptions (protected, WIP)
- `GET /:id` — Get subscription by ID (protected, WIP)
- `PUT /:id` — Update subscription (protected)
- `DELETE /:id` — Delete subscription (protected)
- `PUT /:id/cancel` — Cancel subscription (protected, WIP)
- `GET /upcoming-renewals` — Fetch upcoming renewals (WIP)

### ♻️ Workflows (`/api/v1/workflows`)

- Automate email reminders via Upstash

---

## 🔁 Authentication Flow

1. Register → user created
2. Login → JWT returned
3. Include `Authorization: Bearer <token>` header for protected endpoints

---

## 🔍 Example Requests

Because of rate-limiting and bot protection (Arcjet), we recommend testing with **Postman** or **Insomnia** instead of raw `curl`.

Below are sample request bodies you can use:

### Register user

`POST /api/v1/auth/sign-up`

```json
{
  "name": "Demo",
  "email": "demo@example.com",
  "password": "Pass123!"
}
```

### Login

`POST /api/v1/auth/sign-in`

```json
{
  "email": "demo@example.com",
  "password": "Pass123!"
}
```

### Create subscription

`POST /api/v1/subscriptions` (requires `Authorization: Bearer <JWT_TOKEN>`)

```json
{
  "name": "Netflix",
  "price": 9.99,
  "currency": "USD",
  "frequency": "monthly",
  "category": "lifestyle",
  "paymentMethod": "Credit Card",
  "status": "active",
  "startDate": "2025-08-01T00:00:00.000Z",
  "renewalDate": "2025-09-01T00:00:00.000Z",
  "user": "<USER_ID>"
}
```

---

## 📄 License

[MIT](./LICENSE)

---

## Credits

Built and maintained by [@nuwandev](https://github.com/nuwandev). Inspired by [JavaScript Mastery](https://www.youtube.com/@javascriptmastery).
