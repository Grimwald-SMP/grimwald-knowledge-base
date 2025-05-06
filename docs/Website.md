# 🌐 **Updating the Website**

This guide explains how to **update the home page and navbar** on the Website which is required when a new season starts or if the IP changes

---

# **1. Website Link**

[https://grimwald.vercel.app](https://grimwald.vercel.app)

---

# **2. Updating the Home Page For A New Season**

1. Open the file: `app/page.tsx`
2. Locate the section of code similar to the following:

```tsx
<>
  <Navbar />
  <Hero />
  <div className="parallax"></div>
  <h2 id="subtitle">Season 21</h2>
  <Timer
    startText="Season Started: 8th of February 2025"
    startTimestamp={1739031120}
  />
  <h2 id="subtitle">Server Lifetime</h2>
  <Timer
    startText="Server Started: 14th of September 2020"
    startTimestamp={1600095600}
  />
</>
```

3. Modify the following:
   - **Season number**: Update in the `<h2 id="subtitle">Season XX</h2>` line.
   - **Start date and timestamp**: Update in the `<Timer>` element immediately below the season subtitle.
     - Maintain the current format.
     - Use a [Unix Timestamp Converter](https://www.unixtimestamp.com) to get the correct `startTimestamp` from the official start date/time.
     - **Do not** modify the second set of `<h2>` and `<Timer>` elements related to **Server Lifetime**. These should always remain unchanged.

4. If the IP has changed open the file 'app/components/HeroStatus.js'
5. Locate this block of code and replace the IP and port with the new IP and port:
```js
export default function HeroStatus() {
  useEffect(() => {
    initServerData("127.0.0.1", "25565");
  }, []);
```

---

# **3. Updating the Map Link**

1. If the map link has changed, Open the file: `app/components/Navbar.js`
2. Find the line similar to:

```tsx
<NavButton href="http://127.0.0.1:1234/" text="Map" />
```

3. Replace the `href` with the updated map URL.
   - This URL should be the **server's IP** + the **map webserver port**.
   - This information can typically be found in either the _Additional Ports_ section or the _Map Config_.
   - Ensure that the map site is properly configured. For more information, refer to the [Dynmap Setup Instructions](plugins.md).

---

# **4. Adding Modlists**

- 

---

# **5. Additional Reminders**

- Ensure all **filenames** and **navigation references** (including Navbar buttons, titles, and imports) are consistent.
- After making changes, always **test locally** before deploying to production.
- Maintain the visual and structural consistency of the homepage.

---

# **6. Notes**

- These updates should be performed **at the beginning of each season**.
- Review the site after every change to ensure no unintended errors were introduced.
- General changes to the website are not covered in these docs, If you want to change something else you will have to read through the code and make changes yourself. An understanding of: Next.js, React, HTML, CSS, JavaScript and Tailwind are recommended.

---