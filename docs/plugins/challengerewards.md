<img src="/assets/images/ChallengeRewards.png" width="150" height="150" />

Plugin Name: **ChallengeRewards**  
Creator: [**MCrow**](steamcommunity.com/id/restoremonarchy)  
Creation Date: **2020-01-10**  
Price: **$15**  
Buy: [**ImperialPlugins**](https://imperialplugins.com/Products/ChallengeRewards)  
Workshop: [**UI**](https://steamcommunity.com/sharedfiles/filedetails/?id=1943347710)

## About Plugin
Players receive random periodic quests that plugin tracks and rewards them if they complete them.  

## Note
In future if Unturned updates how UI work plugin will receive update so you'll can have infinite amount of challenges and quests. Currently you should only have x3 challenges first with x3 quests second with x2 and third x1  

## Features
* Players can complete daily, weekly & monthly quests
* Quests can reward in item, vehicle, money or experience
* 16 available quest types!

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
**/challenges** – Displays a UI with challenges and progress
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
  <EffectId>6548</EffectId>
  <AllowDuplicateQuestTypes>false</AllowDuplicateQuestTypes>
  <Challenges>
    <ChallengeModel ChallengeName="Day" ChallengeDurationHours="24" QuestsAmount="3">
      <ChallengeQuests>
        <ChallengeQuestModel QuestType="Kills_Zombies_Normal" Target="10" Reward="EXPERIENCE_200" />
        <ChallengeQuestModel QuestType="Kills_Players" Target="2" Reward="ITEM_363" />
        <ChallengeQuestModel QuestType="Found_Items" Target="8" Reward="VEHICLE_93" />
        <ChallengeQuestModel QuestType="Kills_Animals" Target="3" Reward="ITEM_1364" />
      </ChallengeQuests>
    </ChallengeModel>
    <ChallengeModel ChallengeName="Week" ChallengeDurationHours="168" QuestsAmount="2">
      <ChallengeQuests>
        <ChallengeQuestModel QuestType="Kills_Zombies_Normal" Target="20" Reward="EXPERIENCE_200" />
        <ChallengeQuestModel QuestType="Kills_Players" Target="5" Reward="ITEM_363" />
        <ChallengeQuestModel QuestType="Found_Items" Target="15" Reward="VEHICLE_93" />
        <ChallengeQuestModel QuestType="Kills_Animals" Target="5" Reward="ITEM_1364" />
      </ChallengeQuests>
    </ChallengeModel>
    <ChallengeModel ChallengeName="Month" ChallengeDurationHours="720" QuestsAmount="1">
      <ChallengeQuests>
        <ChallengeQuestModel QuestType="Kills_Zombies_Normal" Target="30" Reward="EXPERIENCE_200" />
        <ChallengeQuestModel QuestType="Kills_Players" Target="15" Reward="ITEM_363" />
        <ChallengeQuestModel QuestType="Found_Items" Target="25" Reward="VEHICLE_93" />
        <ChallengeQuestModel QuestType="Kills_Animals" Target="8" Reward="ITEM_1364" />
      </ChallengeQuests>
    </ChallengeModel>
  </Challenges>
</ChallengeRewardsConfiguration>
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
  <Translation Id="QuestProgress" Value="{0}/{1}" />
  <Translation Id="QuestCompleted" Value="Completed" />
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
