# 🛠️ **Plugins**

This document provides a clear and concise guide for setting up the plugins we use on the server.

---

# **1. Plugins List**

- General:
    - [DiscordSRV](https://modrinth.com/plugin/discordsrv) - Minecraft <-> Discord chat.
    - [Dynmap](https://modrinth.com/plugin/dynmap) - World map.
    - [Chunky](https://modrinth.com/plugin/chunky) - Chunk pre-generation for world map.
    - [HexNicks](https://modrinth.com/plugin/hexnicks) - Set different colored nicknames with /nick or /nick other, E.g. `/nick <#ffffff>Steve`.
    - [Gsit](https://www.spigotmc.org/resources/gsit-modern-sit-seat-and-chair-lay-and-crawl-plugin-1-16-1-21-5.62325/) - Ability to sit anywhere.
    - [SimpleVoicechat](https://modrinth.com/plugin/simple-voice-chat) - Proximity chat.
    - [WelcomeMessage](https://modrinth.com/plugin/simple-welcome-message) - Welcome Message that gets sent when someone joins the game.
    - [BetterMultiplayerSleep](https://modrinth.com/plugin/better-multiplayer-sleep) - Allows players to toggling no sleeping for the night with `/no-sleep`.
    - [PortalLinkHelper](https://modrinth.com/plugin/portal-link-helper) - Immediately sends the link coordinates for a portal once it has been constructed.

- Admin:
    - [Luckperms](https://modrinth.com/plugin/luckperms) - Allows admins to set up permissions groups to allow or deny certain people access to certain commands.
    - [Coreprotect](https://modrinth.com/plugin/coreprotect) - Logging and rollbacks.
    - [SuperVanish](https://www.spigotmc.org/resources/supervanish-be-invisible.1331/) - Allows admins to become invisble.
    - [ProtocolLib](https://www.spigotmc.org/resources/protocollib.1997/) - Required for SuperVanish to work correctly .
    - [OpenInv](https://dev.bukkit.org/projects/openinv) - Allows admins to check inventories or enderchests.
    - [Plan](https://modrinth.com/plugin/plan) - Gathers loads of stats about the server, which can be helpful for admins.

---

# **2. Installation**

1. Download all of the plugins above.
2. Navigate to PebbleHost File Manager/plugins
3. Place all of the downloaded plugin jars in this folder.
4. Restart the server.

- Once the server restarts the plugins will be installed, but some will need configured.
- If the server does not start, check console to see if there any any errors, Plugins usually work across versions but for some plugins you may need a specific version.
- After each edit, press the green "Save Content" button.

---

# **3. Configuration**

- Some plugins have no configuration so will not be listed here.
- Only the config options we use will be documented, any other options you will have to look into yourself.

## **Welcome Message**
- Open plugins/welcomeMessage/config.yml.
- Replace whatever is inside the quotations with `&6Welcome to Grimwald SMP Season 21 %player%` changing the season number to the correct one.

## **Better Multiplayer Sleep**
- Open plugins/BetterMultiplayerSleep/config.yml.
- You can change the default sleep percentage to match whatever you want it to be in game. Usually we stay with 0 though so only one person needs to sleep to skip to day.

## **SuperVanish**
- Open plugins/SuperVanish/config.yml.
- Find the "Fly" section.
- In this section make sure "Enable" is set to `false` and "DisableOnReappear" is set to `true`.

## **DiscordSRV**
- Open plugins/DiscordSRV/config.yml.
- Add the Discord Bot Token in the "BotToken" field.
- Go onto discord and enable developer mode you do not have it enabled already. This allows you to copy channel IDs.
- In the "Channels: {"global" : ""}" insert the ID of channel you want to use in the quotations. Usually `849310724844027941`.
- In the "DiscordInviteLink" insert the permanent link in the quotations. You can find this on discord.

## **Dynmap**
- Open plugins/dynmap/configuration.txt.
- Change the "deftemplatesuffix" to `vlowres`.
- Change "allowwebchat" and "allowchat" to `false`.
- Go into the "Additional Ports" tab on Pebblehost, Click add port. Leave a note stating what this port is for. Then note down the port number.
- Back in the config, change "webserver-port" to the value of the port you just created, usually a four digit number.
- The link can be found at `http://ip:port` where ip is the servers IP and port is the new port you just created and set in the webserver-port option.

## **SimpleVoiceChat**
- Go into the "Additional Ports" tab on Pebblehost, Click add port. Leave a note stating what this port is for. Then note down the port number.
- Open plugins/voicechat/voicechat-server.properties.
- Change "port" to the value of the port you just created, usually a four digit number.

## **Plan**
- Go into the "Additional Ports" tab on Pebblehost, Click add port. Leave a note stating what this port is for. Then note down the port number.
- Open plugins/Plan/config.yml.
- Find the "Webserver" section.
- In this section change "Port" to the value of the port you just created, usually a four digit number.
- Go into the server.properties and ensure the "server-ip" is set to the servers-ip (Without the port).
- Optionally you can enable location tracking which tells you which countries your players are from, To do this:
    - Read the [Geolite2 Eula](https://www.maxmind.com/en/geolite2/eula)
    - In the conig, find the "Data_gathering" section.
    - Change "Geolocations" to `true`
    - Change "Accept_Geolite2_EULA" to true, if you have read and agreed to the terms.
- At the moment anyone with the link can access this site, you could secure it if you wanted to but this is more technical. [Find out more](https://github.com/plan-player-analytics/Plan/wiki/SSL-Certificate-%28HTTPS%29-Set-Up)

Now that all the plugins are configured restart the server again and the configuration should be applied.

---

# **3. Luckperms**

- Although the server is set up luckperms permission groups will need to be added.
- By default luckperms will block most plugin permissions from everyone, You should add some default permissions to the everyone group and create new groups for admin permissions.
- The easiest way to do this is with the editor, run `/lp-editor' from in game, which will open a web editor view.
- Make sure you give everyone permissions to speak and listen with voicechat.
- There are a lot of things you can do with luckperms so rather than describe all of them here you can read the [Wiki](https://luckperms.net/wiki/Web-Editor).

# **4. Pre-Generating The World**

- Chunky can be used to pre-generate chunks. (Quickly load and unload each chunk within a certain area).
- This is useful for dynmap, which cannot render chunks until they have been loaded at least once.
- Run `/chunky radius <radius>` or `/chunky corners ` to set the area.
- Then run `/chunky start` to start the pre-generation task.
- Once this is complete start the dynmap render with `/dynmap fullrender`.
- Warning, the chunky pre-generation task and the dynmap full render task can take a while and whilst they are running server-performance may be significantly worse. You may wish to run these before opening the world up to players or not run them at all and let dynmap render areas as they are explored.