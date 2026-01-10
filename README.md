# OctoPrint-Octo4a_battery

This plugin displays the battery level of yout phone running OctoPrint with [Octo4a](https://github.com/feelfreelinux/octo4a) .
It also has a basic telegram integration and is able to send warnings to a telegram at pre defined battery levels

## Screenshots
### Battery Level

![Octo4a_battery](images/screenshot_battery_level.png?raw=true)

### Settings

![Octo4a_battery](images/screenshot_settings.png?raw=true) 

## Setup

1. Install manually the Octo4a_battery plugin using the URL from this repository:

    `https://github.com/tobiasgraf/OctoPrint-Octo4a_battery/archive/master.zip`

2. Install [BatteryDog from Fdroid](https://f-droid.org/en/packages/net.sf.andbatdog.batterydog/)
3. Set the battery optimisation to "Not Optimized" for BatteryDog
4. Start the BatteryDog service and it will begin writing the battery status to a text file 
5. Find the BatteryDog dump file location. (e.g. look for "recent files" in FX file manager)
6. Copy the BatteryDog dump file location path.
7. Open the Octoprint configuration and find the Octo4a_battery settings
8. Paste the BatteryDog filepath in the configuration


## Configuration

 This plugin simply reads the file battery from the file `/sys/class/power_supply/battery/capacity`. This works on my Phone (Nexus 5). If this does not work for you, you can change the path in the settings.


### Telegram

You need to create a telegram bot and configure the token in the settings. How to create a bot have a look at the [Otcoprint Telegram Plugin](https://github.com/fabianonline/OctoPrint-Telegram#create-telegram-bot) or just google it.

To get the ChatID, write a message to the bot or add it to a channel. Then go to 

https://api.telegram.org/bot**yourTokenHere**/getUpdates

with your browser. This returns a JSON where you can find your chat ID.
