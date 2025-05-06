# 🌐 **Updating the Stats Page**

This document provides a complete guide for **extracting**, **formatting**, and **updating** the player statistics for the Grimwald website.

---

# **1. Tracking the Stats**

- Grimwald uses two **Vanilla Tweaks datapacks** to track player statistics:
  - Track Statistics
  - Track Raw Statistics
- These datapacks must be installed **at the start of each season** and can be found at [Vanilla Tweaks](https://vanillatweaks.net/picker/datapacks/).
- If the datapacks are not available for the current server version:
  - Use the **latest available version** if no technical changes have occurred.
  - Update to the correct version once available; new statistics will only begin tracking after the update.
- If running an older Minecraft version, download the appropriate datapack version from Vanilla Tweaks.
- Although other methods exist to access player stats, the Grimwald formatter is designed specifically for these datapacks. Using alternatives would require extensive manual work or reprogramming.

---

# **2. Extracting and Formatting Stats**

## **Extracting Stats**

1. Download the `scoreboard.dat` file from the server's **data** folder.
2. Download and install [Python](https://www.python.org/downloads/).
3. Download and install [NBTExplorer](https://github.com/jaquadro/NBTExplorer/).
4. Download the [Grimwald Stat Formatter](https://github.com/JadenLabs/grimwald-stat-prep).
5. Open **Command Prompt** as an administrator in the NBTExplorer directory.
6. Run the following command, replacing `PATH` with the correct location:
   ```
   nbtutil --path "PATH\scoreboard.dat\data\PlayerScores" --printtree --json "main.json"
   ```
7. Move the generated `main.json` file within your NBTExplorer directory into the **MainStats** directory within the Stat Formatter.

## **Using the Formatter**

1. Open `main.py` in the formatter project.
2. Edit the `aliases` section if needed:
   - Example format:
     ```
     ["NewName", ["OldName1", "OldName2"]]
     ```
   - Only add players who have changed their name.
3. Run `main.py`.
4. When prompted, choose to **run the full program** and **output for website**.
5. Find the output files inside the `output` folder.

## **Manual Formatting Steps**

- **Remove** any rows where the score is `0`.
- **Remove** any entries belonging to banned players.
- **Convert playtime** from minutes into hours by dividing by `60`.
- **Convert distances** tracked in centimeters (cm) into meters (m) by dividing by `100`.
  - Distances labeled as *(Blocks)* should be treated as meters as blocks are cubic meters.
- **Combine diamond statistics**:
  - Merge the regular diamond and deepslate diamond stats into a single total.
  - Modify the deepslate diamond file to reflect the combined total.
  - After combining, **reorder** players if necessary so the highest scores remain at the top.
- **Round** all converted values to **two decimal places**.

---

# **3. Adding Stats to the Website**

## **Updating the Files**

1. Navigate to the `public/stats` directory.
2. Open `stats.html`:
   - Update the season number in both the `<title>` tag and the `<h1>` header.
3. Open `stats.js`:
   - In the `const scoreboardData` section, replace each block with the newly formatted data.
   - Note: The name of the diamond stat in this file is slightly altered to reflect the diamond stats being combined

## **Updating the Navbar**

1. Open `app/components/Navbar.js`.
2. Update the season number displayed in the Stats button text.

---

# **4. Important Notes**

- Test all changes **locally** before pushing them live.
- Always double-check:
  - Stat conversions
  - Diamond stat merging
  - File structure and order
- This process may be automated more fully in the future. Until then, maintain accuracy manually.