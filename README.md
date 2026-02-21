# VestBlock — Fractional Real Estate Investment Platform

Enterprise-grade fractional real estate investment platform supporting tokenized property investments across Pakistan, UAE, UK, USA, and Qatar.

## Features

- **Multi-Tenant Architecture** — Platform-level and user-level tenant isolation
- **Role-Based Access Control** — Investor, Issuer, Agent, Agency, Admin, Super Admin roles
- **KYC/AML Compliance** — Full identity verification and enhanced due diligence pipeline
- **Digital Wallets** — Multi-currency support (PKR, AED, GBP, USD, QAR, USDT, USDC) with FX conversion
- **Tokenized Investments** — SPV-backed fractional property ownership
- **Secondary Market** — Exit window-based trading system
- **AI-Powered Tools** — Document summarizer, property matching, ROI scenarios, Market Pulse
- **Appointment Scheduling** — Client/agent/manager booking system with email notifications
- **Email System** — Dev mode (log-only) + production (Resend API) with full audit logging
- **Marketing Automation** — Subscriber management, CSV export, campaign sending with segmentation
- **Transaction Security** — OTP-based 2FA for payment confirmation
- **Google OAuth** — Sign in with Google via passport-google-oauth20
- **PWA Support** — Installable app with offline fallback and service worker caching

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React 18, TypeScript, Vite, Tailwind CSS |
| Backend | Express.js 5, REST API |
| Database | PostgreSQL (Neon) + Drizzle ORM |
| Auth | JWT (httpOnly cookies) + Google OAuth |
| Styling | Glassmorphism UI, Royal Blue palette (#1E2BFF) |

## Project Structure

```
client/src/
  pages/          — 100+ pages (marketing, investor, admin, issuer, agent, agency, CMS)
  components/     — UI components (shadcn/ui based)
  lib/            — Auth, API client, utilities
server/
  controllers/    — 50+ domain controllers
  services/       — Business logic (fee engine, wallet, FX, etc.)
  middleware/     — Auth, tenant context, rate limiting, RBAC
  lib/ai/         — AI providers, RAG pipeline
shared/
  schema.ts       — 95+ Drizzle ORM tables
  constants.ts    — Platform configuration
```

## Getting Started

### Prerequisites

- Node.js 20+
- PostgreSQL database

### Installation

```bash
# Install dependencies
npm install

# Set up environment variables (see below)
cp .env.example .env

# Push database schema
npm run db:push

# Start development server
npm run dev
```

The app runs on `http://localhost:5000`.

### Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `DATABASE_URL` | Yes | PostgreSQL connection string |
| `SESSION_SECRET` | Yes | Session encryption key |
| `GOOGLE_CLIENT_ID` | No | Google OAuth client ID |
| `GOOGLE_CLIENT_SECRET` | No | Google OAuth client secret |
| `AI_INTEGRATIONS_OPENAI_API_KEY` | No | OpenAI API key for AI features |
| `RESEND_API_KEY` | No | Resend API key for production emails |
| `EMAIL_FROM` | No | Sender email address |

### Demo Users

All demo users use password: `password123`

| Username | Role |
|----------|------|
| `agency_manager` | Platform Admin |
| `khalid_malik` | Agent |
| `aisha_rahman` | Agent |
| `james_wilson` | Investor |
| `lisa_chen` | Investor |
| `robert_kim` | Investor |
| `maria_santos` | Investor |
| `tariq_hussain` | Investor |

## API Health Checks

- `GET /api/health` — System health (DB, auth, email status)
- `GET /api/health/rbac` — Role mapping and RBAC config (admin-only)
- `GET /api/health/pwa` — PWA asset readiness

## Design System

- **Palette**: Royal blue (#EEF0FF to #1E2BFF)
- **Font**: Plus Jakarta Sans
- **Style**: Glassmorphism with noise texture overlays
- **Dark Mode**: Supported

## License

Proprietary — All rights reserved.
