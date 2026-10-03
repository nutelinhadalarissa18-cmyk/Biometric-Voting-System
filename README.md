# Secure Biometric Voting System Using Fingerprint Authentication

**Subtitle:** A Software-Based One-Time Voting System with Fingerprint Verification and Database  
**Project Category:** Final Year Academic Project Prototype (2026)

> [!IMPORTANT]
> **ACADEMIC PROTOTYPE CONTEXT NOTICE:**  
> This application is built as an academic demonstration system. It features WebAuthn biometric verification, atomic database transaction locks, role-based administration, and audit trails. It is **NOT certified for legally binding government/public elections**.

---

## Key Features

- **WebAuthn Biometric Authenticator Enrollment**: Passkey authentication using platform authenticators (fingerprint, TouchID, Windows Hello, FaceID, device PIN).
- **One-Voter-One-Vote Guarantee**: Enforced at the server & database layer with `UNIQUE(voter_id, election_id)` constraints and atomic database transaction locks.
- **Decoupled Vote Privacy Model**: Voter participation records are decoupled from candidate choices to preserve secret ballot privacy while providing verifiable receipt codes.
- **Role-Based Access Control (RBAC)**: Role permissions for `VOTER`, `ADMIN`, `SUPER_ADMIN`, and `AUDITOR`.
- **Election Lifecycle Control**: State machine transitions (`DRAFT` -> `SCHEDULED` -> `ACTIVE` -> `PAUSED` -> `CLOSED` -> `RESULTS_PUBLISHED`).
- **Immutable Audit Logging & Security Anomaly Detection**: Tracks security events, failed logins, and rate-limit spikes.

---

## Technology Stack

- **Frontend**: React 18, TypeScript, Vite, Tailwind CSS, React Router v6, TanStack Query, Zod.
- **Backend**: Node.js, Express.js, TypeScript, `@simplewebauthn/server`, Bcryptjs, JWT, Helmet, Rate Limiters.
- **Database**: PostgreSQL with Prisma ORM.
- **Testing**: Vitest unit and integration test suite.
- **Deployment**: Docker & Docker Compose configuration.

---

## Project Structure

```
secure-biometric-voting/
├── frontend/             # React + TypeScript + Vite Tailwind App
├── backend/              # Express + TypeScript + WebAuthn API
├── prisma/               # Prisma PostgreSQL schema & migrations
├── tests/                # Unit & Integration test suite
├── docs/                 # Academic report & architecture documentation
│   ├── architecture.md
│   ├── database.md
│   ├── security.md
│   ├── api.md
│   ├── deployment.md
│   ├── user-guide.md
│   ├── admin-guide.md
│   └── academic-report.md
├── docker-compose.yml
├── .env.example
├── .env
└── README.md
```

---

## Quick Start Guide

### 1. Backend Setup
```bash
cd backend
npm install
npm run build
npm start
```

### 2. Frontend Setup
```bash
cd frontend
npm install
npm run dev
```

### 3. Demo Login Credentials
- **Voter Account**: `voter1@voting.local` (Voter ID: `VOTER001`) / Password: `Voter123!`
- **Super Admin Account**: `admin@voting.local` / Password: `SuperAdmin@123`

---

## Testing & Verification

Run automated test suite:
```bash
cd tests
npm test
```
