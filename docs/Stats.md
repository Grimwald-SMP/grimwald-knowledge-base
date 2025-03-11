# TODO Apply Standards and make sure file name is consistent with nav

# Stats
- This documents aims to provide a guide for extracting formatting and updating the stats for the website.

# Tracking The Stats
- We use 2 vanilla tweaks datapacks to track the stats, they can be found here https://vanillatweaks.net/picker/datapacks/
- These are Track Statistics and Track Raw Statistics, they should be installed as soon as a season starts.
- In the event these datapacks are not updated to the version the server is running on, use the latest version as long as there has been no technical changes that break the datapacks they should work but may be missing new stats due to the next version, once the packs release for this version you can safely update without losing any stats, new stats will start tracking from then.
- In the event that the server is running an older version, try to get the correct version from vanilla tweaks.
- Technically there are other ways to access players stats without these packs but our formatter is based around this so using other methods requires a lot of manual work or programming a new formatter so try to use these packs where possible.

# Extracting The Stats From The Server And Formatting Them
## Extracting stats
- Download `scoreboard.dat` from the data folder on the server
- Download Python if you do not already have it installed. https://www.python.org/downloads/
- Download the stat formatter. https://github.com/JadenLabs/grimwald-stat-prep
- Download and Install NBTExplorer. https://github.com/jaquadro/NBTExplorer/
- Open CMD in administrator mode inside of the NBTExplorer directory
- Enter the following command, replace PATH with the path to wherever you downloaded `scoreboard.dat` to:
```
nbtutil --path "PATH\scoreboard.dat\data\PlayerScores" --printtree --json "main.json"
```
- You should now have a main.json within your NBTExplorer Directory, move this file to the MainStats directory from the stat formatter.

## Using the formatter
- Open main.py and edit aliases if needed (If any players have switched names or accounts) the format for this is as follows `["NewName", ["OldName1", "OldName2", "OldName3"]]` or more commonly  `["NewName", ["OldName"]]` for players who have only had one name change include all the names that players have used throughout the season, There is no need to list players who have not changed their name.
- You are now ready to run Main.py, when prompted choose to run the whole program and output for website.
- You can find the outputted files in the output folder.

## Manual formatting steps
- WARNING: Currently this program does not format everything, there are some additional steps before you can add it to the website. (Note: This process may be automated in the future.)
- Note that all converted values should be rounded to 2 decimal places.
- Go through each file and remove all rows that contain score: 0.
- Go through each file and remove banned players.
- Convert playtime minutes into hours.
- Convert distances from cm into m, You can check which stats are they are indicated by (Blocks) on the stats page (1m = 1 block)
- Add the 2 different diamond stats together, there are 2 diamonds mined stats one for regular diamonds and one for deepslate diamonds. On the website we just display a total diamonds mined, these stats need manually combined, it is easier to modify the deepslate version as most people don't mine much regular diamond ore. Ensure once you have combined each persons stat that they are still in the correct position based on their score, you may have to move them up/down in the file to maintain the correct order. (Order is determined by position in the json, higher scores should be at the top.)

# Adding The Stats To The Website
- Open the stats directory in `public/stats`
- Open the `stats.html` file amd change the season number to the season you are updating the stats for on both the title element and the h1 element.
- Open the `stats.js` file, in `const scoreboardData` there are multiple sections with different names that match the files generated from the formatter. (Which should now have had the manual formatting applied too, Note: The name of the diamond stat in this file is slightly altered to reflect the 2 diamond stats being combined)
- You will have to manually open the each new stats file and paste it into the correct section of this file replacing the old data. (This process could be automated in the future, generating the entire js file for you) 
- Once this is done go to `app/components/Navbar.js` and change the season number for the stats button text.