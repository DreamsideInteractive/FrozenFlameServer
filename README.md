# Frozen Flame - Dedicated Server

You will need a static (public) IP address, so people will be able to connect to your server.

#  Installation via SteamCMD

You can use [SteamCmd](https://developer.valvesoftware.com/wiki/SteamCMD) tool to download a server.

Use the next AppID `1348640`

#  Download for Windows

Please download the archive from GitHub and unpack it.

You can also try to find `Frozen Flame - Dedicated server` in your Steam library (should be available soon).

# Installation on Windows

Open a folder of Dedicated server and launch `FrozenFlameServer.exe` with `-log` command line argument. 
After that a game console will be shown. You can try to add it to your game private servers list with `127.0.0.1` IP by default (for local tests).

# Installation on Linux
Use the next example to install the game server on Linux:
```
1.    adduser steam
2.    passwd steam
3.    dnf install glibc.i686 libstdc++.i686 tmux screen -y
4.    su - steam
5.    curl -sqL "https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz" | tar zxvf -
6.    force_install_dir ./frozen_flame/
7.    login anonymous
8.    app_update 1348640 validate
9.    quit
```

# Command line arguments

`-log` - Shows a server console

`-LOCALLOGTIMES` - Use a local timezone 

`-MetaGameServerName=CoolServer` - Set server name

`RconPassword=password` - Set Rcon password

`RconPort=` - Set Rcon port

# Configuration file
Create a `Game.ini` file at:

For Windows: `Your Dedicated Server Folder\FrozenFlame\Saved\Config\WindowsServer` folder.

For Linux: `Your Dedicated Server Folder\FrozenFlame\Saved\Config\LinuxServer` folder.

Here is an example of `Game.ini` server config file:

```
[/Script/Engine.GameSession]
MaxPlayers=10
ServerPassword=""

[/Script/FrozenFlame.GameBalance]

# Enable PVP for non-friends
bFreePVP=True

# How long a day lasts
DurationOfDay=3600


# Health after death
HealthAfterRespawn=0.5

# Restore health on level up
bRestoreHealthOnLevelUp=True

# Stamina cost at jumping
JumpStaminaCost=6

# Stamina cost at sprinting
SprintStaminaCost=1

# Loss of armor durability after death
ArmorDurabilityReducementAfterDeath=25

# Weapon durability loss speed
DefaultWeaponDurabilityCost=0.5


# Allow to teleport with overweight
bIsAllowedToTeleportWithOverweight=False

# Allow to fly with overweight
bIsAllowedToGlideWithOverweight=False


# Drop of items after level X
MinimalLevelToDropItemAfterDeath=2147483647

# Drop equipped items after death
bDropEquippedItems=False

# Drop equipable items after death
bDropEquipableItems=False

# Drop food on death
bDropFoodItems=False


#Flame rate from everything
FlameRate=1

#Player damage multiplier
PlayerDamageMultiplier=1

#Monsters health multiplier
MonstersHealthMultiplier=1

#Monsters damage multiplier
MonstersDamageMultiplier=1



#Bulding without material costs
bNoModuleCost=False

#Building without restrictions
bLimitlessSupport=False

#Bulding without decay
bInvulnerableModules=False


[/Script/FrozenFlame.DecaySubsystemSettings]
#A minimum durability that keeps after weather decay system damage
MinDurability=0.300000
```

# RCON

COMING SOON

# F.A.Q.

### Disconnecting from server after 20-30s
Make sure that your server supports `EasyAntiCheat` and players using it as well.
It should be in the end og server log right after start `LogEOSAnalytics: Start Session (User: ...)`

If for some reason it doesn't work - players can play on your dedicated server only without EasyAntiCheat (a second option on Steam game start).

### Where to find the game save files?
The default location for save files are:
`Frozen Flame - Dedicated Server\FrozenFlame\Saved\SaveGames`

### Which ports might be required?
Default ports list:
```
25575
27015/udp
27015
7777/udp
7777
```
