# Acme Dashboard

A full-stack dashboard application built with Next.js App Router. Manages invoices and customers with authentication, search, pagination, and real-time data from PostgreSQL.

## Tech Stack

- **Framework:** Next.js (App Router) + TypeScript
- **Styling:** Tailwind CSS
- **Database:** PostgreSQL (`postgres`)
- **Auth:** NextAuth v5
- **Validation:** Zod
- **Package Manager:** pnpm

## Getting Started

### Prerequisites

- Node.js 18+
- pnpm (`npm i -g pnpm`)
- PostgreSQL database

### Install

```bash
pnpm install
pnpm approve-builds  # approve bcrypt + sharp native builds
```

### Environment Variables

Create a `.env.local` file:

```env
POSTGRES_URL=
POSTGRES_USER=
POSTGRES_HOST=
POSTGRES_PASSWORD=
POSTGRES_DATABASE=

AUTH_SECRET=        # openssl rand -base64 32
AUTH_URL=http://localhost:3000/api/auth
```

### Seed the Database

Start the dev server, then visit:

```
http://localhost:3000/api/seed
```

This creates and populates the `users`, `customers`, `invoices`, and `revenue` tables.

### Run

```bash
pnpm dev      # development (Turbopack)
pnpm build    # production build
pnpm start    # production server
```

## Routes

| Route | Description |
|-------|-------------|
| `/` | Landing page |
| `/login` | Authentication |
| `/dashboard` | Overview with revenue chart and latest invoices |
| `/dashboard/invoices` | Invoice list with search, filter, and pagination |
| `/dashboard/customers` | Customer list with invoice statistics |
| `/api/seed` | Database seed endpoint |

## Scripts

```bash
pnpm lint           # ESLint
pnpm format         # Prettier (write)
pnpm format:check   # Prettier (check only)
```

## Project Structure

```
app/
├── dashboard/
│   ├── customers/    # Customer management
│   ├── invoices/     # Invoice management
│   └── page.tsx      # Dashboard overview
├── lib/
│   ├── data.ts           # Database queries
│   ├── definitions.ts    # TypeScript types
│   └── utils.ts          # Formatting helpers
├── ui/
│   ├── dashboard/    # Dashboard components
│   ├── invoices/     # Invoice forms & tables
│   └── customers/    # Customer table
├── seed/             # Seed API route
└── layout.tsx        # Root layout
```
