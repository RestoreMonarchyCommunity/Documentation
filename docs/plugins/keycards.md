<img src="/assets/images/Keycards.png" width="150" height="150" />

Plugin Name: **Keycards**  
Creator: [**MCrow**](steamcommunity.com/id/restoremonarchy)  
Creation Date: **2019-09-08**  
Price: **$12**  
Buy: [**ImperialPlugins**](https://imperialplugins.com/Products/Keycards)  
Video Preview & Tutorial: [**Youtube**](https://www.youtube.com/watch?v=ouR8P3W1OUg)

## About plugin
Keycards is a simple plugin that adds functionality of keycards to game. 

## Features

* Players can open the specific doors only if they have an item with ID of a keycard set in configuration
* Players don't need to press any button to open these doors, but just hover at it for a moment set in configuration
* You can transform any normal door into keycard door by using the command `/authkey` while pointing at the door
* You can set a custom health of keycard doors or use 0 to keep them default
* Tutorial & Preview video of the plugin on Youtube

## Configuration
```xml
<?xml version="1.0" encoding="utf-8"?>
<KeycardConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <KeycardAuthentications>
    <KeycardAuthentication AuthenticationID="1" Keycards="1196 519" />
    <KeycardAuthentication AuthenticationID="2" Keycards="519" />
  </KeycardAuthentications>
  <ShouldEquip>true</ShouldEquip>
  <DoorHealth>0</DoorHealth>
  <CloseDoorDelay>3</CloseDoorDelay>
  <ToggleDoorRange>4</ToggleDoorRange>
  <CheckFrequency>40</CheckFrequency>
</KeycardConfiguration>
```

## Translations
```xml
<?xml version="1.0" encoding="utf-8"?>
<Translations xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Translation Id="InvalidAuthID" Value="You didn't specify authentication ID parameter or it's invalid." />
  <Translation Id="AuthIDNotExist" Value="This authentication ID doesn't exist in your configuration." />
  <Translation Id="FailGetID" Value="Failed getting door the ID!" />
  <Translation Id="NotLooking" Value="You are not looking at any door." />
  <Translation Id="Success" Value="Successfully made door openable with keycard!" />
</Translations>
```