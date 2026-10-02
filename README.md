# MEGHA × AWS Student Builders

**The digital hub for a student builders community focused on cloud computing, AWS, AI/ML, software engineering, DevOps, and emerging technologies.**

> Built with React, TypeScript, Three.js, and Supabase — engineered as a serious technology community platform, not a template landing page. Built for the community, by the community.

---

## Table of Contents

1. [About the Project](#about-the-project)
2. [Tech Stack](#tech-stack)
3. [Architecture](#architecture)
4. [Project Structure](#project-structure)
5. [Getting Started](#getting-started)
6. [Environment Variables](#environment-variables)
7. [Branching Strategy](#branching-strategy)
8. [Contribution Workflow](#contribution-workflow)
9. [Coding Standards](#coding-standards)
10. [Feature Map](#feature-map)
11. [Roles & Access Levels](#roles--access-levels)
12. [Security Practices](#security-practices)
13. [Implementation Status](#implementation-status)
14. [Roadmap](#roadmap)
15. [Design Principles](#design-principles)
16. [Getting Help](#getting-help)

---

## About the Project

The MEGHA × AWS Student Builders platform brings together everything a student-run tech community needs in one place:

- **Community information** — About, mission, and values
- **Events** — Workshops, hackathons, meetups, and sessions (with registration)
- **Builders** — Public profiles of community members
- **Projects** — Student-built projects and collaborations
- **AWS Hub** — Curated AWS learning, practice, and career resources
- **Learning Resources** — Downloadable, categorized technical resources
- **Opportunities** — Internships, jobs, competitions, and openings
- **Achievements** — Community and individual recognition
- **Journey** — Community timeline and milestones
- **Gallery** — Photos from events, projects, and activities
- **Announcements** — Community news and updates
- **Certificates** — Issued, publicly verifiable certificates
- **Ask MEGHA AI** — An AI assistant for community and technical questions
- **Admin CMS** — Full content management, no code changes required

If you're picking up a ticket, **read the section of this README relevant to it before writing code** — it tells you where things belong and how they're expected to behave.

---

## Tech Stack

### Frontend

| Technology | Purpose |
|---|---|
| React 19 | UI component library |
| Vite 8 | Build tool and dev server |
| TypeScript | Type-safe development |
| Tailwind CSS 4 | Utility-first styling |
| React Router 7 | Client-side routing and navigation |
| Three.js | 3D rendering engine |
| React Three Fiber | React renderer for Three.js |
| @react-three/drei | Three.js helpers and abstractions |

### Backend / Platform

| Technology | Purpose |
|---|---|
| Supabase | Backend-as-a-service |
| PostgreSQL | Relational database |
| Supabase Auth | Authentication and user management |
| Supabase Storage | File and media storage |
| Supabase Edge Functions | Server-side logic and secure API processing |
| Row Level Security (RLS) | Database-level access control |
| Database triggers / functions | Automation, auditing, data integrity |

### AI

| Technology | Purpose |
|---|---|
| Ask MEGHA AI | Community AI assistant |
| OpenRouter | AI model routing and integration |
| Edge Function processing | Server-side AI request handling |
| Admin-managed knowledge | Administrator-curated AI knowledge base |

### Hosting & Deployment

| Layer | Platform |
|---|---|
| Frontend | **Not decided yet** — flag this in an issue if you have a strong opinion |
| Backend services | Supabase (managed cloud infrastructure) |

> **Do not introduce a new library, framework, or service** (state management, CSS framework, DB client, etc.) without opening an issue/discussion first. Keeping the stack small is a deliberate choice so every contributor can reason about the whole codebase.

---

## Architecture

```
┌──────────────────────────────────────────────────────────────────┐
│                         USER (Browser)                           │
└────────────────────────────────┬─────────────────────────────────┘
                                  │
┌────────────────────────────────▼─────────────────────────────────┐
│                    React + Vite Frontend                         │
│                    (TypeScript, Tailwind CSS)                     │
└────────────────────────────────┬─────────────────────────────────┘
                                  │
┌────────────────────────────────▼─────────────────────────────────┐
│                React Router / UI Components                      │
│  ┌──────────┐  ┌──────────┐  ┌───────────┐  ┌────────────────┐   │
│  │  Public  │  │   Auth   │  │  Member   │  │  Admin CMS     │   │
│  │  Pages   │  │  Pages   │  │  Area     │  │  (Protected)   │   │
│  └──────────┘  └──────────┘  └───────────┘  └────────────────┘   │
└────────────────────────────────┬─────────────────────────────────┘
                                  │
┌────────────────────────────────▼─────────────────────────────────┐
│                       Supabase Client                             │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────────┐    │
│  │Authentication│  │ PostgreSQL   │  │    Storage           │    │
│  │ (Auth / MFA) │  │ (RLS)        │  │ (Avatars, Gallery,   │    │
│  │              │  │              │  │  Resources, Certs)   │    │
│  └──────────────┘  └──────────────┘  └──────────────────────┘    │
│  ┌──────────────────────────────────────────────────────────┐    │
│  │                   Edge Functions                         │    │
│  │  ┌─────────────────┐    ┌─────────────────────────────┐  │    │
│  │  │   Ask MEGHA     │    │  Other Server-Side          │  │    │
│  │  │   (AI Logic)    │    │  Operations                 │  │    │
│  │  └────────┬────────┘    └─────────────────────────────┘  │    │
│  └───────────┼──────────────────────────────────────────────┘    │
└──────────────┼───────────────────────────────────────────────────┘
               │
┌──────────────▼──────────────┐
│   External AI Service        │
│   (OpenRouter)                │
└───────────────────────────────┘
```

**Architecture principles:**
- PostgreSQL stores all structured application data.
- Row Level Security (RLS) protects every table — there is no "trust the frontend" access path.
- Supabase Storage manages media and file content, split into public and protected buckets.
- Edge Functions handle anything that needs a secret (AI calls, sensitive processing) — **the frontend must never hold or call third-party AI/API credentials directly.**
- Database triggers support automation and audit logging.
- Authentication (plus MFA for admin actions) gates protected functionality.

---

## Project Structure

> This is the expected/target structure for the codebase. If your branch doesn't match this layout yet, that's a good first contribution — but confirm with a maintainer before doing a large restructuring PR.

```
megha-platform/
├─ src/
│  ├─ pages/                 # Route-level pages (Home, About, Events, Admin/*, ...)
│  ├─ components/
│  │   ├─ ui/                 # Low-level, reusable primitives (Button, Card, Modal, ...)
│  │   ├─ sections/           # Home-page sections (Hero, Announcements, Builders, ...)
│  │   ├─ three/              # React Three Fiber scenes/components for the 3D hero
│  │   └─ admin/              # Admin CMS layout, tables, forms shared across modules
│  ├─ hooks/                  # Shared React hooks (useAuth, useRole, useSupabaseQuery, ...)
│  ├─ lib/
│  │   ├─ supabase.ts          # Supabase client singleton
│  │   └─ utils.ts             # Generic helpers
│  ├─ context/                 # Auth/session context, role context
│  ├─ types/                   # Shared TypeScript types (mirrors DB schema)
│  └─ routes/                  # Route definitions / guards (public, member, admin)
├─ supabase/
│  ├─ migrations/              # Numbered SQL migrations (schema, RLS, triggers)
│  └─ functions/                # Edge Functions (ask-megha, gallery-urls, ...)
├─ public/
├─ docs/                        # Architecture notes, ADRs, this README's long-form backups
├─ .env.example
├─ package.json
└─ README.md
```

**Rules of thumb:**
- A new public-facing section on the Home page → `src/components/sections/`.
- A new Admin CMS module → `src/pages/admin/<module>/` with `list / detail / create / edit` following the existing modules' pattern (see [Coding Standards](#coding-standards)).
- Anything touching the database → a new file under `supabase/migrations/`, never a hand-run SQL command against production.
- Anything that needs a secret (AI keys, etc.) → an Edge Function under `supabase/functions/`, never client-side code.

---

## Getting Started

### Prerequisites
- Node.js 18+
- npm (or pnpm/yarn if the team standardizes on one — check `package.json`'s `packageManager` field first)
- A Supabase project (ask a maintainer for dev-project access, or spin up your own free Supabase project for local development)

### Setup

```bash
git clone <repo-url>
cd megha-platform
git checkout develop        # always branch from develop, see below
npm install
cp .env.example .env.local  # fill in your Supabase project values
npm run dev
```

### Running the backend locally
- Database schema and RLS policies live in `supabase/migrations/`. Apply them to your own Supabase project with the Supabase CLI:
  ```bash
  supabase link --project-ref <your-project-ref>
  supabase db push
  ```
- Edge Functions can be run locally with `supabase functions serve <function-name>` — see each function's folder for its own notes.

---

## Environment Variables

| Variable | Purpose |
|---|---|
| `VITE_SUPABASE_URL` | Your Supabase project URL |
| `VITE_SUPABASE_ANON_KEY` | Public anon key (safe for frontend use — RLS does the real protection) |
| `OPENROUTER_API_KEY` | **Edge Function secret only.** Set via `supabase secrets set`, never in a `VITE_*` variable, never committed |

**Never commit `.env`, `.env.local`, or any file containing real keys.** `.env.example` should only ever contain placeholder values.

---

## Branching Strategy

This project uses a **two-branch trunk model**:

| Branch | Purpose | Who can push directly |
|---|---|---|
| `main` | Always in a **working, deployable** state. This is what gets released/deployed. | **No one** — only via reviewed merge from `develop` |
| `develop` | Integration branch. Reviewed, working contributions land here first. | **No one** — only via reviewed, approved Pull Requests |
| `feature/<short-name>` | One feature or fix per branch, cut from `develop`. | The contributor working on it |

```
main      ──●────────────────●─────────────●──────▶   (releases only)
             \                \             \
develop   ────●───●───●───●───●───●───●───●─●──────▶   (integration)
                  \       \           \
feature/x          ●───●───●           
feature/y              ●───●───●
```

**Flow for every change:**
1. Branch off the latest `develop`: `git checkout develop && git pull && git checkout -b feature/<short-name>`.
2. Commit your work on that feature branch.
3. Open a Pull Request **into `develop`** (not `main`).
4. A maintainer reviews the code. Once approved and checks pass, it's merged into `develop`.
5. `develop` is tested as a whole (manually and/or via CI) to confirm the integrated feature set is stable.
6. Periodically, a maintainer merges `develop` into `main` — this is a **release**, and only happens once everything in `develop` is confirmed working.

**Rules:**
- Never push directly to `main` or `develop`.
- Never open a PR directly against `main` — it always goes through `develop` first.
- Keep feature branches small and focused on one thing — easier to review, easier to revert if something's wrong.
- If your feature depends on another unmerged feature branch, say so explicitly in the PR description.

---

## Contribution Workflow

1. **Find or open an issue** describing what you want to work on before starting — this avoids two people building the same thing, and lets a maintainer flag if it conflicts with planned architecture.
2. **Branch from `develop`** using the naming convention: `feature/<name>`, `fix/<name>`, `chore/<name>`, or `docs/<name>`.
3. **Write the code** following the [Coding Standards](#coding-standards) below and the existing patterns in the module you're touching.
4. **Test locally** — run the app, exercise the feature, and if you touched the database, confirm your RLS policies actually restrict access the way you intend (test as a non-admin user, not just as yourself).
5. **Open a Pull Request into `develop`** with:
   - A clear title and description of what changed and why
   - Linked issue (`Closes #123`)
   - Screenshots/GIFs for any UI change
   - Notes on any new environment variables, migrations, or Edge Functions introduced
6. **Respond to review comments** — a maintainer will review for correctness, security (especially RLS/auth), and consistency with existing patterns.
7. **Once approved**, a maintainer merges it into `develop`. Do not merge your own PR unless explicitly told to.
8. `develop` gets integration-tested; once stable, it's merged into `main` as a release.

**What gets a PR rejected or sent back for changes:**
- Direct writes to the database bypassing Supabase migrations
- New third-party services/libraries added without prior discussion
- Client-side code that calls an AI provider directly (must go through an Edge Function)
- Missing or incorrect RLS policy on a new table
- Hardcoded secrets or `.env` files committed
- UI that doesn't follow the [Design Principles](#design-principles) below (e.g. introduces glassmorphism, neon, random gradient blobs)

---

## Coding Standards

- **TypeScript everywhere** — no new `.jsx`/`.js` files in `src/`; use proper types, avoid `any` unless genuinely unavoidable (and comment why).
- **Follow the existing CMS pattern** for any new Admin module: `list → detail → create/edit`, with search, filtering, and pagination, and soft-delete/archival rather than hard deletes where the data matters (events, projects, members).
- **Components**: small and composable. Shared primitives go in `components/ui/`; page-specific composition stays local to the page/section.
- **Styling**: Tailwind CSS only — no inline style objects except where truly dynamic (e.g. computed positions for the 3D scene or canvas-based rendering).
- **Accessibility is not optional**: semantic HTML, keyboard reachability, visible focus states, labeled form fields, and respect for `prefers-reduced-motion` (especially around the 3D hero and any animation).
- **Server-side secrets stay server-side**: anything needing an API key (OpenRouter, etc.) is an Edge Function, never a frontend call.
- **Database changes are migrations**: every schema or policy change is a new numbered file in `supabase/migrations/`, reviewed like code, never applied by hand to the shared project.
- **Commit messages**: short, imperative, and specific — e.g. `fix: correct RLS policy on gallery table`, `feat: add opportunities CMS detail view`.

---

## Feature Map

| Module | Purpose | User Type | Status |
|---|---|---|---|
| Home Page (Hero, Sections) | Landing experience with all major content areas | Public | ✅ Complete |
| 3D Hero Visualization | Immersive cloud infrastructure 3D scene | Public | ✅ Complete |
| About | Community identity and mission | Public | ✅ Complete |
| Community Statistics | Live community metrics | Public | ✅ Complete |
| Events (Public) | Browse and explore events | Public | ✅ Complete |
| Builders (Public) | Community member profiles | Public | ✅ Complete |
| Projects (Public) | Community project showcase | Public | ✅ Complete |
| AWS Hub (Public) | AWS learning resources | Public | ✅ Complete |
| Resources (Public) | Learning materials | Public | ✅ Complete |
| Opportunities (Public) | Jobs, internships, competitions | Public | ✅ Complete |
| Achievements (Public) | Community accomplishments | Public | ✅ Complete |
| Journey (Public) | Community timeline | Public | ✅ Complete |
| Gallery (Public) | Community photos and media | Public | ✅ Complete |
| Announcements (Public) | Community news and updates | Public | ✅ Complete |
| Certificate Verification | Verify issued certificates | Public | ✅ Complete |
| Ask MEGHA AI | AI assistant for questions | Public | ✅ Complete |
| Authentication | Login, password recovery, MFA | Member | ✅ Complete |
| Admin Dashboard | Platform overview and metrics | Admin | ✅ Complete |
| Events / Projects / Members / Resources / Opportunities / Achievements / Journey / Gallery / Announcements / AWS Hub / Certificates / AI Knowledge CMS | Full content management for each domain | Admin | ✅ Complete |
| Audit Logs | Administrative action history | Admin | ✅ Complete |
| Site Settings | Platform configuration | Admin | ⬜ Placeholder |
| Dedicated Public Pages | Standalone pages (About, Events, etc.) beyond Home sections | Public | ⬜ Pending |
| Member Area | Authenticated member dashboard | Member | ⬜ Pending |
| Non-Member Area | Authenticated non-member experience | Member | ⬜ Pending |
| Footer | Site-wide footer | Public | ⬜ Pending |
| Contact Page | Public contact form | Public | ⬜ Pending |

> See [Roadmap](#roadmap) for the prioritized list of what's open for contribution right now.

---

## Roles & Access Levels

| Role | Can do |
|---|---|
| **Visitor** | Browse all public content, use public features (certificate verification, Ask MEGHA AI). No login required. |
| **Member** | Everything a Visitor can, plus authenticated/member-specific functionality and content visibility. |
| **CO_ADMIN** | Authorized access to content management modules. Cannot access audit logs or site settings. Cannot modify roles/permissions. Requires auth + MFA. |
| **ADMIN** | Full platform management: all CMS modules, audit logs, site settings. Requires auth + MFA. |

Permissions are enforced **both** at the frontend (route guards/UX) and the backend (PostgreSQL RLS policies) — a frontend-only check is not considered secure and will be rejected in review.

---

## Security Practices

| Layer | What it does |
|---|---|
| Authentication | Email-based auth via Supabase Auth |
| Role-based authorization | Visitor / Member / CO_ADMIN / ADMIN, each with distinct permissions |
| MFA (AAL2 enforcement) | Required for all administrative operations |
| Row Level Security (RLS) | Database-level access control on every table |
| Private storage buckets | Protected storage for sensitive files (certificate PDFs, etc.) |
| Controlled public verification | Certificate verification exposes only recipient name, program, issue date, and status — nothing else |
| Audit logging | Administrative actions are recorded for accountability |
| Protected admin APIs | Server-side enforcement, not just UI hiding |
| Server-side AI processing | AI credentials/logic live only in Edge Functions |
| Rate limiting | Applied to AI requests to prevent abuse |
| Input validation | Both form-level and database-level |
| Controlled file uploads | Storage policies restrict upload types and access |

If a change you're making touches any row of this table, flag it explicitly in your PR description so review gives it extra attention.

---

## Implementation Status

### Frontend Foundation
Vite + React + TypeScript setup, design system, Tailwind config, responsive nav, 3D Hero (lazy-loaded, code-split), and routing are all **complete**.

### Home Page Sections
Hero/3D, Announcements, About, Community Statistics, Events, Builders, Projects, AWS Hub, Resources, Opportunities, Achievements, Gallery — all **complete**.
Not yet added to the Home page: **Journey section, Ask MEGHA CTA, Join MEGHA CTA, Footer.**

### Backend (Supabase)
Schema (24 migrations), profiles/roles, core + relationship + extended content tables, admin/audit tables, RLS policies, storage buckets, indexes, MFA/AAL2 enforcement, certificate verification RPC, Ask MEGHA schema + baseline knowledge, and the Ask MEGHA / Gallery URL Edge Functions are all **complete**.

### Authentication
Login, forgot/reset password, MFA enrollment + verification, auth context/session management, and protected routes with role + MFA checks are all **complete**.

### Admin CMS
Every module (Dashboard, Events, Projects, Members, Resources, Opportunities, Achievements, Journey, Gallery, Announcements, AWS Hub, Certificates, AI Knowledge, Audit Logs) is **complete**. **Site Settings remains a placeholder.**

### Public Features
Builders, community stats, announcements with detail pages, certificate verification, Ask MEGHA AI (with rate limiting and live certificate verification), gallery, AWS Hub, achievements, opportunities, resources, and journey are all **complete**.

---

## Roadmap

These are the open areas — good first places to pick up a contribution:

| Area | Details |
|---|---|
| Home page: Journey section | Compose the existing Journey content into the Home page |
| Home page: Ask MEGHA CTA | Add a call-to-action section linking to Ask MEGHA |
| Home page: Join MEGHA CTA | Add a call-to-action section for joining the community |
| Footer | Site-wide footer — not yet implemented anywhere |
| Dedicated public pages | Standalone pages for About, Events, Builders, Projects, etc. (currently Home-page sections only) |
| Contact page | Public contact form |
| Member area | Authenticated member dashboard and features |
| Non-member area | Authenticated non-member experience |
| Site Settings CMS | Currently a placeholder — needs real platform configuration UI |
| Security audit | Final production security review |
| Accessibility / performance audit | Final pass before production launch |
| Production QA | End-to-end testing |
| Production deployment config | Finalize hosting choice + Supabase production setup |

If you want to work on one of these, comment on (or open) the matching issue before starting so work doesn't get duplicated.

---

## Design Principles

The platform uses a **cinematic technology aesthetic** — dark/deep navy foundation, electric blue/cyan as the primary accent, white/off-white type for readability, and AWS orange reserved specifically for AWS-related elements. The 3D Hero (React Three Fiber) represents cloud infrastructure nodes, network topology, and data flow — it exists to communicate the community's actual focus, not as decoration.

**Deliberately avoided**, and grounds for requesting changes in review:
- Generic SaaS appearance
- Excessive glassmorphism
- Excessive neon effects
- Crypto / cyberpunk aesthetics
- Unnecessary animation
- Cluttered interfaces
- Template-like layouts
- Random gradient blobs

If you're adding UI, it should look like it belongs to an engineering-focused, community-driven identity — not a generic startup landing page.

---

## Getting Help

- **Unsure where something belongs?** Ask in the project's contributor channel before opening a PR — it's faster than a review round-trip.
- **Found a security issue** (auth bypass, RLS gap, exposed secret)? Report it privately to a maintainer, not as a public issue.
- **Not sure if your idea fits the roadmap?** Open a discussion/issue first — this keeps `develop` from accumulating half-finished, conflicting directions.

---

*This README is a living document. If you notice it's out of date with what's actually in the codebase, fixing it is a welcome first contribution — open a `docs/` branch and update it.*
