# MEGHA × AWS Student Builders — Website & Platform Plan

This document describes the complete architecture, feature set, and current implementation status of the **MEGHA × AWS Student Builders** website and platform.

It is intended as a public project overview suitable for sharing with club members, students, faculty, technical contributors, event participants, and future developers.

---

## 1. Platform Overview

The MEGHA × AWS Student Builders platform is a modern technology community website designed to serve as the digital hub for a student builders group focused on cloud computing, AWS, AI/ML, software engineering, DevOps, and emerging technologies.

The platform brings together:

- **Community information** — About, mission, and values
- **Events** — Workshops, hackathons, meetups, and sessions
- **Builders** — Public profiles of community members
- **Projects** — Student-built projects and collaborations
- **AWS Hub** — Curated AWS learning, practice, and career resources
- **Learning resources** — Downloadable and categorized technical resources
- **Opportunities** — Internships, jobs, competitions, and other openings
- **Achievements** — Community and individual recognition
- **Community journey** — Timeline and milestones
- **Gallery** — Community images from events, projects, and activities
- **Announcements** — Community news and updates
- **Certificates** — Issued and publicly verifiable certificates
- **Ask MEGHA AI** — AI assistant for community and technical questions
- **Administrative management** — Full CMS for platform content

---

## 2. Technology Stack

### Frontend

| Technology | Purpose |
|---|---|
| **React 19** | UI component library |
| **Vite 8** | Build tool and dev server |
| **TypeScript** | Type-safe development |
| **Tailwind CSS 4** | Utility-first styling |
| **React Router 7** | Client-side routing and navigation |
| **Three.js** | 3D rendering engine |
| **React Three Fiber** | React renderer for Three.js |
| **@react-three/drei** | Three.js helpers and abstractions |

### Backend / Platform

| Technology | Purpose |
|---|---|
| **Supabase** | Backend-as-a-service platform |
| **PostgreSQL** | Relational database |
| **Supabase Auth** | Authentication and user management |
| **Supabase Storage** | File and media storage |
| **Supabase Edge Functions** | Server-side logic and secure API processing |
| **Row Level Security (RLS)** | Database-level access control |
| **Database triggers / functions** | Automation, auditing, and data integrity |

### AI

| Technology | Purpose |
|---|---|
| **Ask MEGHA AI** | Community AI assistant |
| **OpenRouter** | AI model routing and integration |
| **Edge Function processing** | Server-side AI request handling |
| **Admin-managed knowledge** | Administrator-curated AI knowledge base |

### Hosting & Deployment

| Layer | Platform |
|---|---|
| **Frontend** | Not decided yet |
| **Backend services** | Supabase (managed cloud infrastructure) |

---

## 3. Website Structure

The website provides the following public navigation and pages:

| Page | Purpose |
|---|---|
| **Home** | Main landing page with all major sections |
| **About** | Community mission, values, and identity |
| **Events** | Browse upcoming and past community events |
| **Builders** | Public profiles of community members |
| **Projects** | Browse community projects |
| **AWS Hub** | Curated AWS learning and career resources |
| **Resources** | Downloadable learning materials and references |
| **Opportunities** | Internships, jobs, competitions, and openings |
| **Achievements** | Community and individual accomplishments |
| **Journey** | Community timeline and milestones |
| **Gallery** | Community images and event photos |
| **Announcements** | Community news, updates, and notices |
| **Ask MEGHA** | AI assistant for community and technical questions |
| **Join MEGHA** | Call-to-action for joining the community |
| **Contact** | Reach the community team |
| **Login** | Authentication for members and administrators |
| **Certificate Verification** | Public verification of issued certificates |

---

## 4. Home Page

The Home page is a single-page experience composed of the following major sections:

