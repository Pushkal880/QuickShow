# QuickShow 🎬

QuickShow is a full-stack movie ticket booking web application built with the MERN stack. Users can browse now-showing movies, view details and trailers, pick a showtime and seat, book tickets online, and manage their bookings — while admins get a dedicated dashboard to manage shows and bookings.

## Features

- Browse now-showing and featured movies with details and trailers
- Interactive seat selection and date/showtime picker
- Secure authentication via [Clerk](https://clerk.com/)
- Online payments with [Stripe](https://stripe.com/)
- Background jobs / event-driven workflows with [Inngest](https://www.inngest.com/)
- Booking confirmation emails via Nodemailer
- Favorites and "My Bookings" pages for users
- Admin dashboard to add/list shows and view bookings
- Responsive UI styled with Tailwind CSS

## Tech Stack

**Frontend (`/client`)**
- React 19 + Vite
- React Router
- Tailwind CSS
- Clerk (auth)
- Axios, React Hot Toast, React Player, Lucide Icons

**Backend (`/server`)**
- Node.js + Express 5
- MongoDB with Mongoose
- Clerk (auth middleware)
- Stripe (payments + webhooks)
- Inngest (event-driven functions)
- Nodemailer + Cloudinary

## Project Structure

```
QuickShow-FullStack/
├── client/          # React frontend (Vite)
│   └── src/
│       ├── components/   # Reusable UI components (incl. admin/)
│       ├── pages/        # Route-level pages (incl. admin/)
│       ├── context/       # Global app context
│       └── lib/           # Formatting helpers
└── server/          # Express backend
    ├── configs/       # DB & Nodemailer config
    ├── controllers/   # Route logic (admin, booking, show, user, Stripe webhooks)
    ├── middleware/    # Auth middleware
    ├── models/        # Mongoose models (User, Movie, Show, Booking)
    ├── routes/        # API route definitions
    └── inngest/       # Inngest client & functions
```

## Getting Started

### Prerequisites
- Node.js
- A MongoDB instance (e.g. MongoDB Atlas)
- API keys for Clerk, Stripe, Inngest, and Cloudinary/Nodemailer as needed

### Setup

1. Clone the repository
   ```bash
   git clone <your-repo-url>
   cd QuickShow-FullStack
   ```

2. Install dependencies
   ```bash
   cd server && npm install
   cd ../client && npm install
   ```

3. Configure environment variables
   Create a `.env` file in both `server/` and `client/` with your own credentials (MongoDB URI, Clerk keys, Stripe keys, Inngest keys, etc.). These files are gitignored and should never be committed.

4. Run the app
   ```bash
   # Terminal 1 — backend
   cd server
   npm run server

   # Terminal 2 — frontend
   cd client
   npm run dev
   ```

## Deployment

Both `client/` and `server/` include `vercel.json` configs for deployment on [Vercel](https://vercel.com/).

## License

This project is for personal/educational purposes.
