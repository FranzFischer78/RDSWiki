---
description: >-
  This page will show you the basic commands to set user ranks and grant/revoke
  permissions.
---

# Managing Player Permissions

First of all, when you make changes to your `ranks_config.json` file, you can simply use the command `perm.reload` to reload the configuration rather than restarting the server everytime.

### How to set user ranks ?

In order to set a user rank you can use the command `perm.setrank`.\
The command syntax is `perm.setrank <username/steamid>`.\
Here's some examples :

```
perm.setrank TeK admin
perm.setrank TeK user
perm.setrank 76561198127513494 vip
```

### How to grant/revoke permissions ?

If you have all your ranks ready but you just want to give a few extra permissions to a specific user, you can use the `perm.grant` and `perm.revoke` commands.\
The commands syntax is `perm.grant <username/steamid> <permission>` (same for revoke)\
Here's some examples :&#x20;

```
perm.grant TeK worldprotection.*
perm.grant TeK *.*
perm.grant TeK myplugin.commands.hi
perm.revoke TeK myplugin.commands.hi
perm.revoke 76561198127513494 myplugin.commands.hi
```

## RDS Built in permissions list

RDS by default have a few permissions available for its built in features.\
Here's the list of them.

* chat.say - Send messages in the chat. Even without it players can use chat commands.
* chat.kick - Admin command used to kick users from the server.
* chat.ban - Admin command used to permanently ban users from the server.
* chat.unban - Admin command used to unban someone with his steamid.
* anticheat.bypass - Bypass the anticheat punishments.
