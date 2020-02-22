<img src="/assets/images/Marketplace.png" width="150" height="150" />

Plugin Name: **Marketplace**  
Creator: [**MCrow**](steamcommunity.com/id/restoremonarchy)  
Creation Date: **2020-02-20**  
Price: **$25**  
Buy: [**ImperialPlugins**](https://imperialplugins.com/Products/Marketplace)

## About Marketplace
Marketplace is a three parts project (website, plugin & client side module). It gives your players ability to put up their items on sale, so they can be bought by others through website for in-game currency.

## Features
* Responsive and basic Marketplace website design using Bootstrap & SweetAlerts
* Plugin connects with website via other thread running web requests
* Plugin automatically uploads all item assets on the server to Marketplace Web API
* Client side module to semi-automatically generate and upload server item icons
* Web API is a bridge between database and plugin
* Two possible Database providers (MySQL >= 5.7 & SQL Server Express)
* Saves metadata of items put on sale, including gun attachments, quality, fuel etc.
* Works with Uconomy plugin
* Long Term Support

## Planned features
* Translations
* Vehicles Marketplace
* Admin dashboard for Marketplace to blacklist items, edit assets and wipe listings

## How it works
As it was said in product description, it's built of three projects. They all kind of depend on each other:  

* Web is the most essential part of Marketplace. Through the website players can see items listings and if they sign in through Steam, they can buy and manage their sellings.
* Plugin provides a way for players to withdraw their items from Marketplace within the valid purchase. It's also got a command to put their items on sale. 
* Module first requests from web API a list of assets uploaded by plugin when first ran on the server and then generate and upload icon for each of them that do not have icon yet

## Commands
**/sell** `<price>` – Puts an item you drop in vault like storage on sale for a given `price`  
```
<Permission Cooldown="0">sell</Permission>
```
**/claim** `<listingId>` – Claims a listing with `listingId` you purchased earlier 
```
<Permission Cooldown="0">claim</Permission>
```