| # | Section | Description |
|---|---|---|
| 1 | **Hero / 3D Experience** | Full-screen immersive hero with 3D cloud infrastructure visualization, community identity, tagline, and primary CTAs |
| 2 | **Announcements** | Latest community announcements with priority-aware display |
| 3 | **About MEGHA × AWS** | Community overview, mission, and focus areas |
| 4 | **Community Statistics** | Live counters for members, events, projects, and other community metrics |
| 5 | **Featured Events** | Highlighted upcoming and recent events |
| 6 | **Builders** | Featured community members with public profiles |
| 7 | **Featured Projects** | Showcase of community-built projects |
| 8 | **AWS Hub** | Curated AWS learning and career resources |
| 9 | **Resources** | Learning materials and downloadable content |
| 10 | **Opportunities** | Current internships, jobs, and competitions |
| 11 | **Achievements** | Community and member accomplishments |
| 12 | **Gallery** | Community images from events and activities |

**Planned sections** (not yet on the Home page):
- Journey (community timeline)
- Ask MEGHA CTA
- Join MEGHA CTA
- Footer

---

## 5. Design System

### Visual Direction

The platform uses a **cinematic technology aesthetic** that communicates engineering seriousness and community identity.

| Element | Direction |
|---|---|
| **Foundation** | Dark / deep navy background |
| **Primary accent** | Electric blue / cyan |
| **Typography** | White / off-white for readability |
| **AWS contexts** | AWS orange used appropriately for AWS-related elements |
| **Identity** | Engineering-focused, community-driven |
| **Layout** | Responsive / mobile-first design |
| **Accessibility** | Accessible layouts with reduced-motion considerations |
| **Atmosphere** | Professional technology community |

### 3D Visualization

The Hero section features a **3D cloud infrastructure visualization** built with React Three Fiber, representing:

- Cloud infrastructure nodes
- Network topology connections
- Data flow animations
- Computing endpoints

This visualization communicates the community's focus on cloud and infrastructure technology.

### Design Avoidances

The design deliberately avoids:

- ❌ Generic SaaS appearance
- ❌ Excessive glassmorphism
- ❌ Excessive neon effects
- ❌ Crypto / cyberpunk aesthetics
- ❌ Unnecessary animations
- ❌ Cluttered interfaces
- ❌ Template-like layouts
- ❌ Random gradient blobs

---

## 6. Public Features

### Events

- Browse upcoming and past community events
- View event details (description, date, time, location, type)
- Event registration with capacity awareness
- Event status indicators (upcoming, ongoing, completed, cancelled)

### Builders

- Public member profiles with roles and titles
- Skills and domain expertise
- Professional links (GitHub, LinkedIn, portfolio) where available
- Featured builders showcase on the Home page

### Projects

- Browse community projects
- Project details with descriptions and problem statements
- Project status tracking
- Technologies, domains, and AWS services used
- Project team members and roles

### AWS Hub

- AWS learning resources (courses, tutorials, documentation)
- Practice resources (labs, sandboxes)
- Career resources (certifications, career paths)
- Community resources (events, groups)
- Featured and categorized resources

### Resources

- Learning resources and downloadable materials
- Categorized by topic and type
- Resource metadata and descriptions

### Opportunities

- Internships, jobs, competitions, and other openings
- Location and work mode information
- External links to application portals
- Status tracking (open, closed, expired)

### Achievements

- Community achievements and milestones
- Individual member recognition
- Achievement categories and descriptions

### Journey

- Community timeline with milestones
- Published journey entries and historical events

### Gallery

- Community images from events, projects, and activities
- Event and project associations
- Categories and published gallery content

### Announcements

- Community announcements with priority levels
- Detailed announcement pages
- Publishing and expiry-aware visibility
- Direct links to individual announcements

### Certificate Verification

- Public certificate verification by certificate number
- Verification statuses: **VALID**, **REVOKED**, or **NOT FOUND**
- Displays: recipient name, program, and issue date
- Privacy-conscious verification (shows only necessary information)

### Ask MEGHA AI

- Interactive AI assistant
- MEGHA-specific questions (community, events, projects, members)
- General technical questions (AWS, cloud, programming)
- Certificate verification assistance
- Rate-limited requests for responsible usage

---

## 7. Ask MEGHA AI

The Ask MEGHA AI system provides an intelligent assistant for the community.

### How It Works

- Users interact with the AI through a dedicated page
- The AI can answer MEGHA-specific questions using administrator-managed knowledge
- It can answer general technical questions about AWS, cloud computing, and related topics
- Certificate verification is supported through approved live verification functionality
- AI processing is handled entirely server-side via Supabase Edge Functions

