📐 Wireframes – Artist Music Showcase Website

---

## SC-01: Homepage

### Layout

```
┌─────────────────────────────────────┐
│                                     │
│         ARTIST MUSIC SHOWCASE       │
│                                     │
├─────────────────────────────────────┤
│                                     │
│        [Artist Profile Image]       │
│                                     │
├─────────────────────────────────────┤
│                                     │
│           Artist Name               │
│           Brief Bio / Description   │
│                                     │
├─────────────────────────────────────┤
│                                     │
│    ┌─────────────────────────────┐  │
│    │  🎵 View All Songs  →       │  │
│    └─────────────────────────────┘  │
│                                     │
├─────────────────────────────────────┤
│                                     │
│      Latest Songs (Optional)        │
│      • Song 1                       │
│      • Song 2                       │
│      • Song 3                       │
│                                     │
└─────────────────────────────────────┘
```

### Notes
- **Button Action:** "View All Songs" → Navigate to SC-02
- **Optional Feature:** Display latest 3 songs below
- **Responsive:** Stack vertically on mobile
- **Interactive Element:** CTA button

---

## SC-02: Song List

### Layout

```
┌─────────────────────────────────────┐
│  ← Back  |  SONGS  |  ☰ Menu       │
├─────────────────────────────────────┤
│                                     │
│  📋 All Songs                       │
│                                     │
├─────────────────────────────────────┤
│  Song Title 1           [▶ Play]    │
├─────────────────────────────────────┤
│  Song Title 2           [▶ Play]    │
├─────────────────────────────────────┤
│  Song Title 3           [▶ Play]    │
├─────────────────────────────────────┤
│  Song Title 4           [▶ Play]    │
├─────────────────────────────────────┤
│  Song Title 5           [▶ Play]    │
├─────────────────────────────────────┤
│                                     │
│  (Scrollable content)               │
│                                     │
└─────────────────────────────────────┘
```

### Interactive Elements

| Element | Action | Result |
| --- | --- | --- |
| Song Title | Click | Navigate to SC-03 (Song Detail) |
| ▶ Play Button | Click | Play audio in-line (optional) |
| ← Back Button | Click | Return to SC-01 (Homepage) |

### Notes
- **Primary Action:** Click on song title
- **Secondary Action:** Quick play button (optional for MVP)
- **List Type:** Simple, scrollable list
- **Responsive:** Full width, single column on all devices

---

## SC-03: Song Detail

### Layout

```
┌─────────────────────────────────────┐
│  ← Back  |  SONG DETAIL  |  ☰ Menu │
├─────────────────────────────────────┤
│                                     │
│         [Song Cover Image]          │
│                                     │
├─────────────────────────────────────┤
│                                     │
│         Song Title                  │
│         by Artist Name              │
│                                     │
├─────────────────────────────────────┤
│                                     │
│   ┌───────────────────────────────┐ │
│   │ ▶ │  ────●────────────  │ 3:45│ │
│   │   [Play / Pause]              │ │
│   │   Seek to any position         │ │
│   └───────────────────────────────┘ │
│                                     │
├─────────────────────────────────────┤
│                                     │
│  📝 Song Description:               │
│  [Text content about the song]      │
│                                     │
├─────────────────────────────────────┤
│                                     │
│  🎤 Lyrics:                         │
│  [Full song lyrics]                 │
│  [Scrollable]                       │
│                                     │
│                                     │
│                                     │
│                                     │
└─────────────────────────────────────┘
```

### Audio Player Detailed View

```
Audio Player Component:
┌─────────────────────────────────────┐
│  ▶  │━━━━━●━━━━━━━━━━━━│  3:45      │
│  Play/Pause    Seek Bar    Duration  │
└─────────────────────────────────────┘

States:
- Stopped:  [ ▶ ]
- Playing:  [ ⏸ ]  (shows pause icon)
- Seeking:  [●] on drag
```

### Interactive Elements

| Element | Action | Behavior |
| --- | --- | --- |
| ▶ Play Button | Click | Start audio playback, button changes to ⏸ |
| ⏸ Pause Button | Click | Pause audio, button changes to ▶ |
| Seek Bar | Drag/Click | Jump to that position in song |
| ← Back Button | Click | Return to SC-02 (Song List) |
| Song Description | Scroll | Read full song information |
| Lyrics | Scroll | Read complete lyrics |

### Notes
- **No Page Reload:** SPA (Single Page Application) - smooth transitions
- **Audio Controls:** Play/Pause/Seek without disruption
- **Responsive Design:** Scrollable on mobile for lyrics
- **Auto-playing:** Audio continues to play while user scrolls

---

## 4. UI/UX Behavior Specifications

### Audio Player Behavior

```
State Flow:
[Stopped] --click play--> [Playing] --click pause--> [Paused]
   ↓                         ↑ ←──────────────────────────│
   └──────── seek/drag ──────┘
```

**Key Behaviors:**
1. **Play:** Click ▶ button → audio starts → button becomes ⏸
2. **Pause:** Click ⏸ button → audio pauses → button becomes ▶
3. **Seek:** Drag seek bar → jump to position → continue playing
4. **Duration:** Display current time / total duration

### Navigation Behavior

```
SC-01 (Homepage)
    ↓ [View Songs button]
SC-02 (Song List)
    ↓ [Click Song Title]
SC-03 (Song Detail)
    ↓ [Back button]
SC-02 (Song List)
    ↓ [Back button or Home]
SC-01 (Homepage)
```

**Key Behaviors:**
1. **No Page Reload:** Use client-side routing (Next.js Router)
2. **Smooth Transitions:** Fade/slide effects between screens
3. **Back Navigation:** Always available to return to previous screen
4. **Persistent Audio:** Audio continues playing during navigation (optional for Phase 2)

### Responsive Design

| Device | Layout |
| --- | --- |
| Desktop (1024px+) | Full width, center content, sidebar (optional) |
| Tablet (768px - 1023px) | Full width, touch-friendly buttons |
| Mobile (< 768px) | Single column, large touch targets, full-width buttons |

---

## 5. Component Specifications

### Header/Navigation Component

```
┌─────────────────────────────────────┐
│ [←] | Title/Screen Name | [☰]      │
└─────────────────────────────────────┘

Elements:
- Back Button: Always visible (except on SC-01)
- Title: Screen name or logo
- Menu Button: Hamburger menu (mobile)
```

### Song List Item Component

```
┌─────────────────────────────────────┐
│ Song Title              [▶ Play]    │
├─────────────────────────────────────┤
│ (Full width, clickable)             │
└─────────────────────────────────────┘
```

### Audio Player Component (Reusable)

```
┌─────────────────────────────────────┐
│ [▶/⏸] [Seek Bar ●] [Time]           │
├─────────────────────────────────────┤
│ Reusable across SC-02 and SC-03     │
└─────────────────────────────────────┘
```

---

## 6. Accessibility & Mobile Considerations

### Touch-Friendly
- Minimum button size: 44px × 44px
- Sufficient spacing between interactive elements
- Large text for readability on mobile

### Performance
- Lazy load lyrics/descriptions
- Cache audio metadata
- Optimize images for different screen sizes

### User Experience
- Clear visual feedback on interactions
- Loading states for audio buffering
- Error messages for failed audio loads
- Scroll position preservation (SPA)

---

