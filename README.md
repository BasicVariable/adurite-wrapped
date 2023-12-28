# adurite-wrapped
Documentation for the config.yml file of adurite-wrapped, by healthward on discord.

**• Q/A**
- Why is it taking minutes to edit prices?
Adurite has ratelimits, doing price changes every 1-2 minutes prevents the bot from hitting these limits and getting detected by cloudflare

- Why do you need my browser in debugging mode?
The best way to avoid cloudflare detection is to run the bot from a real browser. The browser window it uses will only ever come into focus when you start the bot, it isn't intrusive.

**• Tutorial**
```
Before doing anything you'll NEED adurite-wrapped from discord.gg/callie, this isn't free...
1. Do /whitelist time-left and copy the key (it'll be under the spoiler)
2. Download the latest build in #🎁adurite-wrapped that's based on your OS
  a. If you use windows pick the windows one.
```

**• Getting your old security token**
```
Disclaimer: This tutorial is for Google Authenticator, if you used any other authenticator app to hold your security tokens you'll need to figure this out yourself.
```
Follow [this](https://github.com/krissrex/google-authenticator-exporter) tutorial to retrieve your old security code, if you're unable to get your security token you'll need to make a new adurite account or ask them to give it to you (they probably won't).

**• How to get a discord bot**
```
Heads up! I do this on a PC, as that's where I made the instructions.
1. Go to "https://discord.com/developers/applications" and login to discord
2. Click the "Applications" button on the left
3. Click "New Application" on the top right corner of your screen
4. Name it and click create
5. Go to the "Bot" tab on the left panel and scroll down to the "Privileged Gateway Intents" section then flip all the SWITCHES (not the buttons at the bottom)
6. Scroll back up and click "reset token" then save the token it gives you
7. Click OAuth2 on the panel to the left then URL generator
8. Under the "Scopes" section click "Bot" then click administrator and use the link it gives you at the bottom
```

# Config settings
Most of these are self explanatory but, here are some of the docs I've written for them.

If you're getting yaml errors put your config in https://jsonformatter.org/yaml-formatter

 **• valuing > customLowest**
List of items that have specific min/max rates attached to them.
EX:
```
customRates:
    - [itemid", [max, min]]
    - [000010, [2, 3]]
```

**• discordBotToken**
The token you got after clicking the "reset token" button earlier (see "How to get a discord bot")

**• whitelistToken**
Token you got from the discord command earlier, used to authenticate your client.

**• chromeWS**
Websocket to your chromium based browser (I think it can also work for Firefox but, I'm not sure what the instructions would be since I did testing with Chrome).

Here's how to get it:
```
1. Right click on your Google Chrome shortcut icon => Properties
2. In Target field, add to the very end --remote-debugging-port=9222
  a. Example: "C:\Program Files (x86)\Google\Chrome\Application\chrome.exe" --remote-debugging-port=9222
3. Open Google Chrome and go to http://127.0.0.1:9222/json/version
4. Put the webSocketDebuggerUrl value in the chromeWS field
```

**• account > username**
Username to your adurite.com account. This DOES NOT leave your PC at all, it's only sent to adurite through your browser to login (if you aren't).

**• account > password**
Password to your adurite.com account. This DOES NOT leave your PC at all, it's only sent to adurite through your browser to login (if you aren't).

**• account > securityToken**
Security token for entering your seller panel on adurite. This DOES NOT leave your PC at all, it's only used for the 2step process adurite forces us to do every 24hrs.

**• valuing > rap**
Min/max rates the bot will list rap items for.

**• valuing > valuing**
Min/max rates the bot will list valued items for.

**• listingMethods > Stripe**
Boolen (true/false), will list items with Stripe enabled. When set to false it won't set your items to be sold with Stripe

**• listingMethods > PayPal**
Boolen (true/false), will list items with paypal enabled. When set to false it won't set your items to be sold with PayPal.
