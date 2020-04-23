<img src="/assets/images/ChallengeRewards.png" width="150" height="150" />

Plugin Name: **ChallengeRewards**  
Creator: [**MCrow**](steamcommunity.com/id/restoremonarchy)  
Creation Date: **2020-01-10**  
Price: **$15**  
Buy: [**ImperialPlugins**](https://imperialplugins.com/Products/ChallengeRewards)  
Workshop: [**Steam**](https://steamcommunity.com/sharedfiles/filedetails/?id=2061613655)

## About Plugin
Players receive random periodic quests that plugin tracks and rewards them if they complete them.  

## 1.1 Update Note
ChallengeRewards 1.1 update are mainly optimization improvements (calling database from non-game thread), clean up (cleaned up the code and changed pattern) and two new UIs.

## Features
* Plugin has support for two different UIs  
* Quests can reward in item, vehicle, money or experience
* Quest rewards can be claimed either through UI or automatically given on complete
* 14 available quest types!

| Quest Type      | Description  |
------------- | -----------
| KILLS_ZOMBIES_NORMAL | All zombie kills (except mega)  |
| KILLS_PLAYERS | Player kills  |
| FOUND_ITEMS | Found items  |
| FOUND_RESOURCES | Gathered resources (chopped trees, mined rocks)  |
| FOUND_EXPERIENCE | Gained experience points |
| KILLS_ZOMBIES_MEGA | Mega zombie kills  |
| DEATHS_PLAYERS | Your (player) deaths  |
| KILLS_ANIMALS | Animal kills  |
| FOUND_CRAFTS | Found crafts (no idea)  |
| HEADSHOTS | Headshots  |
| ARENA_WINS | Arena wins  |
| FOUND_BUILDABLES | Found buildables (picked up structures and barricades I guess)  |
| FOUND_THROWABLES | Found throwables (grenades maybe)  |
| FOUND_REPUTATION | Gained repoutation |

## Commands
**/challenges** – Displays challenges UI
```
<Permission Cooldown="0">challenges</Permission>
```

## Configuration
```xml
<?xml version="1.0" encoding="utf-8"?>
<ChallengeRewardsConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <HasOldMySQL>false</HasOldMySQL>
  <ConnectionString>Server=127.0.0.1;Database=unturned;Uid=root;Password=Password!123;</ConnectionString>
  <MessageColor>yellow</MessageColor>
  <EffectId>8430</EffectId>
  <AllowDuplicateQuestTypes>false</AllowDuplicateQuestTypes>
  <GiveRewardOnComplete>false</GiveRewardOnComplete>
  <Challenges>
    <ChallengeModel ChallengeName="daily" ChallengePublicName="Daily" ChallengeDurationHours="24" QuestsAmount="3">
      <ChallengeQuests>
        <ChallengeQuestModel QuestType="Kills_Zombies_Normal" Target="10" Reward="EXPERIENCE_200" />
        <ChallengeQuestModel QuestType="Kills_Players" Target="2" Reward="ITEM_363" />
        <ChallengeQuestModel QuestType="Found_Items" Target="8" Reward="VEHICLE_93" />
        <ChallengeQuestModel QuestType="Kills_Animals" Target="3" Reward="ITEM_1364" />
      </ChallengeQuests>
    </ChallengeModel>
    <ChallengeModel ChallengeName="weekly" ChallengePublicName="Weekly" ChallengeDurationHours="168" QuestsAmount="2">
      <ChallengeQuests>
        <ChallengeQuestModel QuestType="Kills_Zombies_Normal" Target="20" Reward="EXPERIENCE_200" />
        <ChallengeQuestModel QuestType="Kills_Players" Target="5" Reward="ITEM_363" />
        <ChallengeQuestModel QuestType="Found_Items" Target="15" Reward="VEHICLE_93" />
        <ChallengeQuestModel QuestType="Kills_Animals" Target="5" Reward="ITEM_1364" />
      </ChallengeQuests>
    </ChallengeModel>
    <ChallengeModel ChallengeName="monthly" ChallengePublicName="Monthly" ChallengeDurationHours="720" QuestsAmount="1">
      <ChallengeQuests>
        <ChallengeQuestModel QuestType="Kills_Zombies_Normal" Target="30" Reward="EXPERIENCE_200" />
        <ChallengeQuestModel QuestType="Kills_Players" Target="15" Reward="ITEM_363" />
        <ChallengeQuestModel QuestType="Found_Items" Target="25" Reward="VEHICLE_93" />
        <ChallengeQuestModel QuestType="Kills_Animals" Target="8" Reward="ITEM_1364" />
      </ChallengeQuests>
    </ChallengeModel>
  </Challenges>
```

## Translations
```xml
<?xml version="1.0" encoding="utf-8"?>
<Translations xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Translation Id="NewChallenge" Value="You got new {0} challenge!" />
  <Translation Id="ReceiveExperience" Value="You received {0} experience for completing quest!" />
  <Translation Id="ReceiveMoney" Value="You received {0} money for completing quest!" />
  <Translation Id="ReceiveItem" Value="You received {0} item for completing quest!" />
  <Translation Id="ReceiveVehicle" Value="You received {0} vehicle for completing quest!" />
  <Translation Id="MoneyReward" Value="Reward: {0} credits" />
  <Translation Id="ItemReward" Value="Reward: {0}" />
  <Translation Id="VehicleReward" Value="Reward: {0}" />
  <Translation Id="ExperienceReward" Value="Reward: {0} experience" />
  <Translation Id="NoChallenges" Value="You don't have any challenge" />
  <Translation Id="UI_Header" Value="Challenges" />
  <Translation Id="UI_Next" Value="Next" />
  <Translation Id="UI_Prev" Value="Prev" />
  <Translation Id="UI_Close" Value="Close" />
  <Translation Id="UI_QuestProgress" Value="{0}/{1}" />
  <Translation Id="UI_QuestCompleted" Value="Completed" />
  <Translation Id="UI_QuestClaim" Value="Claim" />
  <Translation Id="UI_Page" Value="{0}/{1}" />
  <Translation Id="UI_Simple_Title" Value="{0} Quest {1}" />
  <Translation Id="UI_Simple_Progress" Value="Progress: {0}/{1}" />
  <Translation Id="KILLS_ZOMBIES_NORMAL" Value="Kill Zombies" />
  <Translation Id="KILLS_PLAYERS" Value="Kill Players" />
  <Translation Id="FOUND_ITEMS" Value="Find Items" />
  <Translation Id="FOUND_RESOURCES" Value="Find Resources" />
  <Translation Id="FOUND_EXPERIENCE" Value="Find Experience" />
  <Translation Id="KILLS_ZOMBIES_MEGA" Value="Kill Mega Zombies" />
  <Translation Id="DEATHS_PLAYERS" Value="Die" />
  <Translation Id="KILLS_ANIMALS" Value="Kill Animals" />
  <Translation Id="FOUND_CRAFTS" Value="Find Craftings" />
  <Translation Id="FOUND_FISHES" Value="Catch Fishes" />
  <Translation Id="FOUND_PLANTS" Value="Find Plants" />
  <Translation Id="HEADSHOTS" Value="Hit Headshots" />
  <Translation Id="ARENA_WINS" Value="Win Arenas" />
  <Translation Id="FOUND_BUILDABLES" Value="Find Buildables" />
  <Translation Id="FOUND_THROWABLES" Value="Find Throwables" />
  <Translation Id="FOUND_REPUTATION" Value="Gain Reputation" />
</Translations>
```

## FAQ

#### What UI should I use?
You can use any UI you want, but if you want to use main ChallengeRewardsUI (8430) with pagination and tabs, you'll need to make sure you follow these:
* You must have exactly 3 challenges named `daily, weekly, monthly`, so like in default configuration (name is never displayed to player but public name is, so you can translate these to your language)
* If you want to use claim button, make sure you have `GiveRewardOnComplete` disabled
* You can have any amount of quests, that's what pagination is for
