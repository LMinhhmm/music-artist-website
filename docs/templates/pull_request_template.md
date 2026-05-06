## 🧩 Pull Request

---

## 📌 Related Issue

Closes #

---

## 📝 Summary

<!-- Brief description of what this PR does -->

---

## 🔍 Changes

<!-- List specific changes made -->

---

## 🎯 Purpose / Background

<!-- Why is this change needed? What problem does it solve? -->

---

## 🧪 How to Test

<!-- Step-by-step instructions for testing this PR -->

---

## 📸 Screenshots (if UI change)

### Before:

<!-- Add screenshot or N/A -->

### After:

<!-- Add screenshot or N/A -->

---

## ✅ Checklist

- [ ] Code runs without error
- [ ] No console errors
- [ ] UI works as expected
- [ ] Tested manually
- [ ] Related issue is linked
- [ ] Changes are documented (if applicable)

---

## ⚠️ Notes / Concerns

<!-- Any additional information or concerns? -->

---

## 📋 PR Guidelines

**Size:** Keep PRs under 300 lines when possible (easier to review)

**Scope:** Each PR should address one feature or fix

**UI Changes:** Always include before/after screenshots

**Testing:** Always provide clear testing steps

**Issues:** Always link to related GitHub issue using "Closes #X"

---

### Example PR (Real-world format)

**Title:** `feat: add song list page`

**Related Issue:** Closes #6

**Summary:**

- Implement song list page UI component
- Add routing to /songs endpoint
- Integrate with dummy data

**Changes:**

- Created `components/SongList.tsx` component
- Updated `pages/songs.ts` route
- Added mock data for development

**Purpose / Background:**
This PR implements the Song List page (SC-02) as defined in the requirements, allowing users to view all available songs and navigate to individual song details.

**How to Test:**

1. Run `npm run dev`
2. Navigate to `/songs`
3. Verify song list displays correctly
4. Click on a song to verify navigation to detail page

**Screenshots:**

- After: [Insert screenshot]

**Checklist:**

- [X] Code runs without error
- [X] No console errors
- [X] UI works as expected
- [X] Tested manually
- [X] Related issue is linked

**Notes:**

- Using mock data - will integrate with Firebase API in Phase 2
- Responsive design tested on mobile (375px) and desktop (1024px)

### ⚠️ **Mistakes to avoid:**

- ❌ Generic messages ("update code", "fix bug")
- ❌ No testing instructions
- ❌ Issue not linked
- ❌ No screenshots for UI changes

### 🚀 **Team best practices:**

- Keep PRs ≤ 300 lines
- One feature per PR
- Always include screenshots for UI changes
- Clear, structured descriptions

---
