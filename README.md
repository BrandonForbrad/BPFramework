![Logo](SmallBPLogo.png)

Download BPFramework file and put it under your ServerScriptService

By forbrad

Join my discord: https://discord.gg/2B3vBzqnhT
Youtube Tutorial: https://www.youtube.com/watch?v=3Df70TJZunI
# Roblox BP Framework

This is a simple roblox framework for people who just wanna use a well made framework in roblox studio


# Documentation

Server - Server Modules
Client - Client Modules
Start()
Init()

# Server Networking

```
Server.Post:Client(event,player, ...)
```
Example:
```lua
--Server
local player = game.Players.forbrad --ANY PLAYER
Server.Post:Client("TestEvent", player, "TESTCLIENT")

--Client 
Client.Listen:Connect("TestEvent",function(arg)
    print(arg)
end)

--Output arg: TESTCLIENT
```
# Client Networking
```
Client.Post:Server(event, ...)
```
Example:
```lua
--Client
Client.Post:Server("TestEvent","TESTSERVER")

--Server
Server.Listen:Connect("TestEvent", function(player, arg) 
   print(player.Name, arg)
end)

--Output player, arg: forbrad TESTSERVER
```
# All Network functions

```lua
--Client
Client.Post:Server(event, ...)
Client.Listen:Connect(event, func) [func put function in here]

--Server
Server.Post:Client(event,player, ...)
Server.Post:AllClients(event, ...)
Server.Post:AllClientsExcept(event,player, ...) --[player or {list of players}]
Server.Post:ClientList(event,playerList, ...) --[{list of players}]

Server.Listen:Connect(event, func) --[func put function in here]
```
