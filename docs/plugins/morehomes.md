<img src="/assets/images/MoreHomes.png" width="150" height="150" />

Plugin Name: **MoreHomes**  
Creator: [**MCrow**](steamcommunity.com/id/restoremonarchy)  
Creation Date: **2019-05-22**  
Price: **Free**  
Download: [**Rocket**](https://harbor.rocketmod.net/MoreHomes)  
Open Source: [**True**](https://github.com/RestoreMonarchyPlugins/MoreHomes)

## About Plugin
Allows players to have multiple beds. This plugin can integrate with [Teleportation](https://docs.restoremonarchy/plugins/teleportation)

## Features
* Allows players to have multiple beds
* You can set the delay of teleportation
* Manage max amount of homes by creating permissions
* Restore all beds to the database with a command
* Checks if bed exists before teleporting

## Commands

**/home** *<Name>* – Teleports player to their bed
``` 
<Permission Cooldown="0">home</Permission>
```
**/homes** – Displays a list of player's claimed beds
``` 
<Permission Cooldown="0">homes</Permission>
```
**/destroyhome** *<Name>* – Destroys the bed and removes it from you home list
```
<Permission Cooldown="0">destroyhome</Permission>
```
**/renamehome** *<Name>* *<NewName>* – Changes home's name to a new one
``` 
<Permission Cooldown="0">renamehome</Permission>
```
**/restorehomes** - Restores all beds that are claimed and not in database
``` 
<Permission Cooldown="0">restorehomes</Permission>
```

## Configuration

```xml
<?xml version="1.0" encoding="utf-8"?>
<MoreHomesConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <MessageColor>yellow</MessageColor>
  <DefaultHomeCooldown>20</DefaultHomeCooldown>
  <DefaultHomeDelay>10</DefaultHomeDelay>
  <DefaultMaxHomes>2</DefaultMaxHomes>
  <VIPCooldowns>
    <VIPPermission PermissionTag="morehomes.vip" Value="10" />
    <VIPPermission PermissionTag="morehomes.star" Value="5" />
  </VIPCooldowns>
  <VIPDelays>
    <VIPPermission PermissionTag="morehomes.vip" Value="5" />
    <VIPPermission PermissionTag="morehomes.star" Value="3" />
  </VIPDelays>
  <VIPMaxHomes>
    <VIPPermission PermissionTag="morehomes.vip" Value="3" />
    <VIPPermission PermissionTag="morehomes.star" Value="4" />
  </VIPMaxHomes>
</MoreHomesConfiguration>
```

## Translations

```xml

<?xml version="1.0" encoding="utf-8"?>
<Translations xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Translation Id="HomeCooldownWarn" Value="You have to wait {0} to use this command again" />
  <Translation Id="HomeDelayWarn" Value="You will be teleported to your bed in {0} seconds" />
  <Translation Id="MaxHomesWarn" Value="You cannot have more beds" />
  <Translation Id="NoBedsToTeleport" Value="You don't have any bed to teleport or name doesn't match any" />
  <Translation Id="BedDestroyed" Value="Your bed got destroyed. Teleportation canceled" />
  <Translation Id="WhileDriving" Value="You cannot teleport while driving" />
  <Translation Id="HomeSuccess" Value="Successfully teleported You to your {0} bed!" />
  <Translation Id="HomeList" Value="Your beds: " />
  <Translation Id="NoHomes" Value="You don't have any bed claimed" />
  <Translation Id="DestroyHomeFormat" Value="Format: /destroyhome &lt;BedName&gt;" />
  <Translation Id="HomeNotFound" Value="No home match {0} name" />
  <Translation Id="DestroyHomeSuccess" Value="Successfully destroyed and unclaimed your {0} home!" />
  <Translation Id="RenameHomeFormat" Value="Format: /renamehome &lt;HomeName&gt; &lt;NewName&gt;" />
  <Translation Id="HomeAlreadyExists" Value="You already have a home named {0}" />
  <Translation Id="RenameHomeSuccess" Value="Successfully renamed home {0} to {1}!" />
  <Translation Id="WhileRaid" Value="You can't teleport while in raiding" />
  <Translation Id="WhileCombat" Value="You can't teleport while in combat" />
  <Translation Id="RestoreHomesSuccess" Value="Successfully restored {0} homes!" />
</Translations>
```
