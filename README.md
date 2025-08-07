# 📆 Subscription Tracker API

A production-ready **Node.js + Express API** for managing and tracking user subscriptions, created with the [JS Mastry Complete Backend Course](https://www.youtube.com/watch?v=rOpEN1JDaD0).

> Built as a learning project to understand real-world API architecture, email workflows, authentication, and backend security.

---

## 🚀 Features

* ✅ JWT-based user authentication
* 📅 Full subscription CRUD operations
* 📧 Automated email reminders with Upstash Workflows
* 🔐 Advanced rate-limiting and bot protection via Arcjet
* 🧠 MongoDB & Mongoose schema modeling
* ⚙️ Global error handling, input validation, and logging
* 🧰 Modular, scalable folder structure

---

## 🛠️ Tech Stack

* **Node.js** + **Express.js**
* **MongoDB** + **Mongoose**
* **JWT** for authentication
* **Nodemailer** for email handling
* **Arcjet** for rate limiting and protection
* **Upstash Workflows** for automation
* **dotenv**, **morgan**, **bcryptjs**, and more

---

## 📁 Project Structure

```bash
.
├── app.js                   # Main application entry point
├── config/                  # Env, nodemailer, Arcjet, Upstash config
├── controllers/             # Logic for each route
├── database/                # MongoDB connection logic
├── middlewares/             # Auth, error, and Arcjet middleware
├── models/                  # User and Subscription schemas
├── routes/                  # Express route definitions
├── utils/                   # Email templates, sendMail, helpers
├── package.json             # Dependencies and metadata
└── jsconfig.json            # Path aliases
```

---

## 📅 API Endpoints

### 🔐 Auth (`/api/auth`)

* `POST /register`
* `POST /login`

### 👤 Users (`/api/users`)

* `POST /` – Create new user *(WIP)*
* `PUT /:id` – Update user *(WIP)*
* `DELETE /:id` – Delete user *(WIP)*

### 💳 Subscriptions (`/api/subscriptions`)

* `POST /` – Create subscription
* `GET /` – Get all subscriptions *(WIP)*
* `GET /:id` – Get subscription by ID *(WIP)*
* `PUT /:id` – Update subscription *(WIP)*
* `DELETE /:id` – Delete subscription *(WIP)*
* `PUT /:id/cancel` – Cancel subscription *(WIP)*
* `GET /upcoming-renewals` – Get upcoming renewals *(WIP)*

### ♻️ Workflows (`/api/workflows`)

* Automates emails & reminders via Upstash

---

## 📧 Email Notifications

* Email templates and handlers in `utils/email-template.js`
* Notifications for upcoming renewals & events
* Built using **Nodemailer** and **Upstash Workflow**

---

## 🔒 Security

* JWT-based session auth
* Arcjet for abuse protection and rate limiting
* Custom middleware for validation and error handling

---

## ✅ Setup & Installation

```bash
# 1. Clone the repo
$ git clone https://github.com/nuwandev/subscription-tracker.git
$ cd subscription-tracker

# 2. Install dependencies
$ npm install

# 3. Configure environment
Edit `config/env.js` with:
  - MONGO_URI
  - JWT_SECRET
  - SMTP credentials (Nodemailer)
  - Arcjet keys (optional)

# 4. Run the server
$ npm run dev
```

---

## 🔄 Roadmap

* [ ] Complete subscription route functionality
* [ ] Dashboard integration (React or Next.js)
* [ ] Admin roles & permissions
* [ ] Logging and analytics support

---

## 🧱 Contributing

This project was built as a learning experience — and contributions are welcome!

```bash
# Fork the repo
# Create a new branch
$ git checkout -b feature/your-feature-name
# Commit your changes
$ git commit -m "Add your feature"
# Push and open a pull request
```

Please open issues or discussions if you'd like to suggest improvements.

---

## 📄 License

[MIT](LICENSE)

---

## 🙌 Shoutout

## 📚 Tutorial Reference

This project was originally based on:

**[Complete Backend Course | Build and Deploy Your First Production-Ready API](https://www.youtube.com/watch?v=fgTGADljAeg)**  
by [JavaScript Mastery](https://www.youtube.com/@javascriptmastery)

> Covers everything from HTTP, API types, backend architecture, authentication, workflows, email automation, to VPS deployment.  
> I followed along, built it step-by-step, and added my own improvements.

---

> Built and maintained by [@nuwandev](https://github.com/nuwandev) ❤️