### Knowledge Management

- Administrators maintain the knowledge base used by the AI
- Published knowledge entries are available for MEGHA-specific responses
- The AI is designed not to expose private or internal community information

### Safety & Limits

- All AI requests are rate-limited
- Server-side processing ensures sensitive credentials are never exposed to the client
- Responses are contextually grounded in approved knowledge

---

## 8. Certificate System

The certificate system provides verifiable recognition for community members.

### Certificate Lifecycle

1. **Issuance** — Authorized administrators create certificate records with recipient, program, and issue date
2. **Unique identification** — Each certificate receives a unique certificate number
3. **PDF management** — Certificate PDFs can be uploaded and managed
4. **Public verification** — Anyone can verify a certificate using its certificate number

### Verification Statuses

| Status | Meaning |
|---|---|
| ✅ **VALID** | Certificate is authentic and current |
| 🔴 **REVOKED** | Certificate has been revoked by an administrator |
| ⚪ **NOT FOUND** | No certificate exists with the provided number |

### Privacy

Public verification is designed to expose only the information necessary for verification:
- Recipient name
- Program name
- Issue date
- Verification status

No additional private information is disclosed through the verification endpoint.

---

## 9. Authentication & Member Experience

### Authentication

- Email-based login with Supabase Auth
- Password recovery via forgot password / reset password flow
- Multi-Factor Authentication (MFA) enrollment and verification
- Secure session management

### Member Experience

- Authenticated users access member-specific functionality
- Role-aware content and features
- Protected routes and areas
- Secure account management

### Access Levels

- **Public content** — Accessible to all visitors without login
- **Member content** — Requires authentication
- **Administrative content** — Requires authentication, authorized role, and MFA verification

---

## 10. Admin Platform

The Admin CMS is a complete content management platform that allows administrators to manage all platform content without editing frontend source code.

### Admin Modules

| Module | Description |
|---|---|
| **Dashboard** | Platform overview with key metrics and statistics |
| **Events** | Create, edit, manage events; track registrations and attendance |
| **Projects** | Manage project listings, members, tags, and metadata |
| **Members** | Edit member profiles, visibility, status, and avatars |
| **Resources** | Manage learning resources and downloadable content |
| **Opportunities** | Manage internships, jobs, competitions |
| **Achievements** | Manage community and member achievements |
| **Journey** | Manage community timeline and milestones |
| **Gallery** | Manage community images and media |
| **Announcements** | Create and manage community announcements |
| **AWS Hub** | Manage AWS learning and career resources |
| **Certificates** | Issue, manage, revoke, and delete certificates |
| **AI Knowledge** | Create and manage AI knowledge base entries |
| **Audit Logs** | View administrative action history (ADMIN only) |
| **Site Settings** | Platform configuration (ADMIN only) |

### CMS Design Principles

- All CMS modules follow a consistent list → detail → edit pattern
- Search, filtering, and pagination across all content types
- Safe deletion patterns (soft-delete / archival where appropriate)
- Real-time data from the database
- Form validation and error handling

---


## 12. Security Features

The platform implements multiple layers of security:

| Security Layer | Description |
|---|---|
| **Authentication** | Email-based authentication via Supabase Auth |
| **Role-based authorization** | Visitors, Members, Co-Admins, and Admins with distinct permissions |
| **Multi-Factor Authentication (MFA)** | Required for administrative operations (AAL2 enforcement) |
| **Row Level Security (RLS)** | Database-level access control on all tables |
| **Private storage** | Protected storage buckets for sensitive files |
| **Controlled public verification** | Certificate verification exposes only necessary information |
| **Audit logging** | Administrative actions are recorded for accountability |
| **Protected administrative APIs** | Server-side enforcement of administrative permissions |
| **Server-side AI processing** | AI credentials and logic processed on the server, never in the browser |
| **Rate limiting** | AI requests are rate-limited to prevent abuse |
| **Input validation** | Form-level and database-level validation |
| **Controlled file uploads** | Storage policies restrict upload types and access |
| **Public / administrative separation** | Clear separation between public-facing and administrative data |

