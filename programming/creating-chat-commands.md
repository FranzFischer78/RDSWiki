---
description: This page will help you to create chat commands in your plugins.
---

# Creating chat commands

Chat commands are created through attributes and only works with STATIC methods.\
Here's different examples :&#x20;

```csharp
[ChatCommand("hi", "Says hi to you")]
public static string TestCommand(Network_Player player)
{
    return "Hi " + player.GetName();
}
```

You can add permissions to command natively.

```csharp
// The last argument is a permission, this will make the command only available
// to users with the said permission granted.
[ChatCommand("hi", "Says hi to allowed users", "myplugin.commands.hi")]
public static string TestCommand(Network_Player player)
{
    return "Hi " + player.GetName();
}
```

You can also just make it void and do your own stuff without sending a message to the user.

```csharp
[ChatCommand(name:"hi",docs:"a description",permission:"myplugin.hicommand")]
public static void TestCommand(Network_Player player)
{
    // Do your stuff.
}
```

Chat commands can also have arguments with a `string[] args` parameter as shown below.

```csharp
[ChatCommand("mycommand")]
public static void TestCommand(Network_Player player, string[] args)
{
    // Do your stuff with the args string array. (does not include the initial command)
}
```
