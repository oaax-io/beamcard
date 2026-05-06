# Beamio Platform

GitHub-ready monorepo for Beamio.

## Structure

```txt
beamio-platform/
  frontend/   React + Vite + Tailwind
  backend/    NestJS + MongoDB + JWT + Stripe + Google Wallet
```

## Local setup

### 1. Install dependencies

```bash
npm run install:all
```

Or separately:

```bash
cd frontend && npm ci
cd ../backend && npm ci
```

### 2. Configure environment variables

Frontend:

```bash
cp frontend/.env.example frontend/.env
```

Backend:

```bash
cp backend/.env.example backend/.env
```

Update `backend/.env` with MongoDB, JWT, Stripe and Google Wallet values.

### 3. Start development servers

Backend:

```bash
npm run dev:backend
```

Frontend:

```bash
npm run dev:frontend
```

Default URLs:

- Frontend: http://localhost:3000
- Backend: http://localhost:3001

## Lovable usage

Recommended setup:

1. Push this project to GitHub.
2. Connect/open the repo in Lovable.
3. Work primarily inside `frontend/` in Lovable.
4. Deploy the backend separately, for example Railway, Render, Coolify, VPS or OAASE Cloud.
5. Set `VITE_API_URL` in the Lovable/frontend environment to your deployed backend URL.

## Deployment notes

### Frontend

Build command:

```bash
cd frontend && npm ci && npm run build
```

Output directory:

```txt
frontend/dist
```

### Backend

Build command:

```bash
cd backend && npm ci && npm run build
```

Start command:

```bash
npm run start:prod
```

Backend requires these environment variables:

- `MONGO_URI`
- `JWT_SECRET`
- `JWT_REFRESH_SECRET`
- `STRIPE_SECRET_KEY`
- `STRIPE_WEBHOOK_SECRET`
- `STRIPE_SUCCESS_URL`
- `STRIPE_CANCEL_URL`
- `FRONTEND_URL`
- `GOOGLE_APPLICATION_CREDENTIALS`
- `GOOGLE_ISSUER_ID`

## Important security note

Do not commit real `.env` files or Google service account credentials. Keep secrets in your hosting provider's environment variable settings.
