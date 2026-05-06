🧭 Screen Transition Diagram

## 1. Overall User Flow

```
┌─────────────────────┐
│   SC-01 Homepage    │
└──────────┬──────────┘
           │
           ↓
┌─────────────────────┐
│  SC-02 Song List    │
└──────────┬──────────┘
           │
           ↓
┌─────────────────────┐
│ SC-03 Song Detail   │
└─────────────────────┘
```

---

## 2. Detailed Flow (With User Actions)

```
① User Access
  ↓
┌─────────────────────────────────────┐
│   SC-01 Homepage                    │
│   (Display artist info)             │
└──────────┬────────────────────────┬─┘
           │                        │
    (View Songs)            (Exit)
           │                        │
           ↓                   [End]
┌─────────────────────────────────────┐
│   SC-02 Song List                   │
│   (Display all songs)               │
└──────────┬────────────────────────┬─┘
           │                        │
    (Click Song)              (Go Back)
           │                        │
           ↓                        │
┌─────────────────────────────────────┐
│   SC-03 Song Detail                 │
│   (Display title, lyrics, player)   │
└──────────┬────────────────────────┬─┘
           │                        │
    (Play Audio)              (Back to List)
           │                        │
         [Play]          (Return to SC-02)
```

---

## 3. State Transitions

| Current State | Action | Next State |
| --- | --- | --- |
| SC-01 Homepage | Click "View All Songs" | SC-02 Song List |
| SC-02 Song List | Click on a song | SC-03 Song Detail |
| SC-03 Song Detail | Click "Back" button | SC-02 Song List |
| SC-02 Song List | Click "Home" button | SC-01 Homepage |

---

## 4. Navigation Tree

```
Homepage (SC-01)
├── Navigation Menu
│   ├── Home (SC-01)
│   ├── Songs (SC-02)
│   └── About (optional)
│
Song List (SC-02)
├── Back to Homepage
├── Song Item
│   └── → Song Detail (SC-03)
│
Song Detail (SC-03)
├── Audio Player
├── Back to Song List
└── Navigation Menu
    └── Home (SC-01)
```

---

## 5. User Interaction Points

### Homepage (SC-01)
- **Navigation:** Link to Song List
- **Call-to-Action:** "Explore Songs" / "View All"

### Song List (SC-02)
- **Interaction:** Click on any song title or play button
- **Navigation:** Back button to Homepage
- **Action:** Navigate to Song Detail

### Song Detail (SC-03)
- **Interaction:** 
  - Play/Pause audio
  - Seek through song
  - Read lyrics
- **Navigation:** Back button to Song List
- **Action:** Return to Song List

---