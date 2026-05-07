📄 BRD – Artist Music Showcase Website

## 1. Overview

### 1.1 Background

Currently, the artist's (your father's) compositions have not been officially released as an album or on streaming platforms.

Recently, songs have been recorded through AI technology, creating an opportunity to:

- Publish works to the public
- Build a personal artist brand

However, there is no centralized platform to showcase these songs.

### 1.2 Objective

Build a website with the following goals:

- Introduce artist information
- Provide a list of composed songs
- Allow users to preview audio recordings (AI-generated)
- Create a foundation for future development (album, streaming, fanbase)

### 1.3 Scope

✔️ **In Scope**

- Public website (PC + mobile)
- Artist introduction page
- Song list
- Audio listening directly on web
- Song detail page

❌ **Out of Scope (current phase)**

- Payment / music sales
- User login / account
- Large-scale real-time streaming
- Native mobile app

---

## 2. Glossary

| Term          | Definition                          |
| ------------- | ----------------------------------- |
| Song          | A composition created by the artist |
| Audio         | Audio file                          |
| User          | Website visitor                     |
| Administrator | Content manager                     |

---

## 3. Stakeholders

| Role             | Description    |
| ---------------- | -------------- |
| Owner (Musician) | Lai Hong Phong |
| Developer        | Lai Hien Minh  |
| BA/PM            | Lai Son Thach  |
| User             | Music listener |

## 4. Business Flow

### 4.1 User Perspective

Access → View Homepage → Browse Song List → Select Song → Play

### 4.2 Administrator Perspective (Simple)

Register Song → Upload Audio → Publish

---

## 5. Functional Requirements

### 5.1 Homepage

**ID:** FR-01

**Description:** Display artist information

**Details:**

- Name
- Photo
- Short bio

### 5.2 Song List

**ID:** FR-02

**Description:** Display list of songs

**Details:**

- Title
- Thumbnail (optional)
- Quick play button

### 5.3 Song Detail

**ID:** FR-03

**Description:** Display song details

**Details:**

- Title
- Lyrics
- Audio player
- Song description

### 5.4 Audio Player

**ID:** FR-04

**Description:** User can listen to music

**Details:**

- Play / Pause
- Seek bar
- Duration

### 5.5 Admin Features (Optional Phase 2)

**ID:** FR-05

**Description:** Manage songs

**Details:**

- Upload audio
- Enter metadata

---

## 6. Non-functional Requirements

### 6.1 Performance

- Load time < 3 seconds
- Audio playback without significant delay

### 6.2 Availability

- Website operational 24/7 (except maintenance)

### 6.3 Security

- No login required (initial phase)
- File upload restricted to admin

### 6.4 Responsive Design

- PC
- Mobile (required)

---

## 7. Data Requirements

### 7.1 Song

| Field       | Type   | Description |
| ----------- | ------ | ----------- |
| id          | string | ID          |
| title       | string | Song title  |
| description | string | Description |
| audio_url   | string | Audio link  |
| lyrics      | text   | Song lyrics |

### 7.2 Artist

| Field     | Type   |
| --------- | ------ |
| name      | string |
| bio       | text   |
| image_url | string |

---

## 8. Screen List

| Screen ID | Name        |
| --------- | ----------- |
| SC-01     | Homepage    |
| SC-02     | Song List   |
| SC-03     | Song Detail |

---

## 9. Constraints

- Development part-time (after work hours)
- Small team (2 people)
- Zero budget

---

## 10. Success Metrics

- Website successfully deployed
- Audio playback runs smoothly
- At least 5 songs uploaded
- Real-world traffic (optional)

---
