<img src="/assets/images/Pickpocket.png" width="150" height="150" />

Plugin Name: **Pickpocket**  
Creator: [**MCrow**](steamcommunity.com/id/restoremonarchy)  
Creation Date: **2019-05-25**  
Price: **Free**  
Download: [**Rocket**](https://harbor.rocketmod.net/Pickpocket)   
Open Source: [**True**](https://github.com/RestoreMonarchyPlugins/Pickpocket)  
Youtube: [**Video**](https://www.youtube.com/watch?v=O_NKTCZmKEg)

## About Plugin
This plugin allows you to steal items from players. To do this, use the animation "Point" and keep the sight for a certain time on your target.

## Features
• Let your players steal items from others instead of killing.   
• Pickpocket must hover the cursor on the victim as long as it’s configured to rob him.  
• Manage who can rob and who cannot be robbed with permissions.  
• You can set an alert for the police in the config, if pocket theft was committed.

## Configuration

```xml
<?xml version="1.0" encoding="utf-8"?>
<PickpocketConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <PickpocketTime>2</PickpocketTime>
  <PickpocketCooldown>30</PickpocketCooldown>
  <NotifyVictimOnSuccess>false</NotifyVictimOnSuccess>
  <NotifyVictimOnFail>true</NotifyVictimOnFail>
  <UsePermissions>false</UsePermissions>
  <NotifyPolice>false</NotifyPolice>
  <PoliceGroupId>police</PoliceGroupId>
</PickpocketConfiguration>
```

## Translations

```xml
<?xml version="1.0" encoding="utf-8"?>
<Translations xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Translation Id="SUCCESS" Value="You successfully robbed {0}" />
  <Translation Id="NOTIFY_SUCCESS" Value="You were robbed by {0}!" />
  <Translation Id="FAIL" Value="You failed to rob {0}" />
  <Translation Id="NOTIFY_FAIL" Value="{0} tried to rob you!" />
  <Translation Id="NOTHING" Value="{0} had nothing to steal!" />
  <Translation Id="COOLDOWN" Value="You have to wait {0} seconds before you can pickpocket again" />
  <Translation Id="NOTIFY_POLICE" Value="{0} stole {1}({2}) from {3}" />
</Translations>
```