# neergz-fashion-platform

Full-stack fashion design platform for students, studios, and companies.

## Stack

- Frontend: React + Vite + React Router
- Backend: Node.js + Express
- Database: MongoDB + Mongoose
- Auth: JWT (admin login)

## Features

- Marketing landing page with modern UI
- Light/dark theme toggle with persistence
- Contact form that creates inquiries
- Admin login
- Protected admin dashboard with inquiry table, search, and filters

## Project Structure

```text
neergz-fashion-platform
├── client
│   ├── src/pages
│   │   ├── Landing.jsx
│   │   ├── AdminLogin.jsx
│   │   └── AdminDashboard.jsx
│   ├── src/components
│   │   └── ThemeToggleButton.jsx
│   ├── src/lib
│   │   ├── api.js
│   │   └── theme.js
│   └── src/styles.css
└── server
    ├── src/routes
    │   ├── auth.js
    │   └── inquiries.js
    ├── src/middleware/auth.js
    ├── src/models/Inquiry.js
    └── src/index.js
```

## Environment Variables

### Server (`server/.env`)

```env
PORT=4000
MONGO_URI=mongodb://localhost:27017/fashion_designer
JWT_SECRET=replace_with_long_secret
ADMIN_EMAIL=admin@neergz.com
ADMIN_PASSWORD=changeme
```

### Client (`client/.env`)

```env
VITE_API_BASE_URL=
```

Leave `VITE_API_BASE_URL` empty for local same-origin API usage.

## Run Locally

Open 2 terminals.

### 1) Backend

```bash
cd /Users/apple/Documents/neergz-fashion-platform/server
cp -n .env.example .env
npm install
npm start
```

### 2) Frontend

```bash
cd /Users/apple/Documents/neergz-fashion-platform/client
cp -n .env.example .env
npm install
npm run dev -- --host 127.0.0.1 --port 5173
```

Open:

- `http://127.0.0.1:5173`
- `http://127.0.0.1:5173/admin/login`

## API

- `GET /api/health`
- `POST /api/auth/login`
- `POST /api/inquiries`
- `GET /api/inquiries` (Bearer token required)

## Troubleshooting

- If you see `Missing script: "start"`, you are likely in the wrong folder.
- Verify location first:

```bash
pwd
```

It must be exactly:

- `/Users/apple/Documents/neergz-fashion-platform/server` for backend
- `/Users/apple/Documents/neergz-fashion-platform/client` for frontend

## License

MIT
