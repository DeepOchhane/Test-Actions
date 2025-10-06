## 🎨 Frontend PR (UI/UX Changes)

### 📌 ClickUp Task
[ClickUp Task](https://app.clickup.com/t/XXXXXX)

---

### 📝 Description
- What UI/UX change is introduced?

---

### ✅ Acceptance Criteria
- [ ] UI matches design (Figma reference if applicable).  
- [ ] I verified cross-browser and Responsive design tested (mobile, tablet, desktop).  
- [ ] No console errors/warnings in browser.  
- [ ] My changes build and run successfully in dev.
- [ ] No unused imports, console logs, or debug code remain.
- [ ] All UI text is internationalized (i18n) if applicable.

---

## ⚛️ Effects Sanity Check
- [ ] If I added an effect, it connects React to an *external system* (network, storage, timers, subscriptions, DOM imperative work).
- [ ] This logic could not be handled at the *event boundary* (e.g., onOpenChange, router action).
- [ ] For data fetching I used *React Query/SWR* with enabled/queryKey instead of manual effects.
- [ ] I did *not* mirror props to local state. Any computed value is derived (useMemo/variable), not synced.
- [ ] I am *not* using useLayoutEffect (or this file is in the allowed folder for measurement/focus).
- [ ] Dependency arrays are minimal and stable (no unstable function identities unless memoized for a reason).

### 📸 Screenshots / Video
<!-- Add before/after screenshots or Loom video -->

---

## 🧠 Notes for Reviewers
Add any context or testing steps that will help reviewers.
