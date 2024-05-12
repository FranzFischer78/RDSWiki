---
description: >-
  This page will help you to create console commands on the server for your
  plugins.
---

# Creating console commands

Console commands are created through attributes and only works with STATIC methods.\
Here's different examples :&#x20;

```csharp
[ConsoleCommand("hi", "Says hi to you")]
public static string TestCommand()
{
    return "Hi console"
}
```

Console commands can also have arguments with a `string[] args` parameter as shown below.

```csharp
[ConsoleCommand("mycommand")]
public static void TestCommand(string[] args)
{
    // Do your stuff with the args string array. (does not include the initial command)
}
```
