---
description: >-
  This page will help you with checking if a player has a said permission or a
  group of permissions with wildcards.
---

# Player Permissions

RDS have class extensions to Network\_Player and CSteamID.\
This means you can just call for example class.HasPermission() on them.\
Examples :

```csharp
Network_Player player;
if(player.HasPermission("worldprotection.breakblocks")){
    // The player have the permission.
}else{
    // The player does not have the permission.
    // Here you might want to send them a chat message saying they don't have access.
}
```

Permissions also supports wildcards, which means if a plugin have all its permissions starting with `worldprotection` for example, you can just give all permissions with `worldprotection.*`.\
Example :&#x20;

```csharp
Network_Player player;
if(player.HasPermission("worldprotection.test")){
    // This will be true in any of the following cases :
    // The user have worldprotection.* permission.
    // The user have *.* permission.
    // Or the user just have worldprotection.test permission.
}
```
