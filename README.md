# Frozen Flame - Dedicated Server

You will need a static (public) IP address, so people will be able to connect to your server.

### You will also need to open next ports:
!!!!!

### Recommended system requirements:
!!!!

№## Download
AppID for SteamCMD: `1348640`

##  Installation via Steam Client
First, you need to find "Frozen Flame - Dedicated server in your Steam library. 

Find `FrozenFlameServer.exe` and start it with `-log` command line argument. After that a game console will be shown.

## Installation via Linux
Install SteamCMD:
```
1.    adduser steam
2.    passwd steam
3.    dnf install glibc.i686 libstdc++.i686 tmux screen -y
4.    su - steam
5.    curl -sqL "[https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz](https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz)
" | tar zxvf -
6.    force_install_dir ./frozen_flame/
7.    login anonymous
8.    app_update 1348640 validate
9.    quit
```

## Comman line arguments

`-log` - Shows a server console
`-LOCALLOGTIMES` - Use a local timezone 

## Configuration file
To configuration a server you should create a `Game.ini` filt at `Your Dedicated Server Folder\FrozenFlame\Saved\Config\WindowsServer` folder.

Here is an example of config file:

```
[/Script/FrozenFlame.GameBalance]
#Enable PVP
bFreePVP=False

#How long a day lasts
DurationOfDay=3600

#Stamina cost at jumping
JumpStaminaCost=4

#Stamina cost at sprinting
SprintStaminaCost=3

#Stamina cost at swimming
SwimStaminaCost=0

#Multiplycator of weight max
InventoryLimitOverweightFactor=5

#Drop of items after level X
MinimalLevelofDropItemAfterDeath=1

#Drop equipped items on death
bDropEquippedItems=True
#Drop equipable items on death
bDropEquipableItems=True
#Drop food on death
bDropFoodItems=True

#lose on durability on death
ArmorDurabilityReducementAfterDeath=0

#Health after death
HealthAfterRespawn=1.0

#Bulding without material costs
bNoModuleCost=True

#Building without restrictions
bLimitlessSupport=True

#Bulding without decay
bInvulnerableModules=True

#Unlock all recipes
bUnlockAllRecipes=True

[/Script/FrozenFlame.FGameMode]
bEnableCheats=True
```

## RCON

COMING SOON

## Save files
The default location for save files are:
`Frozen Flame - Dedicated Server\FrozenFlame\Saved\SaveGames`

## F.A.Q.

### Disconnecting from server after 20-30s
Make sure that your server supports `EasyAntiCheat` and players using it as well.
It should be in the end og server log right after start `LogEOSAnalytics: Start Session (User: ...)`

If for some reason it doesn't work - players can play on your dedicated server only without EasyAntiCheat (a second option on Steam game start).
