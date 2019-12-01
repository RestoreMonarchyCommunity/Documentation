<img src="/assets/images/Challenge.png" width="150" height="150" />

Plugin Name: **Challenge**  
Creator: [**MCrow**](steamcommunity.com/id/restoremonarchy)  
Creation Date: **2019-11-29**  
Price: **$7**  
Buy: [**ImperialPlugins**](https://imperialplugins.com/Products/Challenge)
Video Preview: [**Youtube**](https://youtu.be/zGa1GaED9hQ)

## About Plugin
Challenge plugin allows players to chellenge each other for cash. Player who kills gets the others bet.

## Features
* Players can challenge each other using a command
* Challenge times out after configurable period (3 minutes by default)
* Bets are automatically refund on challenge timeout and server shutdown 
* Uses Uconomy for bets


## Commands
**/challenge** *<player> <bet>* – Challenges `player` for `bet`    
**/challenge accept** – Accepts most recent request  
```
<Permission Cooldown="0">challenge</Permission>
```

## Configuration
```xml
<?xml version="1.0" encoding="utf-8"?>
<ChallengeConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <MessageColor>yellow</MessageColor>
  <ChallengeValidMinutes>3</ChallengeValidMinutes>
  <AnnounceWinner>true</AnnounceWinner>
</ChallengeConfiguration>
```

## Translations
```xml
<?xml version="1.0" encoding="utf-8"?>
<Translations xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Translation Id="ChallengeFormat" Value="Usage: /challenge &lt;player&gt; &lt;bet&gt;" />
  <Translation Id="ChallengeRequest" Value="{0} has challenged you with bet on {1} credits!" />
  <Translation Id="ChallengeYourself" Value="You cannot challenge yourself" />
  <Translation Id="ChallengeAlreadyIn" Value="You are already in challenge against {0}" />
  <Translation Id="ChallengeNotEnough" Value="You don't have enough credits to bet" />
  <Translation Id="ChallengeNoPending" Value="There aren't any pending challenges to you" />
  <Translation Id="ChallengeStart" Value="Your challenge against {0} has started. Winner gets {1} credits!" />
  <Translation Id="ChallengeWin" Value="You have won a challenge against {0} and received {1} bet!" />
  <Translation Id="ChallengeLose" Value="You have lost a challenge against {0} and lost {1} bet!" />
  <Translation Id="ChallengeTimeout" Value="Your challenge against {0} timed out! Your {1} bet goes back to you!" />
  <Translation Id="ChallengeShutdown" Value="Your challenge against {0} has has been canceled due to server shutdown!" />
  <Translation Id="ChallengeSuccess" Value="Successfully sent a challenge request to {0} on {1} bet!" />
  <Translation Id="ChallengeAnnouncement" Value="{0} won a challenge against {1}!" />
</Translations>
```