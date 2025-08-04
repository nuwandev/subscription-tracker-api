# Subscription Tracker

A production-ready Node.js API for managing and tracking user subscriptions, inspired by the [JavaScript Mastery](https://www.youtube.com/@javascriptmastery) YouTube channel's "Complete Backend Course | Build and Deploy Your First Production-Ready API" video.

## Features

- User authentication (JWT-based)
- Subscription CRUD operations
- Automated email notifications (Nodemailer)
- Workflow automation for subscription events
- MongoDB integration
- Modular, scalable architecture
- Robust error handling and middleware

## Project Structure

```
.
├── app.js                   # Main application entry point
├── config/                  # Configuration files (env, nodemailer, upstash, arcjet)
├── controllers/             # Route controllers (auth, subscription, user, workflow)
├── database/                # MongoDB connection setup
├── middlewares/             # Custom middleware (auth, error, arcjet)
├── models/                  # Mongoose models (user, subscription)
├── routes/                  # Express route definitions
├── utils/                   # Utility functions (email templates, send email)
├── package.json
└── jsconfig.json
```

## Getting Started

### Prerequisites

- Node.js (v16+ recommended)
- MongoDB instance (local or cloud)

### Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/nuwandev/subscription-tracker.git
   cd subscription-tracker
   ```
2. Install dependencies:
   ```sh
   npm install
   ```
3. Configure environment variables:
   - Edit `config/env.js` with your credentials (MongoDB URI, email, etc.)
4. Start the application:
   ```sh
   node app.js
   ```
   Or for development:
   ```sh
   npx nodemon app.js
   ```

## API Endpoints

- **Auth:** `/api/auth` (register, login)
- **Users:** `/api/users`
- **Subscriptions:** `/api/subscriptions`
- **Workflows:** `/api/workflows`

See the `routes/` directory for detailed endpoint documentation.

## Planned & Unimplemented Endpoints

The following endpoints are present in the codebase but are currently stubs or need full implementation. Contributions are welcome!

### User Routes (`/api/users`)

- `POST /` — Create new user (not implemented)
- `PUT /:id` — Update user (not implemented)
- `DELETE /:id` — Delete user (not implemented)

### Subscription Routes (`/api/subscriptions`)

- `GET /` — Get all subscriptions (not implemented)
- `GET /:id` — Get subscription details (not implemented)
- `PUT /:id` — Update subscription (not implemented)
- `DELETE /:id` — Delete subscription (not implemented)
- `PUT /:id/cancel` — Cancel subscription (not implemented)
- `GET /upcoming-renewals` — Get upcoming renewals (not implemented)

If you’d like to contribute, check the corresponding files in `routes/` and `controllers/` and help implement these features!

## Email Notifications

- Configured via `config/nodemailer.js` and templates in `utils/email-template.js`.
- Automated emails for subscription events (renewals, expirations, etc.).

## Credits

This project was built by following the [JavaScript Mastery Complete Backend Course](https://www.youtube.com/watch?v=fgTGADljAeg) on YouTube.

## Contribution

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a pull request

## License

MIT
