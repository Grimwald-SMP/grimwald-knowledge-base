# TODO Apply Standards and make sure file name is consistent with nav

# Admin Guide
- This document aims to provide usage for all of our commands as well as guidelines on how to use them.
- Some of the guidelines might seem to state the obvious but most are based on past experience so it was designed to be as specific as possible

# Commands
## Basic commands
- `ban <Username>` - Used to ban a player.
- `/kick <Username>` - Used to kick a player from the server (they will be able to join back instantly after).
- `/tp <your Username> <destination or Username to tp to>` - Teleports you to a specific player or location.
- `/restart` - Restarts the server (no progress lost) use this if the server is really laggy, ensure it is not just you who is laggy.
- `/tps` - Gets the ticks per second, this is a good measure of server performance, 20tps is what it should be at anything under means it is underperforming, consider restarting if it is under 15tps, If it does not help hardware upgrades may be needed.
## Coreprotect
- `/co i` - Toggles Inspector mode, allowing you to left/right click (They show different info based on which button you click, E.g. interactions vs transactions on containers) to view the logs of any block or container, including a timestamp and which user performed the action, useful for catching griefers or thiefs.
- `/co l <page number>` - Allows you to view other pages of the most recently viewed log in inspector mode.
- `/co rollback <radius> <time>` Allows you to rollback an area to a time before it was griefed or stolen from, use the timestamp from the logs to help you know how far to rollback. There are other parameters for this command that can filter down what to rollback even further but these are usually not needed (Some things may break when rolled back E.g. redstone machines, especially those with moving components such as flying machines)
- Other Parameters for rollback (Append these to the command above if needed, which usually they won't be):
    - `<username>` Only rollback actions performed by a specific user.
    - `<include items>` - Include specific items or blocks in the rollback, by default everything within the radius is rolled back.
    - `<exclude items>` - Exclude specific items or blocks in the rollback.
    - `<action>` - Choose specific actions to rollback.
## Open inv
- These commands work with offline players.
- `/oi <player name>` - Opens a player's inventory, useful for finding stolen items or identifying xray users or people who have used dupe cheats.
- `/oe <player name>` - Opens a player's end chest, another place to check for illegal items.

## Vanish
- `/vanish` - Toggles vanish, sends a message to show you have logged out, hides your name from the list of online players and makes you invisible, useful for catching players cheating can be paired with spectator mode for better movement.

## Datapack commands
- NEVER USE `/reload` - This command may seem useful as it can enable datapacks on the fly without a full restart but breaks many plugins
- Instead use `/datapack list` to retrieve a list of all datapacks, enabled or not then use `/datapack enable <datapack file name>`

# Guidelines
## Responsibilities
- This is a volunteer role and we understand people can be busy that being said, when you are available you should be able to do the following as required:
    - Help out players when they need it.
    - Punish players who are breaking the rules.
    - Engage in admin discussions. (Voice chat is not required)
    - Welcome new players, guide them to the rules and server info and whitelist them.
    - Ban bots or hacked accounts in chat.
    - Post announcements or polls when needed.
- There are other specialised roles that certain admins will handle such as advertising.

## Punishments for breaking rules
- Punishment for breaking rules are up to you as an admin, however it might be good to discuss with other admins first, depending on the rule that was broken you may want to issue a preliminary ban whilst you discuss.
- Always ensure someone has actually broken the rules before issuing a punishment.
- Only ban people for breaking the rules, not just because they have done something you do not like. Basically just try to remain unbiased when giving out punishments.
- If someone joins and instantly breaks rules it is their own fault for not reading them and in most cases this will be a permanent ban but depending on severity could be a warning if it is something minor.
- If a trusted member breaks the rules you may wish to consult other admins first, But their trusted status should not let them away with breaking the rules so some form of punishment should be given.
- 0 Tolerance against hate speech, harrasment and bullying, If anyone is being racist, homophobic, transphobic, xenophobic, etc, harrasing or bullying other players, they should be permanently banned.

## Using commands for personal gain or aiding players by cheating
- Commands should not be used for person gain or to cheat for other players.
- This includes, teleporting yourself or others, using open inventory to transfer items between players or stealing from people using this, reading personal content E.g. a book and quill inside their inventory, etc.
- Do not use your status as admin or your ability to perform commands as a way to exploit other people.
- There are however a few rare cases where they may be exceptions to a few of these.

## Exceptions
- The End Fight Event or similar, during this event you may teleport latecomers to the stronghold in order to start the event on time.
- You may give players items back from creative or xp via commands if and only if they die to a bug. (If using a graves feature, the grave must also have not spawned or be somewhere inaccessible due to the bug).
- You can transfer items between players using openinv only for the purposes of returning stolen items.

## Coreprotect
- Screenshot logs as evidence to prevent to the admin team, useful in discussions of punishments and in case somebody tries to dispute their ban and claim you falsely accused them.
- Do not give players access to the inspect command, many people think they should have this but it leads to players taking matters into their own hands which usually ends up worse.
- Only rollback when necessary.
- Rollback should be for griefing only, not for creeper explosions.
- Prevent duped items when rolling back, if you are rolling back an area with items in containers ensure players are not getting duplicate items, this can occur if a player gets griefed, takes out items from a chest after the grief and then the chest gets rolled back, now the player has the items they took back and the rolled back ones in the container.
- The same goes for blocks, if blocks get blown up they may drop, when rolling back the blocks are replaced but the player may have picked up the dropped blocks.

## Open Inv
- Do not use this to transfer items between players, read personal content such as book and quill or steal items, Do not move players items in their inventory to mess with them.
- In most cases you should not need to take items out of a players inventory, however unless you have a shulker preview mod such as shulkerbox tooltip, you will need to place shulkers to check contents. If you can get the mod use this instead, if you do have to place them make sure to do this whilst the player is offline and put the shulkers back in the same spot afterwards.
- Screenshot inventories or enderchests as proof of duping or stealing or xray, it can be hard to prove these but by looking at play time to see if the quantity of a certain item obtained is realistic and combining other techiniques such as spectator mode to find xray tunnels and inspector to check who dug those tunnels or who took from a chest.
- Do not use this to plant evidence on players.

## Vanish
- Vanish should only be used when you have reason to believe someone is cheating. Do not spy on people for no reason.
- It should not be used to eavesdrop on players using proximity chat.
- Do not play in vanish mode to avoid responsibilities. E.g. Players needing your help.

# Remember
- Everything you do is logged, If you abuse admin we will be able to find out.
- As an admin it is your job to maintain integrity and only use the commands for the purposes they were intended, If you abuse it, you lose it as simple as that.
- As an admin you are still subject to the normal rules of the server, As well as these additional guidelines.
- If you break the rules as an admin at the very least you will be removed from the admin team, but you may also face standard punishments that can be applied to all players.