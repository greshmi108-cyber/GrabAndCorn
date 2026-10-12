# 🍿 GrabAndCorn

A full-stack movie ticket booking web app. Users can browse now-showing movies, watch trailers, pick showtimes, select seats, pay online, and receive a booking confirmation email. Admins get a dashboard to manage shows and bookings.

## Features

- 🎬 Browse now-playing movies with details, trailers, and showtimes (data from TMDB)
- 🪑 Interactive seat selection
- 💳 Online payments with Stripe (webhook-based confirmation)
- 📧 Booking confirmation emails via Nodemailer
- ⏱️ Background jobs with Inngest
- 🔐 Authentication and user management with Clerk
- ❤️ Favorite movies and "My Bookings" page
- 🛠️ Admin dashboard: add shows, list shows, list bookings
- 📱 Responsive UI built with React and Tailwind CSS

## Tech Stack

**Frontend:** React (Vite), Tailwind CSS, Clerk, Axios, React Hot Toast

**Backend:** Node.js, Express, MongoDB (Mongoose), Stripe, Inngest, Nodemailer

## Project Structure

```
GrabAndCorn/
├── client/                 # React + Vite frontend
│   ├── src/
│   │   ├── components/
│   │   ├── pages/          # incl. admin pages
│   │   ├── context/
│   │   ├── lib/
│   │   ├── App.jsx
│   │   └── main.jsx
│   └── package.json
├── server/                 # Node + Express backend
│   ├── configs/
│   ├── controllers/
│   ├── inngest/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── server.js
│   └── package.json
└── README.md
```

## Getting Started

### Prerequisites

- Node.js (v18+)
- A MongoDB Atlas cluster or local MongoDB
- Accounts/keys for Clerk, TMDB, Stripe, Inngest, and an SMTP provider

### Installation

```bash
git clone https://github.com/<your-username>/GrabAndCorn.git
cd GrabAndCorn

# backend
cd server
npm install

# frontend
cd ../client
npm install
```

### Environment Variables

Copy the example files and fill in your own values:

```bash
cp server/.env.example server/.env
cp client/.env.example client/.env
```

See `server/.env.example` and `client/.env.example` for the full list of variables.

### Running the App

```bash
# backend (http://localhost:3000)
cd server
npm run server

# frontend (http://localhost:5173)
cd client
npm run dev
```

## Scripts

| Location | Command | Description |
|----------|---------|-------------|
| `client` | `npm run dev` | Start the Vite dev server |
| `client` | `npm run build` | Build the frontend for production |
| `server` | `npm run server` | Start the backend with nodemon |
| `server` | `npm start` | Start the backend in production |

## API Overview

| Route prefix | Purpose |
|--------------|---------|
| `/api/show` | Movies and showtimes |
| `/api/booking` | Seat booking and payments |
| `/api/user` | User bookings and favorites |
| `/api/admin` | Admin dashboard data |
| `/api/stripe` | Stripe webhook |
| `/api/inngest` | Background job handler |
