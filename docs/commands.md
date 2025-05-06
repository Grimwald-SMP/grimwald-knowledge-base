# 🛡️ **Commands and Permissions**  

This document outlines the **admin commands** used on the server, how to use them, and the different **permission groups** assigned to players.  

---

# **1. Vanilla Commands**  

These are built-in Minecraft commands available to admins:  

- **`/ban <username>`** – Bans a player from the server.  
- **`/kick <username>`** – Kicks a player from the server (they can rejoin immediately).  
- **`/tp <your username> <destination or username>`** – Teleports you to a player or specific location.  
- **`/restart`** – Restarts the server without data loss. Use this if the server is experiencing severe lag. Before restarting, check with other players to confirm the issue isn't client-side.  
- **`/tps`** – Displays the server's **ticks per second (TPS)**, a key performance metric:  
  - **20 TPS** = Ideal performance.  
  - **Below 15 TPS** = Consider restarting the server.  
  - **If frequent low TPS persists** = Hardware upgrades may be required.  

---

# **2. Datapack & Plugin Management**  

## **Datapack Commands**  

- **Never use `/reload`** – This can break plugins and cause server instability.  
- **`/datapack list`** – Lists all installed datapacks, showing which are enabled/disabled.  
- **`/datapack enable <datapack_name>`** – Enables a specific datapack.  
- **Installing Plugins:** Requires a **full server restart** (`/restart`) or using the **server console**. Note that depending on the server setup, `/restart` may shut down the server without restarting it.  

---

# **3. Plugin Commands**  

## **CoreProtect**

- **`/co i`** – Toggles inspector mode:  
  - **Right-click** = Check block interactions.  
  - **Left-click** = Check chest/container transactions.  
- **`/co l <page_number>`** – Select a page to view in logs from inspector mode.  
- **`/co rollback <radius> <time>`** – Rolls back an area to a previous state.
  - Use log timestamps to determine the rollback time.
  - Be aware that some redstone machines (e.g., flying machines) may break when rolled back.  

**Optional rollback filters:**  
- **`<username>`** – Rollback actions from a specific user.  
- **`<include items>`** – Specify items/blocks to restore.  
- **`<exclude items>`** – Specify items/blocks to ignore.  
- **`<action>`** – Rollback only certain actions.

## **OpenInv**

- **`/oi <player_name>`** – Opens a player's inventory (even if offline). Useful for detecting stolen or illegally obtained items.  
- **`/oe <player_name>`** – Opens a player's Ender Chest (even if offline). Another place to check for cheats/dupes.  

## **Vanish**

- **`/vanish`** – Toggles invisibility and removes the player from the online list. Useful for monitoring players discreetly. Can be combined with spectator mode (`/gamemode spectator`) for easier movement.  

---

# **4. Command Usage Guidelines**  

For specific instructions on command usage and staff protocols, refer to the **[Staff Guidelines](staff-guidelines.md)**.  

---

# **5. Permission Groups**  

The server has different permission levels we use these need set up with a permissions manager plugin (We usually use **Luckperms**) based on responsibility and trust:  

- **Whitelister** – Trusted non-staff members who can **add/remove players from the whitelist**. **(Use caution when assigning this role to prevent abuse.)**  
- **Inspector** – Entry-level staff who are limited to **whitelisting players, inspecting logs, and issuing temporary bans** who must consult higher staff before permanent ban.  
- **Staff** – Full moderation access, including all commands listed in this document.  
- **Op (Operator)** – Highest permission level, typically reserved for the **owner(s)**. Operators have unrestricted access to all server commands, often used for technical maintenance. **(Very few players should have this role.)**  

---