---

## 13. Data Management

The platform manages the following major information domains:

| Domain | Description |
|---|---|
| **Profiles** | User identity and authentication profiles |
| **Members** | Community membership, roles, and public profiles |
| **Events** | Event details, schedules, and metadata |
| **Registrations** | Event registration records and attendance tracking |
| **Projects** | Project details, descriptions, and status |
| **Project relationships** | Project member assignments and tag associations |
| **Resources** | Learning materials and downloadable content |
| **AWS Hub resources** | Curated AWS-specific learning resources |
| **Opportunities** | External opportunities (jobs, internships, competitions) |
| **Achievements** | Community and individual accomplishments |
| **Journey** | Community timeline entries and milestones |
| **Gallery** | Community images and media content |
| **Announcements** | Community news and updates |
| **Certificates** | Certificate records, PDFs, and verification data |
| **AI Knowledge** | Administrator-managed knowledge base for Ask MEGHA |
| **Audit information** | Administrative action logs |
| **Site configuration** | Platform settings and preferences |

---

## 14. Role Structure

### Visitor

- Can browse all public content
- Can use public features (certificate verification, Ask MEGHA AI)
- No authentication required

### Member / Authenticated User

- Can access authenticated and member-specific functionality
- Additional features and content visibility based on permissions

### ADMIN

- Full platform management access
- All CMS modules available
- Audit log access
- Site settings management
- Protected by authentication and MFA

### CO_ADMIN

- Authorized administrative access to content management modules
- Cannot access audit logs or site settings
- Cannot modify administrative roles or permissions
- Protected by authentication and MFA

Administrative permissions are enforced at both the frontend (UX routing) and backend (database RLS policies) levels.

---

## 15. Storage & Media

The platform manages several categories of media and files:

| Content Type | Description |
|---|---|
| **Profile avatars** | Member profile images |
| **Gallery media** | Community event and activity photos |
| **Resource files** | Downloadable learning materials |
| **Certificate PDFs** | Issued certificate documents |

- **Public content** is accessible without authentication
- **Protected content** requires appropriate authorization
- Storage access is controlled through Supabase Storage policies
- File uploads are restricted by type and access level

---

## 16. Database / Backend Architecture

```
┌─────────────────────────┐
│     User (Browser)      │
└────────────┬────────────┘
             │
┌────────────▼────────────┐
│  React + Vite Frontend  │
│  (need to confirm)         │
└────────────┬────────────┘
             │
┌────────────▼────────────┐
│    Supabase Client      │
└────────────┬────────────┘
             │
     ┌───────┼───────┬──────────┐
     │       │       │          │
┌────▼───┐ ┌─▼──┐ ┌──▼───┐ ┌───▼──────────┐
│Supabase│ │Post│ │Supa- │ │  Supabase    │
│  Auth  │ │gre-│ │base  │ │  Edge        │
│        │ │SQL │ │Stor- │ │  Functions   │
│        │ │    │ │age   │ │              │
└────────┘ └────┘ └──────┘ └───┬──────────┘
                               │
                       ┌───────▼────────┐
                       │  External AI   │
                       │  Service       │
                       │  (OpenRouter)  │
                       └────────────────┘
```

### Architecture Principles

- **PostgreSQL** stores all structured application data
- **Row Level Security (RLS)** protects database access at every table
- **Supabase Storage** manages media and file content
- **Edge Functions** handle server-side operations (AI, secure processing)
- **Database triggers** support automation and audit logging
- **Authentication** controls access to protected functionality
- The frontend never directly handles sensitive server-side credentials

---

## 17. Responsive Experience

The platform is designed for responsive use across all device categories:

| Device | Considerations |
|---|---|
| **Desktop** | Full-width layouts, sidebar navigation in admin, multi-column grids |
| **Laptop** | Optimized for standard laptop viewports |
| **Tablet** | Adapted layouts with touch-friendly spacing |
| **Mobile** | Single-column layouts, collapsible navigation, touch-optimized interactions |

### Responsive Features

