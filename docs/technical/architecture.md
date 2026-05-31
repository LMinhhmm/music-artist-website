# Architecture Design

## 1. Overview

This document describes the system architecture of the Music Artist Website project.

The application is designed as a lightweight fullstack web application that showcases original songs and AI-generated audio recordings from an independent artist.

The project architecture prioritizes:

- Simple fullstack development
- Low operational cost
- Learning-oriented implementation
- Maintainability for a small development team

The system uses:

- Next.js for frontend and backend
- SQLite as database
- Prisma ORM for database access

---

## 2. High-Level Architecture

```
User
↓
Next.js Frontend (React UI)
↓
Next.js API Routes
↓
Prisma ORM
↓
SQLite Database
```

---

## 3. Tech Stack

| Layer           | Technology                   |
| --------------- | ---------------------------- |
| Frontend        | Next.js (React + App Router) |
| Backend API     | Next.js Route Handlers       |
| ORM             | Prisma                       |
| Database        | SQLite                       |
| Styling         | Tailwind CSS                 |
| Deployment      | Vercel                       |
| Version Control | GitHub                       |

---

## 4. Architecture Decisions

### Why Next.js Fullstack?

Next.js was selected because:

- Frontend and backend can be developed in one project
- Built-in routing system
- Modern React ecosystem
- Easy deployment
- Suitable for small team development

This architecture allows the developer to learn frontend development, API development, backend architecture, and database integration without introducing unnecessary infrastructure complexity.

---

### Why SQLite?

SQLite was selected because:

- Lightweight setup
- No server management required
- Suitable for MVP and portfolio projects
- Easy local development

SQLite is sufficient for small-scale content management, read-heavy applications, and learning backend fundamentals.

---

### Why Prisma?

Prisma was selected because:

- Type-safe database access
- Developer-friendly syntax
- Easy schema management
- Modern ORM ecosystem

Prisma simplifies database queries, schema migrations, and data modeling.

---

## 5. System Components

### Frontend Layer

Responsibilities:

- Render UI
- Display song information
- Handle navigation
- Handle audio playback

Main pages:

- Homepage
- Song list page
- Song detail page

---

### Backend API Layer

Responsibilities:

- Provide song data
- Handle database access
- Separate frontend and data logic

Planned API endpoints:

- `GET /api/songs`
- `GET /api/songs/[slug]`

---

### Database Layer

Responsibilities:

- Store song metadata
- Manage song content

The database does **not** store audio or image binary files. Those are stored as static assets in:

- `public/audio`
- `public/images`

---

## 6. Data Flow

### Song List Flow

1. User accesses `/songs`
2. Frontend sends request to `GET /api/songs`
3. API queries database via Prisma
4. Database returns song data
5. Frontend renders song list

---

### Song Detail Flow

1. User accesses `/songs/[slug]`
2. Frontend requests song detail API
3. API retrieves song data
4. Frontend renders title, lyrics, and audio player

---

## 7. Project Structure

```
frontend/
├── app/
│   ├── api/
│   │   └── songs/
│   └── songs/
├── components/
├── lib/
├── prisma/
├── public/
│   ├── audio/
│   └── images/
└── types/
```

---

## 8. Database Design

### Song Table

| Column       | Type     |
| ------------ | -------- |
| id           | String   |
| title        | String   |
| slug         | String   |
| description  | String   |
| lyrics       | Text     |
| genre        | String   |
| audioUrl     | String   |
| thumbnailUrl | String   |
| published    | Boolean  |
| createdAt    | DateTime |

---

## 9. API Design

### `GET /api/songs`

**Purpose:** Retrieve published song list

**Response:**
```json
[
  {
    "id": "song-001",
    "title": "Sample Song"
  }
]
```

---

### `GET /api/songs/[slug]`

**Purpose:** Retrieve song detail information

**Response:**
```json
{
  "title": "Sample Song",
  "lyrics": "...",
  "audioUrl": "/audio/sample.mp3"
}
```

---

## 10. Audio File Management

Audio files are stored in `public/audio/` and images in `public/images/`. These files are served as static assets by Next.js.

---

## 11. Deployment Architecture

Vercel is planned for deployment because:

- Native support for Next.js
- Easy GitHub integration
- Fast deployment workflow
- Free tier available

---

## 12. Scalability Considerations

Current architecture is optimized for MVP development. Possible future enhancements include:

- PostgreSQL migration
- Authentication system
- Admin dashboard
- Upload system
- Analytics integration
- AI chatbot integration

---

## 13. Security Considerations

Current MVP scope:

- Public read-only content
- No user authentication
- No content upload feature

Security complexity is intentionally minimized during the MVP phase.

---

## 14. Risks and Limitations

### Risks

- SQLite is not suitable for high concurrency
- No admin content management system yet

### Limitations

- Content updates require manual DB updates
- No authentication support in MVP

---

## 15. Future Architecture Candidates

| Option     | Purpose                      |
| ---------- | ---------------------------- |
| PostgreSQL | Scalable production database |
| Supabase   | Managed backend service      |
| AWS S3     | External audio storage       |
| Cloudinary | Media optimization           |

---

## 16. Summary

The current architecture prioritizes:

- Learning fullstack development
- Fast MVP implementation
- Low operational cost
- Simple deployment
- Maintainable project structure

This architecture is suitable for portfolio projects, small team development, SDLC practice, and fullstack/backend learning.
