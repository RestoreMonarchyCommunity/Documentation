<img src="/assets/images/Moderation.png" width="150" height="150" />

Plugin Name: **Moderation**  
Creator: [**MCrow**](steamcommunity.com/id/restoremonarchy)  
Creation Date: **2019-06-30**  
Price: **$10**  
Buy: [**ImperialPlugins**](https://imperialplugins.com/Products/Moderation)

## About Plugin
Moderation is an advanced and optimized plugin for punishing and checking players.

## Features
* It's optimized to never crash or delay your server by doing all outside requests on different threads
* You can configure it to send Discord webhook message whenever someone gets banned, kicked, warned or unbanned
* It has all of the GlobalBan features and has a checkowner command
* Unban messages are automatically sent when ban expires
* Stores players' data long with the code of a country they connect from

## Commands
**/ban** *<player/steamID> [reason] [duration]* – Bans specified `player` for `duration` with `reason`.
``` 
<Permission Cooldown="0">ban</Permission>
```
**/unban** *<player/steamID>* – Removes specified `player` latest ban.
``` 
<Permission Cooldown="0">unban</Permission>
```
**/bans** *[player/steamID]* – Displays a list of bans (optional only the `player` bans).
``` 
<Permission Cooldown="0">bans</Permission>
```
**/kick** *<player/steamID> [reason]* – Kicks specified `player` for `reason`.
``` 
<Permission Cooldown="0">kick</Permission>
```
**/warn** *<player/steamID> [reason]* – Warns specified `player` for `reason`.
``` 
<Permission Cooldown="0">warn</Permission>
```
**/checkowner** – Check's the owner of barricade/structure/locked vehicle.
``` 
<Permission Cooldown="0">checkowner</Permission>
```

## Configuration
```xml
<?xml version="1.0" encoding="utf-8"?>
<ModerationConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <ConnectionString>Server=127.0.0.1;Database=unturned;Uid=root;Password=YOURPASSWORD;</ConnectionString>
  <Webhooks>
    <DiscordWebhook WebhookType="Ban" WebhookUrl="WEBHOOK_URL" WebhookColor="ff0000">
      <MessageFormat>Name: {name}, SteamID: {steamid}, Punisher: {punisher}, Duration: {duration}, Reason: {reason}</MessageFormat>
    </DiscordWebhook>
    <DiscordWebhook WebhookType="Kick" WebhookUrl="WEBHOOK_URL" WebhookColor="f06c00">
      <MessageFormat>Name: {name}, SteamID: {steamid}, Punisher: {punisher}, Reason: {reason}</MessageFormat>
    </DiscordWebhook>
    <DiscordWebhook WebhookType="Warn" WebhookUrl="WEBHOOK_URL" WebhookColor="ffff00">
      <MessageFormat>Name: {name}, SteamID: {steamid}, Punisher: {punisher}, Reason: {reason}</MessageFormat>
    </DiscordWebhook>
    <DiscordWebhook WebhookType="Unban" WebhookUrl="WEBHOOK_URL" WebhookColor="00ff33">
      <MessageFormat>Name: {name}, SteamID: {steamid}, Unbanner: {punisher}</MessageFormat>
    </DiscordWebhook>
  </Webhooks>
  <RefreshTime>50000</RefreshTime>
  <RequireReason>true</RequireReason>
  <MessageColor>grey</MessageColor>
</ModerationConfiguration>
```

## Translations
```xml
<?xml version="1.0" encoding="utf-8"?>
<Translations xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Translation Id="BanAnnouncement" Value="{0} was banned by {1} for {2} for {3}!" />
  <Translation Id="BanMessage" Value="[BAN] Reason: {0} Time Left: {1}" />
  <Translation Id="BansLimit" Value="You can't view the list of all bans in-game, you must log into console or use the website" />
  <Translation Id="BansLine" Value="BanID: {0} PlayerName: {1} PlayerId: {2} PunisherName: {3} PunisherId: {4}" />
  <Translation Id="BansNone" Value="There is no bans" />
  <Translation Id="UnbanAnnouncement" Value="{0} was unbanned!" />
  <Translation Id="UnbanFail" Value="{0} doesn't have any active ban." />
  <Translation Id="KickAnnouncement" Value="{0} was kicked by {1} for {2}" />
  <Translation Id="WarnAnnouncement" Value="{0} was warned by {1} for {2}" />
  <Translation Id="CheckownerFail" Value="You are not looking at any barricade, structure or locked vehicle." />
  <Translation Id="CheckownerSuccess" Value="Name: {0} | SteamID: {1} | IsBanned: {2}" />
  <Translation Id="RequireReason" Value="You must specify a reason!" />
</Translations>
```

## FAQ

#### How to customize Discord webhhok embed  

<img src="/assets/images/moderation/kick-embed.png" style="max-width: 40%; min-width: 300px;" />  
Each of DiscordWebhook in the configuration file has a MessageFormat property.
```xml
<DiscordWebhook WebhookType="Kick" WebhookUrl="WEBHOOK_URL" WebhookColor="f06c00">
    <MessageFormat>Name: {name}, SteamID: {steamid}, Punisher: {punisher}, Reason: {reason}</MessageFormat>
</DiscordWebhook>
```
Each of the embed field has a name eg. `SteamID:` or `Punisher` and value where you can use variables eg. `{steamid}` or `{punisher}`.  
Available variables for each punishment types:  

* Ban: `name`, `steamid`, `punisher`, `duration`, `reason`
* Unban: `name`, `steamid`, `punisher`
* Kick & Warn: `name`, `steamid`, `punisher`, `reason`

*Remember to include variables in semicolons `{}`*  
You can also use Discord markdown in the values of the field, so for example to have a player name as url to his steam profile do like this
```xml
<DiscordWebhook WebhookType="Kick" WebhookUrl="WEBHOOK_URL" WebhookColor="f06c00">
    <MessageFormat>Name: [{name}](https://steamcommunity.com/profiles/{steamid}), SteamID: {steamid}, Punisher: {punisher}, Reason: {reason}</MessageFormat>
</DiscordWebhook>
```

#### Where can I get WebhookUrl
To have get a Webhook URL you must first create a webhook on your Discord guild. You can do that by going to your `Server Settings > Webhooks > Create Webhook`     
<img src="/assets/images/moderation/discord-modal.png" style="max-width: 40%; min-width: 300px;" />  
Then you should have a modal like one above at the button you'll see Webhook URL.  
You copy it and Save a webhook and then fill the configuration file with your webhook URL.  
You can have multiple webhooks to each punishment message type to different channels and with different icon & name.   

#### How to use Ban command
The syntax of a ban command is `/ban <player/steamID> [reason] [duration]`.  

| Parameter      | Description  |
------------- | -----------
| player/steamID | If the player you want to ban is on the server you can use his character name to ban him, otherwise you have to use his steamID.  |
| reason | Reason should be included between the quotes `""` if it's more than 1 word length, it's optional parameter unless you set RequireReason to true in the plugin's configuration.  |
| duration | Duration can be formatted like this `1d` - 1 day, `1h` - 1 hour, `1m` - 1 minute, `1s` - 1 second, leave empty if you want to permanently ban someone. |

See the usage exmaples below
```
/ban mcrow "breaking rules" 1d 20m 
```
This will ban player with name mcrow for breaking rules for 1 day and 20 minutes
```
/ban 76561198285897058 "abusing their powers" 7d 20h 30m 30s
```
This will ban player with steamid 76561198285897058 for abusing their powers for 7 days 20 hours 30 minutes and 30 seconds
```
/ban braian "making endless loops"
```
This will permanently ban braian for making endless loops