# TODO Apply Standards and make sure file name is consistent with nav

# World Downloads
- This documents aims to provide a guide for downloading, formatting, backing up and distributing the world downloads.

## Downloading and Paper Dimensions Fix
- Download the `world` folder from the server.
- If you are playing on a paper server the format is different from regular worlds and you will also need to download `world_nether` and `world_the_end`
- When downloading everything will be in a compressed file, Extract this first, now make a copy in case anything goes wrong.
- If you were on a paper server you will now need to combine the 3 world folders in order to store the world in a format that can be understood by singleplayer.
  - Rename `world_nether` to `DIM-1`
  - Rename `world_the_end` to `DIM1`
  - Move both of these into the `world folder`
  - We did not know about this issue for a number of seasons hence why a lot of world downloads are missing the nether and end.
 
## Trimming the World
- Now you should trim the world to reduce the file size without deleting anything important.
- To do this you will need to download and install MCA Selector. [https://github.com/Querz/mcaselector](https://github.com/Querz/mcaselector)
- If you had to combine the dimensions you may wish to create another copy at this point to save you recombining them if anything goes wrong at this stage.
- Open MCA Selector and select `file/open world` select the world folder and choose `select folder` when prompted choose the overworld dimension.
- The world will start loading, ensure everything looks right.
- Select `tools/filter chunks` add the following query `InhabitedTime < 5 minutes` if it is not already there. Also ensure there are no other filter queries.
- Change the option at the bottom of this filter menu from `Select` to `Delete` and ensure `Overwrite Selection` is checked, All other fields can be left unchecked/blank.
- Click ok and the program will begin purging the chunks that have been inhabited for less than 5 minutes. This is useful as if you rendered the world for dynamap or all of the chunks would wihtin your set area will have been briefly loaded. It also clears areas players have loaded by just passing through them which can be a lot especially with elytra.
- You can go to `file/open dimension` and run the purge on the nether and end dimension too.
- Depending on the world size you may wish to change the amount of time in the filter. 5 minutes is usually good but it depends how much you are willing to lose/how big the world is.
- Once this is done ensure the world is recognised by the game by placing it in your saves folder. There is no need to load the world but if you do not make changes in it before publishing. (or create a copy so you can publish an unaltered other than trimmed version)

## Uploading the World
- You will need git installed and a github account for this, This guide will not tell you how to set this up or how to use git so you will have to go do that yourself and come back once done.
- Create a new public repository for the world using this name format `Season-X-World` replace X with the season number. (Ensure this is created on this github account `Grimwald-SMP`)
- The repository description should be the same as the name without the dashes `-`.
- Add a README.md file to this repo and enter the following text and adapt it the season you are uploading.
```
# Grimwald SMP Season (Season Number) World

## Requirements
- Version 1.16.4(+/ONLY, Choose one)
- No mods required

## Download and Installation Instructions
- Click the green button near the top that says code
- Click Download Zip
- Wait for the download to complete then unzip into your minecraft saves folder (%appdata%/.minecraft/saves)
```
- If the season requires mods to be played it may look more like this to include a link to required mods, Note the version does not say only or +, just the version this is because it can be upgraded but it is recommended you just stay on the noted version as not all mods might be available in later versions:
```
# Grimwald SMP Season 20 World

## Requirements
- Version 1.19.2 
- Mods Required: https://grimwald.vercel.app/modlists/S20Mods.html

## Download and Installation Instructions
- Click the green button near the top that says code
- Click Download Zip
- Wait for the download to complete then unzip into your minecraft saves folder (%appdata%/.minecraft/saves)

```

- Clone this repo, Move the entire trimmed world folder into it and then commit and push to github.
- Now open [https://github.com/Grimwald-SMP/Grimwald-SMP](https://github.com/Grimwald-SMP/Grimwald-SMP).
- Edit the table adding a new row for the season you just added, filling out the cells and linking the new repo.
- Once this is all done you should announce it to players and send a link.