- Responsive navigation with mobile hamburger menu
- Mobile-friendly card layouts and data tables
- Touch-friendly interactive elements
- Readable typography at all viewport sizes
- Responsive 3D experience (adapts to device capabilities)
- Accessible and usable forms on all screen sizes

---

## 18. Accessibility & UX

The platform incorporates the following accessibility and user experience practices:

| Practice | Implementation |
|---|---|
| **Semantic HTML** | Appropriate use of HTML5 semantic elements |
| **Keyboard accessibility** | Interactive elements reachable and operable via keyboard |
| **Visible focus states** | Clear focus indicators for keyboard navigation |
| **Accessible forms** | Labels, validation messages, and logical form structure |
| **Loading states** | Visual feedback during data loading |
| **Empty states** | Meaningful messages when no data is available |
| **Error states** | Clear error feedback and recovery guidance |
| **Confirmation flows** | Confirmation dialogs for destructive actions (delete, revoke) |
| **Reduced-motion** | Respects `prefers-reduced-motion` for animations and 3D |

---

## 19. Current Implementation Status

### Frontend Foundation

| Area | Status |
|---|---|
| Vite + React + TypeScript setup | ✅ Complete |
| Design system (colors, typography, components) | ✅ Complete |
| Tailwind CSS configuration | ✅ Complete |
| Responsive navigation with mobile menu | ✅ Complete |
| 3D Hero (React Three Fiber, lazy-loaded, code-split) | ✅ Complete |
| Routing (React Router) | ✅ Complete |

### Home Page Sections

| Section | Status |
|---|---|
| Hero / 3D Experience | ✅ Complete |
| Announcements | ✅ Complete |
| About | ✅ Complete |
| Community Statistics (live from database) | ✅ Complete |
| Events | ✅ Complete |
| Builders | ✅ Complete |
| Projects | ✅ Complete |
| AWS Hub | ✅ Complete |
| Resources | ✅ Complete |
| Opportunities | ✅ Complete |
| Achievements | ✅ Complete |
| Gallery | ✅ Complete |
| Journey (Home section) | ⬜ Not yet added to Home page |
| Ask MEGHA CTA (Home section) | ⬜ Not yet added to Home page |
| Join MEGHA CTA (Home section) | ⬜ Not yet added to Home page |
| Footer | ⬜ Not yet implemented |

### Backend (Supabase)

| Area | Status |
|---|---|
| Supabase architecture design | ✅ Complete |
| PostgreSQL database schema (24 migrations) | ✅ Complete |
| Extensions and types | ✅ Complete |
| Profiles and roles | ✅ Complete |
| Core content tables | ✅ Complete |
| Relationship tables | ✅ Complete |
| Extended content tables | ✅ Complete |
| Admin and audit tables | ✅ Complete |
| Row Level Security policies | ✅ Complete |
| Storage buckets and policies | ✅ Complete |
| Database indexes | ✅ Complete |
| MFA / AAL2 enforcement | ✅ Complete |
| Certificate verification RPC | ✅ Complete |
| Ask MEGHA AI schema and baseline knowledge | ✅ Complete |
| Edge Functions (Ask MEGHA, Gallery URLs) | ✅ Complete |

### Authentication

| Area | Status |
|---|---|
| Login page | ✅ Complete |
| Forgot password | ✅ Complete |
| Reset password | ✅ Complete |
| MFA enrollment | ✅ Complete |
| MFA verification | ✅ Complete |
| Auth context and session management | ✅ Complete |
| Protected routes with role and MFA checks | ✅ Complete |

### Admin CMS

| Module | Status |
|---|---|
| Admin shell (sidebar, header, layout) | ✅ Complete |
| Dashboard (statistics and overview) | ✅ Complete |
| Events CMS (list, detail, create, edit, soft-delete, registrations) | ✅ Complete |
| Projects CMS (list, detail, create, edit, members, tags, archival) | ✅ Complete |
| Members CMS (list, detail, edit, avatar upload, visibility) | ✅ Complete |
| Resources CMS (list, detail, create, edit) | ✅ Complete |
| Opportunities CMS (list, detail, create, edit) | ✅ Complete |
| Achievements CMS (list, detail, create, edit) | ✅ Complete |
| Journey CMS (list, detail, create, edit) | ✅ Complete |
| Gallery CMS (list, detail, create, edit) | ✅ Complete |
| Announcements CMS (list, detail, create, edit) | ✅ Complete |
| AWS Hub CMS (list, detail, create, edit) | ✅ Complete |
| Certificates CMS (list, detail, issue, revoke, delete) | ✅ Complete |
| AI Knowledge CMS (list, detail, create, edit, publish) | ✅ Complete |
| Audit Logs (admin-only viewing) | ✅ Complete |
| Site Settings | ⬜ Placeholder (not yet implemented) |

