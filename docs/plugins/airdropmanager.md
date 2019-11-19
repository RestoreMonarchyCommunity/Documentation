<img src="/assets/images/AirdropManager.png" width="150" height="150" />

Plugin Name: **AirdropManager**  
Creator: [**MCrow**](steamcommunity.com/id/restoremonarchy)  
Creation Date: **2019-05-13**  
Price: **Free**  
Download: [**Rocket**](https://harbor.rocketmod.net/AirdropManager)   
Open Source: [**True**](https://github.com/RestoreMonarchyPlugins/AirdropManager)

## About Plugin
This plugin allows you to set your custom airdrop with the desired loot, as well as set your drop points for airdrop.

## Features
• Plugin is available in both RocketMod 4 and 5 versions.  
• Allows you to create airdrops with custom loot.  
• Allows you to create targets for airdrops or you can use default.  
• Allows you to set up ChatMaster like message (with size, colors, style and icon).  
• Allows you to blacklist unwanted airdrops by id.

## Commands

**/airdrop** – Calls in an airdrop.
``` 
<Permission Cooldown="0">airdrop</Permission>
```
**/whenairdrop** – Shows time left to next airdrop.
``` 
<Permission Cooldown="0">whenairdrop</Permission>
```
**/setairdrop** *<AirdropID>* – Saves you current position as airdrop target.
``` 
<Permission Cooldown="0">setairdrop</Permission>
```

## Configuration

```xml
<?xml version="1.0" encoding="utf-8"?>
<AirdropManagerConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <UseDefaultSpawns>true</UseDefaultSpawns>
  <UseDefaultAirdrops>false</UseDefaultAirdrops>
  <AirdropMessage>{size=17}{color=magenta}{i}Airdrop{/i} is coming!{/color}{/size}</AirdropMessage>
  <AirdropMessageIcon>https://i.imgur.com/JCDmlqI.png</AirdropMessageIcon>
  <AirdropInterval>3600</AirdropInterval>
  <Airdrops>
    <Airdrop AirdropId="1005">
      <Items>
        <AirdropItem ItemId="363" Chance="10" />
        <AirdropItem ItemId="17" Chance="20" />
      </Items>
    </Airdrop>
  </Airdrops>
  <AirdropSpawns>
    <AirdropSpawn AirdropId="1005">
      <Position X="1" Y="1" Z="1" />
    </AirdropSpawn>
  </AirdropSpawns>
  <BlacklistedAirdrops />
</AirdropManagerConfiguration>
```

## Translations
```xml
<?xml version="1.0" encoding="utf-8"?>
<Translations xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Translation Id="Next_Airdrop" Value="Next airdrop will be in {0}" />
</Translations>
```