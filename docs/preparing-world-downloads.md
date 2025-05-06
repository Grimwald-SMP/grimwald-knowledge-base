# 🛠️ **World Downloads**

This document provides a complete guide for downloading, trimming, formatting, backing up, and distributing Grimwald SMP world downloads.

---

# **1. Downloading the World & Fixing Paper Format**

- Download the `world` folder from the server.
- Tip: Also download the whitelist.json file, this can be uploaded for the new season to prevent manually whitelisting everyone again.

## **If using Paper**
- If the server runs Paper, you must also download `world_nether` and `world_the_end`.
- Extract the compressed file and create a backup copy before making changes.
- Open `world_nether` and copy `DIM-1` folder.
- Paste this into the main `world` folder.
- Open `world_the_end` and copy `DIM1` folder.
- Paste this into the main `world` folder.

*Note: Older seasons may lack Nether/End data due to this issue being discovered later.*

---

# **2. Trimming the World**

Reducing world size before upload saves space and makes the download more accessible especially if the world has additional loaded chunks for dynmap purposes that have not been explored by players.

## **Requirements**
- Install [MCA Selector](https://github.com/Querz/mcaselector)

## **Steps**
1. Make a backup of the world.
2. Open MCA Selector → `File > Open World` → select `world` folder.
3. When prompted, select the `overworld`.
4. Once loaded, go to `Tools > Filter Chunks` and apply this filter:
   ```
   InhabitedTime < 5 minutes
   ```
5. Change `Action` to `Delete`, and check `Overwrite Selection`.
6. Click OK to delete unnecessary chunks.
7. Repeat steps 2–6 for the Nether and End if required by going to `File > Open Dimension`.
8. Test there are no issues trimmed world by placing a copy of it in your saves folder.
9. Make sure you use the world you upload is a trimmed version that has not been opened after trim. Hence using a copy in the previous stage.

---

# **3. Uploading the World to GitHub**

## **Prerequisites**
- Knowledge of how Git and GitHub work.
- Git must be installed
- You must have access to the [Grimwald-SMP GitHub account](https://github.com/Grimwald-SMP) for the upload.

## **Steps**
1. Create a new **public** repository using the following naming convention:
   ```
   Season-X-World
   ```
   *Replace `X` with the correct season number.*

2. Add a `README.md` using one of the following templates:

For Vanilla Seasons:
```
# Grimwald SMP Season X World

## Requirements
- Version 1.16.4+
- No mods required

## Download and Installation Instructions
- Click the green "Code" button
- Select "Download ZIP"
- Extract to your Minecraft saves folder (%appdata%/.minecraft/saves)
```

For Modded Seasons:
```
# Grimwald SMP Season 20 World

## Requirements
- Version 1.19.2
- Mods Required: https://grimwald.vercel.app/modlists/S20Mods.html

## Download and Installation Instructions
- Click the green "Code" button
- Select "Download ZIP"
- Extract to your Minecraft saves folder (%appdata%/.minecraft/saves)
```
Note exact version listed as usually updating a modded world with many mods causes issues.

3. Edit the template to have the correct information: Version and link to mods required from website. See [Timeline Media Guidelines for how to upload the modlist for modded seasons](timeline.md)
4. Clone the new repo locally.
5. Move the trimmed world folder into the repo.
6. Commit and push the changes to GitHub.

---

## 4. Updating Main Repository

1. Open [Grimwald-SMP/Grimwald-SMP](https://github.com/Grimwald-SMP/Grimwald-SMP)
2. Edit the table to include a new row for the world you uploaded:
   - Add season number
   - Link the GitHub repository
   - Add any relevant notes or version info

---

## 5. Announcing the World Download

Once uploaded:
- Share the download link with the community via Discord or other platforms.
- Include a brief summary (e.g., version, mods if any).