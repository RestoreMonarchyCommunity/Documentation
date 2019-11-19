## Installation
### Installing UnturnedPanel
First thing that you want to do is to download the latest stable Unturned Web Panel release from [Github](https://github.com/RestoreMonarchyPlugins/UnturnedPanel/releases) then extract the zip file and install on your computer for example in this example it's installed in `C:\www\unturnedpanel`. The release should contain `wwwroot` folder, libraries & configuration files.

### Installing Web Server
Based on your operating system this tutorial will cover how to install IIS Express for Windows Server & *coming soon* for Linux.

#### Windows 

##### Installing IIS
I'd recommend watching [this](https://www.youtube.com/watch?v=BVuxNHF2p4c) less than 4 minutes video tutorial on how to install it for Windows Server 2012 (it's the same as on Windows Server 2016) or search for [How to Install IIS on Windows](https://cutt.ly/MT9BiE)

##### Installing Runtime
You wanna go [here](https://dotnet.microsoft.com/download/dotnet-core/2.2) and download ASP.NET Core/.NET Core Runtime & Hosting Bundle of the latest .NET Core 2.2 release.  

<img src="/assets/images/unturnedpanel/dotnetruntime_download.png" />

When it's done downloading launch the installer and follow the steps. When it's done installing you may need to restart your server.

## Configuring

### Configure WebUnturnedPanel

To configure WebUnturnedPanel you open appsettings.json and fill in the fields :D

### Configure Domain

Now you want to add a record to your domain that will point specified address to your server.
<img src="/assets/images/unturnedpanel/domain_addrecord.png" />
1. Stands for your domain prefix (sub domain) in this case I made it to point all of domain formats to my server.  
2. Here you put your server's IP.

### Configure IIS

#### Add Application Pool

Open IIS Manager and right click on the Application Pools field under your server dropdown (in the box on the left) and press on `Add Application Pool...` Then you fill the windows as shown below and press Ok.

<img src="/assets/images/unturnedpanel/application_pool.png" style=""/>

#### Add Website

Next thing you wanna do is to add a new website to your IIS web server. To do that you open IIS Manager and right click on the `Sites` dropdown which is located under Application Pools field and press `Add Website...`

<center><img src="/assets/images/unturnedpanel/add_website.png" style=""/></center>

1. In this field you select the Application Pool that we added in the previous step.
2. You specify the path to the folder where you extracted WebUnturnedPanel files (the folder containing `WebUnturnedPanel.dll` file).
3. Here you specify the name of the recorded you added before.

When you're done filling the fields press Ok.