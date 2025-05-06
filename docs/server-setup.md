# 🛠️ **Server Setup**

This document provides a clear and concise guide for setting up a Minecraft server. It is written specifically for Grimwald staff but is applicable to anyone using a Minecraft hosting services.

---

# **1. Preparing the Server Environment**

## **Hosting Provider**
- We use **Pebblehost** for hosting the Grimwald server.
- Login to the [Pebblehost Panel](https://panel.pebblehost.com/)
- Ensure you are managing the correct server instance.

## **Loader Config**
- Navigate to PebbleHost Loader
- Enable Auto Reboot on Crash
- Ensure Java Version is set to automatically detect.
- If you face any issues related to java version later on you may need to set this to the correct type for your server's jar.

## **Selecting the Server Type**
- Turn off the server.
- Navigate to the **"Jar Manager"** section in the panel.
- Choose the latest stable version of **Paper** that matches the desired Minecraft version.
- If a new version has recently came out, check the [PaperMC Website](https://papermc.io/downloads/paper) and ensure there is a stable build for the version you want to use.
- **Experimental versions** may appear on the server hosting site, but it is up to you if you want to use those or wait for a full release version. **Experimental Builds may have bugs!**
- Click **Install Jar** to apply the changes.
- Restart the server to install the server software setup.

## **Custom Jar**
- If you want a different jar other than paper you may be able to follow a similar process to above, just selecting the jar you want.
- If the jar you want is not listed you will have to do it yourself.
- Download the Jar you want from the official website of that server software, E.g. Fabric, Forge.
- You made or may not need to download the official vanilla **server** minecraft jar for the same game version.
- Zip the jar file(s) up and upload them to the server.
- Right click the zipped folder and choose unarchive. You can now delete the zipped folder.
- Navigate to settings, and in the section that says jarfile, change the jarfile name to the name of the custom jar you uploaded.
- Restart the server to install the server software setup.

---

# **2. Configuring Server Properties**

- Open the **"File Manager" and then "server.properties" file.
- Ensure these values are set:
  - `difficulty=hard`
  - `gamemode=survival`
  - `motd=Grimwald SMP S<Season Number>`
  - `online-mode=true` //Disabling this is allows anyone to join the server bypassing authentication, never disable it.
  - `pvp=true`
  - `=0` //This makes it so there is no spawn protection, you may want to protect a little area depending on what is at spawn.
- You can optionally change other values but ensure you know exactly what they are doing and what effect they will have.
- The only other ones we ever tend to change are spawn protection, and those related to server resource packs.
- Save and restart the server after making changes.
- If you want to use a specific seed you can do so in the `seed=` part of the server.properties.

---

# **3. Server Management**

## **Worlds**
- If using a random seed or specific seed then the server will generate this for you on restart
- If starting with a pre-generated world:
  - Ensure your worlds are named as `world`, `world_nether`, and `world_the_end` for paper. If using fabric you will need store the nether and end inside the world folder as DIM-1 and DIM1 respectively.
  - Zip the world folder(s), upload the zip and then right click and unarchive. You can now delete the zipped folder.
  - Ensure the **level-name** in `server.properties` matches your main world folder name.

## **Paper Settings**
- Paper will generate the `paper.yml`, `spigot.yml`, and `bukkit.yml` files on first run.
- Paper patches some things that many players consider features, you can enable some of these again via these config files.

- Once you have these settings as you want them and the world in place (if using a custom one), restart the server.

---

# **4. Whitelist and Operators**

- Ensure `white-list=true` in `server.properties`.
- Add approved players to the whitelist using either the console or by uploading whitelist.json file.
- Example command:
```
whitelist add PlayerName
```

## **Adding Operators (Owner)**
- Use the following command in the console:
```
op PlayerName
```
- Operators have full command access, so ideally only one owner should be granted this status.

---

# **5. Plugins and Datapacks Installation**

- For instructions on installing and configuring plugins, [see the Plugins Setup guide](plugins.md).
- For instructions on installing datapacks, [see the Datapacks guide](datapacks.md).

---

# **6. Scheduled Tasks**

- You may want to set up scheduled tasks for server restarts, This helps with performance.
- On the PebbleHost Panel, Go to "Scheduled Tasks" and press "Create Schedule"
- Call it "Restart" and you can just use the AI feature to generate the schedule which will format it correctly. E.g. "Everyday at 11.30pm" (Aim for half an hour before you want the reset)
- Open this schedule and add the following tasks:
  - Send Command, `say "Server restarting in 30 minutes`, Continues on failure.
  - Send Command, `say "Server restarting in 15 minutes`, Continues on failure, 900s later.
  - Send Command, `say "Server restarting in 5 minutes`, Continues on failure, 600s later.
  - Send Command, `say "Server restarting in 1 minutes`, Continues on failure, 240s later.
  - Send Power Action, `restart`, 60s later.