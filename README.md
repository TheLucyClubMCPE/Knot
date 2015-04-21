[![](http://achievecraft.com/cimage/i92/Knot/A+PocketMine+PlugIn/mca.png)](https://github.com/thelucyclubmcpe/knot/releases)
# Knot
A pocketmine plugin to tie servers together. (Like RubberBand, but for the NEW API.)
## Usage
1. Drop the file into your /plugins directory
2. Execute `/stop` in the console
3. Restrat your server with `./start.sh`
4. Configure the proxy, with a lobby, and some other servers you may want to add
5. Type `/server <IP> <PORT>` to join IP with the port PORT or `/join <SERVERNAME:LOBBY>` to teleport to SERVERNAME or LOBBY.

## Configuration
To add a server type `/rs <SERVERNAME> <IP> <PORT> <ROLLBACK IP> [ROLLBACK PORT]`
To add a lobby `/al <IP>`
To start the proxy, type `/proxy --enable`
To connect the proxy type `/proxy --connect <database> <user> <password> <host>` OR `/proxy --add <DIRECTORY>`
_NOTE: When setting a lobby server, use its dynamic internal ip (unless it's external of course) and NOT to 127.0.0.1 because this will send the client to itself, which will crash their game._
__KEY:__

* SERVERNAME - The server servers.yml name
* IP - The IP the client data packet will be sent to
* PORT - The port the client will  be directed to
* ROLLBACK IP - The IP to connect to if the desired server is offline (Default is lobby)
* ROLLBACK PORT - Port to rollback to (Only set if lobby port is not 19132)


### Example Configuration
```
/rs survival 192.168.0.77 16778 127.0.0.1 19132
[INFO] Succesfuly registered server "survival"
/al 192.168.0.96
[INFO] Lobby set to host ip "192.168.0.96"
/proxy --enable
External proxy enabled
/proxy --add C:\users\MrMop43403\Desktop\proxyconnector\proxy.bat
Proxy directory set to "proxyconnector"
```

## FAQ
#### It won't work
This is because one of the following reasons:
1. You used and external IP for an internal server
2. The server port is blocked in the firewall
3. Your servers.yml file is messed up

#### The client gets kicked
This is most likely because you did not set a rollback server.
Re-register the server this time, with a rollback IP and PORT.

#### It says "API Version Not Compatible"
That just means your not on the latest version of PocketMine. You need [PocketMine-MP 1.5](https://github.com/PocketMine/PocketMine-MP/releases)