### Public Features

| Feature | Status |
|---|---|
| Public builders profiles | ✅ Complete |
| Public community statistics | ✅ Complete |
| Public announcements with detail pages | ✅ Complete |
| Public certificate verification | ✅ Complete |
| Ask MEGHA AI (page and Edge Function) | ✅ Complete |
| AI rate limiting | ✅ Complete |
| Live certificate verification via AI | ✅ Complete |
| Public gallery with storage URLs | ✅ Complete |
| Public AWS Hub resources | ✅ Complete |
| Public achievements | ✅ Complete |
| Public opportunities | ✅ Complete |
| Public resources | ✅ Complete |
| Public journey | ✅ Complete |

---

## 20. Future / Remaining Work

The following areas are not yet complete based on current repository inspection:

| Area | Details |
|---|---|
| **Home page: Journey section** | Journey section not yet composed into the Home page |
| **Home page: Ask MEGHA CTA** | Ask MEGHA call-to-action not yet on the Home page |
| **Home page: Join MEGHA CTA** | Join CTA section not yet on the Home page |
| **Footer** | Site-wide footer not yet implemented |
| **Dedicated public pages** | Standalone public pages for About, Events, Builders, Projects, etc. (currently sections on the Home page only) |
| **Contact page** | Public contact page not yet implemented |
| **Non-member area** | Authenticated non-member dashboard not yet built |
| **Member area** | Authenticated member dashboard and features not yet built |
| **Site Settings CMS** | Admin settings module is a placeholder |
| **Production security audit** | Final security review for production deployment |
| **Accessibility / performance audit** | Final audit before production launch |
| **Production QA** | End-to-end quality assurance testing |
| **Production deployment configuration** | Final GitHub Pages and Supabase production setup |

---

## 21. User Journeys

### Visitor

```
Home → Explore Sections → Events / Projects / Builders / Resources
     → Ask MEGHA → Get AI Assistance
     → Join MEGHA → Apply to the Community
```

### Event Participant

```
Events Section → Event Details → Register → Confirmation
```

### Certificate Holder

```
Certificate Number → Verify Certificate Page → Verification Result
  → VALID: Recipient, Program, Issue Date
  → REVOKED: Certificate has been revoked
  → NOT FOUND: No matching certificate
```

### Member

```
Login → Authenticated Experience → Community Content and Features
```

### Administrator

```
Login → MFA Verification → Admin Dashboard → Manage Content via CMS
```

### AI User

```
Ask MEGHA Page → Type Question → Receive AI Response
```

### AI Knowledge Administrator

```
Admin → AI Knowledge → Create/Edit Entry → Publish
  → Published knowledge becomes available to Ask MEGHA responses
```

---

## 22. Project Architecture Diagram

