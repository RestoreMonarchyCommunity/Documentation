<img src="/assets/images/SellStorage.png" width="150" height="150" />

Plugin Name: **SellStorage**  
Creator: [**MCrow**](steamcommunity.com/id/restoremonarchy)  
Creation Date: **2020-03-07**  
Price: **$12**  
Buy: [**ImperialPlugins**](https://imperialplugins.com/Products/SellStorage)

## About Plugin
Players can buy and sell their storages by placing a placard on them.

## Features
* Works with Uconomy
* Players can set up their storage on sale with no commands
* After player input a price on the sign it automatically turns it into translations
* Players can preview items in storage by punching the storage

## FAQ
### 1. How to put storage on sale?
To enable your storage on sale you have to place placard or metal sign in front of the locker (or any other storage item). Then write in a sign the number which will be the price.
### 2. How to buy storage?
To buy storage you have to point at the sign that is in front of the storage.


## Configuration
```xml
<?xml version="1.0" encoding="utf-8"?>
<SellStorageConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <MessageColor>yellow</MessageColor>
  <SignIds>
    <unsignedShort>1470</unsignedShort>
    <unsignedShort>1098</unsignedShort>
  </SignIds>
  <PreviewContents>true</PreviewContents>
</SellStorageConfiguration>
```

## Translations
```xml
<?xml version="1.0" encoding="utf-8"?>
<Translations xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Translation Id="BuySuccess" Value="You successfully bought storage for {0}!" />
  <Translation Id="PriceFormat" Value="Price: {0} credits" />
  <Translation Id="SellerFormat" Value="Seller: {0}" />
  <Translation Id="HelpComment" Value="&lt;i&gt;Punch to see contents&lt;/i&gt;" />
  <Translation Id="CantAfford" Value="You cant afford to buy this, you need {0} more credits!" />
</Translations>
```
