# 🌐 **Updating The Timeline**

This guide explains how to **add and manage seasons** on the Grimwald Timeline page. It covers how to create season components, set up background images, and add new entries.

---

# **1. Media Guidelines**

- **Images** should be **1920x1080 resolution**.
- Do **not use shaders or resource packs** in images.
- **Videos** are allowed and can use shaders or packs.
- For **modded seasons**, a modlist can be included:
  - Export the profile from **CurseForge**.
  - Place the html file in the `public/modlists` folder.
  - Name it accordingly (e.g., `S21Mods.html`).

---

# **2. Creating a New Season**

## **Duplicate the Last Season Component**

1. Navigate to `app/components/seasons`
2. Duplicate the most recent file (e.g., `season20.tsx`).
3. Rename it to match the new season (e.g., `season21.tsx`).

4. Open the file and change the following:
```tsx
export default function Season20() {
  return (
    <div className="parallaxS20">
      <div id="S20"></div>
```
- Update to (Using the correct season number):
```tsx
export default function Season21() {
  return (
    <div className="parallaxS21">
      <div id="S21"></div>
```

## **Add Background Styles**

1. Open `app/globals.css`
2. Scroll to the **Parallax section** near the bottom.
3. Add the new class to the parallax list:
```css
.parallaxS20,
.parallaxS21 {
```
4. Scroll down and add the corresponding style block (Using the correct season number):
```css
.parallaxS21 {
  background-image: url("/S21Background.png");
}
```
5. Place your background image in the `public/` folder. It must be named `S<season number>Background.png` (e.g., `S21Background.png`).

## **Add the Component to the Timeline Page**

1. Open `app/pages/timeline/page.tsx`
2. Add a new import:
```tsx
import Season21 from "@/app/components/seasons/season21";
```
3. Add the component in the JSX:
```tsx
<Season21 />
```

---

# **3. Updating Timeline Entries**

1. Open your newly duplicated season file.
2. Update the content inside the `<Timeline />` components:
```tsx
<Timeline
  side="left"
  date="23rd October 2024"
  title="Season 20 Begins"
  description="..."
  imgSrc="/S20Ships.png"
  iframeSrc="/modlists/S20Mods.html"
/>
```

## **Guidelines for Entries**

- `side`: Alternate between `left` and `right` on each entry check the previous entries last side and start with the opposite on your new entry.
- `date`: Use clear, full dates (e.g., "23rd October 2024"). If unknown, use estimates like *"Early January 2025"*.
- `title`: Must be present and descriptive.
- `description`: Must be informative, avoid naming individuals or referencing real world drama. Something like someone getting banned for breaking the server rules would be ok to reference as long as names are left out, but something like a member getting removed after commiting a real world crime should not be on the timeline. [See Section 3 of the Branding Guideliens for more information on this](branding.md).
- `imgSrc`: Path to an image in `public/` folder. Leave empty if not using.
- `iframeSrc`: Path to video or modlist. Leave empty if not using.

---

# **4. Testing**
Test your changes and ensure:
- New component added to Timeline page.
- Background image appears and the parallax effect works correctly.
- Content entries added.
- Content entries follow the guidelines.
- Entries alternate sides (left/right).
- Modlists/videos/images appear.

