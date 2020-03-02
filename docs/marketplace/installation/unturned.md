### Installation
Once you bought the plugin on [ImperialPlugins.com](https://imperialplugins.com/Products/Marketplace/313) you'll have to download ImperialPluginsBootstrapper and follow the `Readme - Install Instructions.txt` instructions.

### Configuration
```xml
<?xml version="1.0" encoding="utf-8"?>
<MarketplaceConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <MessageColor>yellow</MessageColor>
  <ApiUrl>https://marketplace.restoremonarchy.com/api</ApiUrl>
  <ApiKey>f215ab5d-e761-415e-b2de-f97db5069977</ApiKey>
  <TimeoutMiliseconds>10000</TimeoutMiliseconds>
  <Debug>true</Debug>
</MarketplaceConfiguration>
```

* `MessageColor` - color of messages sent by plugin
* `APIUrl` - url of your Marketplace Web API. `{webaddress}/api`
* `APIKey` - API Key for your Web API (equal to one you set in `appsettings.json`)
* `TimeoutMiliseconds` - time before plugin web requests timeout
* `Debug` - Show debug messages