```
┌──────────────────────────────────────────────────────────────────┐
│                         USER (Browser)                          │
└────────────────────────────────┬─────────────────────────────────┘
                                 │
┌────────────────────────────────▼─────────────────────────────────┐
│                    React + Vite Frontend                         │
│                    (TypeScript, Tailwind CSS)                    │
│                                            │
└────────────────────────────────┬─────────────────────────────────┘
                                 │
┌────────────────────────────────▼─────────────────────────────────┐
│                React Router / UI Components                      │
│                                                                  │
│  ┌──────────┐  ┌──────────┐  ┌───────────┐  ┌────────────────┐  │
│  │  Public   │  │  Auth    │  │  Member   │  │  Admin CMS     │  │
│  │  Pages    │  │  Pages   │  │  Area     │  │  (Protected)   │  │
│  └──────────┘  └──────────┘  └───────────┘  └────────────────┘  │
└────────────────────────────────┬─────────────────────────────────┘
                                 │
┌────────────────────────────────▼─────────────────────────────────┐
│                       Supabase Client                            │
│                                                                  │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────────┐   │
│  │Authentication│  │ PostgreSQL   │  │    Storage            │   │
│  │ (Auth/MFA)   │  │ (RLS)        │  │ (Avatars, Gallery,   │   │
│  │              │  │              │  │  Resources, Certs)   │   │
│  └──────────────┘  └──────────────┘  └──────────────────────┘   │
│                                                                  │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │                   Edge Functions                         │   │
│  │  ┌─────────────────┐    ┌─────────────────────────────┐  │   │
│  │  │   Ask MEGHA     │    │  Other Server-Side           │  │   │
│  │  │   (AI Logic)    │    │  Operations                  │  │   │
│  │  └────────┬────────┘    └─────────────────────────────┘  │   │
│  └───────────┼──────────────────────────────────────────────┘   │
└──────────────┼──────────────────────────────────────────────────┘
               │
┌──────────────▼──────────────┐
│   External AI Service       │
│   (OpenRouter)              │
└─────────────────────────────┘
```

---

## 23. Feature Summary Table

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
| Events CMS | Event management and registrations | Admin | ✅ Complete |
| Projects CMS | Project management with members and tags | Admin | ✅ Complete |
| Members CMS | Member profile management and avatars | Admin | ✅ Complete |
| Resources CMS | Resource management | Admin | ✅ Complete |
| Opportunities CMS | Opportunity management | Admin | ✅ Complete |
| Achievements CMS | Achievement management | Admin | ✅ Complete |
| Journey CMS | Timeline management | Admin | ✅ Complete |
| Gallery CMS | Gallery and media management | Admin | ✅ Complete |
| Announcements CMS | Announcement management | Admin | ✅ Complete |
| AWS Hub CMS | AWS resource management | Admin | ✅ Complete |
| Certificates CMS | Certificate issuance and management | Admin | ✅ Complete |
| AI Knowledge CMS | AI knowledge base management | Admin | ✅ Complete |
| Audit Logs | Administrative action history | Admin | ✅ Complete |
| Site Settings | Platform configuration | Admin | ⬜ Placeholder |
| Dedicated Public Pages | Standalone pages (About, Events, etc.) | Public | ⬜ Pending |
| Member Area | Authenticated member dashboard | Member | ⬜ Pending |
| Non-Member Area | Authenticated non-member experience | Member | ⬜ Pending |
| Footer | Site-wide footer | Public | ⬜ Pending |
| Contact Page | Public contact form | Public | ⬜ Pending |

---

## 24. Public Project Description

**MEGHA × AWS Student Builders** is a comprehensive technology community platform designed to serve as the digital hub for student builders focused on cloud computing, AWS, artificial intelligence, software engineering, and emerging technologies.

The platform provides:

- 🎓 **Learning** — Curated AWS resources, learning materials, and a community knowledge base
- 🔧 **Building** — Project showcases, technical collaboration, and builder profiles
- 🤝 **Collaboration** — Community events, team projects, and member networking
- 📅 **Events** — Workshops, hackathons, meetups, and technical sessions with registration
- 💡 **Projects** — Student-built projects with team members, technologies, and AWS services
- ☁️ **AWS & Cloud Exploration** — Dedicated AWS Hub with learning, practice, and career resources
- 🚀 **Opportunities** — Internships, jobs, competitions, and external openings
- 🏆 **Recognition** — Achievements, certificates with public verification, and community milestones
- 🧠 **AI Assistance** — Ask MEGHA AI for community and technical knowledge
- 🛠️ **Administrative Management** — Full CMS for content management without code changes

Built with React, TypeScript, Three.js, and Supabase, the platform is engineered as a serious technology community hub — not a generic landing page. Every aspect, from the 3D cloud infrastructure hero to the PostgreSQL-backed CMS, is designed to reflect the engineering identity of the community.

The platform is built for the community, by the community.

---

*This document is a public project overview. Sensitive implementation details, credentials, and security internals have been intentionally excluded.*
