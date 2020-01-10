<img src="/assets/images/LootBoxes.png" width="150" height="150" />

Plugin Name: **LootBoxes**  
Creator: [**MCrow**](steamcommunity.com/id/restoremonarchy)  
Creation Date: **2020-01-10**  
Price: **$10**  
Buy: [**ImperialPlugins**](https://imperialplugins.com/Products/LootBoxes)

## About Plugin
Allows players to gain chests by players by doing different activities. Boxes drop based on chances and give a random item based on chance.

## Features
* Configure custom loot boxes via configuration
* Saves data in MySQL so it can be shared across servers
* LootBoxes can drop with a different probability (1-1000) from different events e.g. zombie kill or resource found
* Lootbox can drop one item picked based on probability (1-1000)

## Commands
**/boxes** – Shows a list of your boxes  
```
<Permission Cooldown="0">boxes</Permission>
```
**/unbox** *<boxID>* – Opens a box `boxID` if you have one  
```
<Permission Cooldown="0">unbox</Permission>
```
**/givebox** *<player> <boxID>* – Gives a box `boxID` to `player`  
```
<Permission Cooldown="0">givebox</Permission>
```


## Configuration
```xml
<?xml version="1.0" encoding="utf-8"?>
<LootBoxesConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <ConnectionString>Server=127.0.0.1;Database=unturned;Uid=root;Password=Password!123;</ConnectionString>
  <LootBoxes>
    <LootBox BoxId="epic" Name="Epic Chest" PlayerKillChance="50" ZombieKillChance="150" MegaZombieKillChance="1000" FoundPlantsChance="200" FoundResourcesChance="500">
      <Rewards>
        <LootBoxReward ItemId="363" Chance="30" />
        <LootBoxReward ItemId="254" Chance="50" />
        <LootBoxReward ItemId="17" Chance="80" />
        <LootBoxReward ItemId="519" Chance="20" />
      </Rewards>
    </LootBox>
  </LootBoxes>
  <MessageColor>magenta</MessageColor>
</LootBoxesConfiguration>
```

## Translations
```xml
<?xml version="1.0" encoding="utf-8"?>
<Translations xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Translation Id="Box_Unbox" Value="You received {0} from {1}!" />
  <Translation Id="Box_Found" Value="You got {0}!" />
  <Translation Id="Box_None" Value="You don't have any {0}" />
  <Translation Id="Box_NotFound" Value="Failed to find any box with id {0}" />
  <Translation Id="GiveBox_Success" Value="Successfully gave {0} a {1}!" />
  <Translation Id="GiveBox_Fail" Value="Use /givebox &lt;player&gt; &lt;boxID&gt;" />
  <Translation Id="Unbox_Fail" Value="Use /unbox &lt;boxID&gt;" />
  <Translation Id="Boxes_List" Value="Your boxes:" />
  <Translation Id="Boxes_None" Value="You don't have any box" />
</Translations>
```