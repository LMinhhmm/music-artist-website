📘 Basic Design Document

## 1. System Overview

### 1.1 System Name

Artist Music Showcase Website (Tentative)

### 1.2 Purpose

- Artist can introduce their works
- Users can listen to music directly on the web
- Create a platform for future expansion

### 1.3 System Architecture

**Recommended option (practical + easy to implement):**

- Frontend: React (Next.js)
- Backend: Firebase / Supabase
- Storage: Cloud Storage (audio files)

**Architecture diagram:**

```
[User] → [Frontend (Next.js)] → [Backend (Firebase)]
                               → [Storage (Audio files)]
```

---

## 2. Screen Design

### 2.1 Screen List

| Screen ID | Screen Name |
| --- | --- |
| SC-01 | Homepage |
| SC-02 | Song List |
| SC-03 | Song Detail |

### 2.2 Homepage (SC-01)

**Purpose:** Introduce artist

**UI Structure:**

```
---------------------------------
| Artist Image                 |
| Artist Name                  |
| Bio                          |
---------------------------------
| Latest Songs (optional)      |
---------------------------------
```

**Item Definition:**

| Item Name | Type | Required |
| --- | --- | --- |
| name | string | ✓ |
| bio | text | ✓ |
| image_url | string | ✓ |

### 2.3 Song List (SC-02)

**UI Structure:**

```
---------------------------------
| Song List                    |
|-----------------------------|
| Title | Play Button         |
| Title | Play Button         |
---------------------------------
```

**Item Definition:**

| Item Name | Type |
| --- | --- |
| title | string |
| audio_url | string |

### 2.4 Song Detail (SC-03)

**UI Structure:**

```
---------------------------------
| Title                        |
| Audio Player                 |
|-----------------------------|
| Lyrics                       |
---------------------------------
```

---

## 3. UI Specification

### 3.1 Audio Player

| Action | Behavior |
| --- | --- |
| Play | Start playback |
| Pause | Pause playback |
| Seek | Change playback position |

### 3.2 Navigation

| From | To |
| --- | --- |
| Homepage | Song List |
| Song List | Song Detail |

---

## 4. Data Design

### 4.1 ER Model

```
Artist (1) ─── (N) Song
```

### 4.2 Table Definition

#### 4.2.1 Artist

| Column | Type | Description |
| --- | --- | --- |
| id | string | Primary Key |
| name | string | Artist name |
| bio | text | Biography |
| image_url | string | Image URL |

#### 4.2.2 Song

| Column | Type | Description |
| --- | --- | --- |
| id | string | Primary Key |
| title | string | Song title |
| description | text | Description |
| audio_url | string | Audio file URL |
| lyrics | text | Song lyrics |
| artist_id | string | Foreign Key |

---

## 5. API Design (If using separate backend)

*Note: If using Firebase → this section is optional, but recommended for portfolio*

### 5.1 Get Song List

**Method:** GET

**URL:** `/api/songs`

**Response:**

```json
[
  {
    "id": "1",
    "title": "Song A",
    "audio_url": "xxx"
  }
]
```

### 5.2 Get Song Detail

**Method:** GET

**URL:** `/api/songs/{id}`

---

## 6. Non-functional Design

### 6.1 Performance

- Page load < 3 seconds
- Stable audio streaming

### 6.2 Security

- No public upload API
- Storage access control

### 6.3 Availability

- Uptime > 99% (free tier acceptable)

---

## 7. Error Handling

| Case | Response |
| --- | --- |
| Audio load failure | Display error message |
| API failure | Retry / user notification |

---

## 8. Constraints

- Part-time development
- Team of 2 people
- Low budget

---

## 9. Future Enhancements

- Playlist feature
- AI chatbot integration
- Analytics dashboard
- Admin content management dashboard

---

