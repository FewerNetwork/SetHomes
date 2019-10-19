# SetHomes
A simple homes plugin with the ability to create, delete, and teleport to many different homes. Have the ability to control a blacklist of worlds in which players will be restricted from setting homes. Using the config you can control setting such as a maximum number of homes, teleport cooldown, teleport delay, and their respective messages that get display to the user.
***
# Installation
Simply place the downloaded jar from https://dev.bukkit.org/projects/set-homes into your server plugins folder.
***
# Commands
- **/sethome [HomeName] [HomeDescription]** - This command will allow the issuer to set a home with a given name and description of their choosing at your standing location. If no name and description are given then you will set a default home at your standing location.
- **/home [HomeName]** - This command will teleport the user to the given "HomeName". If no home name is given then the user is teleported to their default set by **/sethome**
- **/home-of [PlayerName] [HomeName]** - This command will allow players with the "homes.home-of" permission to teleport to any players set home. If no home name is provided it will assume the default home as the desired destination.
- **/delhome [HomeName]** - This command will delete the home at the given home name. If no home name is given then it will attempt to remove the default home.
- **/delhome-of [PlayerName] [HomeName]** - This command will allow players with the "homes.delhome-of" permission to delete any players set home. If no home name is given it will assume the default home as the home desired for deletion.
- **/homes [PlayerName]** - This command will list all of the players currently set homes if there are any. Players with the "home.gethomes" permission can use the extra PlayerName parameter to list the homes of a specific player.
- **/blacklist [Add/Remove] [WorldName]** - This command is used to manipulate the world blacklist. If a worlds name is in the blacklist then no players will be allowed to set homes in that world. Type /blacklist to list all worlds in the blacklist
- **/strike** - Have fun admins
***
# Permissions
- **homes.*** - A player given this permission will be allowed all commands under the Set Homes plugin
- **homes.home** - A player with this permission is allowed to teleport to named homes
- **homes.sethome** - A player with this permission is allowed to set named homes
- **homes.strike** - Give the power to others!
- **homes.blacklist_list** - Give the ability to list worlds currently in the blacklist
- **homes.blacklist_add** - Give the ability to add worlds to the blacklist
- **homes.blacklist_remove** - Give the ability to remove worlds from the blacklist
- **homes.gethomes** - Give the ability to list any players active homes
- **homes.home-of** - Give the ability to teleport to one of any players active homes
- **homes.delhome-of** - Give the ability to delete one of any players active homes
- **homes.config_bypass** - A player given this permission can set homes in blacklisted worlds, and doesn't have to wait for cooldown or teleport delays. They will also be able to exceed the max home limit.
***
# Default Config
```yaml
# --------------------------
# 	SetHomes Config	
# --------------------------
# Messages: 
# 	You can use chat colors in messages with this symbol §.
# 	I.E: §b will change any text after it to an aqua blue color.
# 	Color codes can be found here https://www.digminecraft.com/lists/color_list_pc.php
# Time: 
# 	Any time value is based in seconds.
# Things to Note: 
# 	Set any integer option to 0 for it to be ignored.
# 	The max-homes does not include the default un-named home.
# 	Use %s as the seconds variable in the cooldown message.

max-homes: 0
max-homes-msg: §4You have reached the maximum amount of saved homes!
tp-delay: 3
tp-cooldown: 0
tp-cancelOnMove: false
tp-cancelOnMove-msg: §4Movement detected! Teleporting has been cancelled!
tp-cooldown-msg: §4You must wait another %s second(s) before teleporting!
```
