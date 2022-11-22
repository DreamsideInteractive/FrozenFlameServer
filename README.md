[阅读中文版教程](./README_CN.md)

# Frozen Flame - Dedicated Server

You will need a static (public) IP address, so people will be able to connect to your server.

#  Installation via Steam

Find `Frozen Flame - Dedicated server` in your Steam library and install it.
Then click on it and open local files folder.

#  Installation via SteamCMD

You can use [SteamCmd](https://developer.valvesoftware.com/wiki/SteamCMD) tool to download a server.

Use the next AppID `1348640`

# Running on Windows

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
*Thanks to Chester for community support.*

## Example Install and launch files

### Install/Update - Create a .bat  or .sh file with the following contents to install the dedicated server. 

`
"path\to\steamcmd.exe" +force_install_dir "path\to\install\DedicatedServer" +login anonymous +app_update 1348640 validate +quit
`

### Launcher -Create a .bat  or .sh file with the following contents to launch you server. 

`
"path\to\FrozenFlameServer.exe" -log -LOCALLOGTIMES -MetaGameServerName="YOURSERVERNAME" -ip=xxx.xxx.xxx.xxx -Port=YOURPORT -queryPort=YOURPORT -RconPort=YOURPORT -RconPassword=YOURPASSWORD 
`

# Command line arguments

`-log` - Shows a server console

`-LOCALLOGTIMES` - Use a local timezone 

`-port` - Sets custom Game port. This is used by client to connect

`-queryPort` - Sets custom Query Port. Used by Steam to get server info 

`-ip` - Sets your public IP 

`-MetaGameServerName=CoolServer` - Set server name

`-noeac` - Start the game with no EasyAntiCheat (clients also should be started without it)

`RconPassword=password` - Set Rcon password

`RconPort=` - Set Rcon port

# Configuration file
Create a `Game.ini` file at:

For Windows: `Your Dedicated Server Folder\FrozenFlame\Saved\Config\WindowsServer` folder.

For Linux: `Your Dedicated Server Folder\FrozenFlame\Saved\Config\LinuxServer` folder.

Here is an example of `Game.ini` server config file https://github.com/DreamsideInteractive/FrozenFlameServer/blob/main/Game.ini

# RCON

COMING SOON

# F.A.Q.

### Disconnecting from server after 20-30s
Make sure that your server supports `EasyAntiCheat` and players using it as well.
It should be in the end og server log right after start `LogEOSAnalytics: Start Session (User: ...)`

If for some reason it doesn't work - players can play on your dedicated server only without EasyAntiCheat (a second option on Steam game start).

Steam might be also required.

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
### Server Crashes after Tutorial

If you are crashing after the tutorial, install the standard [Steam Client](https://store.steampowered.com/about/) on the server you are hosting from. You simply need to install it and let it update. Once complete you can close it. 
