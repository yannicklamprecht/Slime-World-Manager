# Slime World Manager
Slime World Manager, or SMW, is a Minecraft plugin that implements the Slime Region Format, developed by the Hypixel Dev Team. Its goal is to provide server administrators with an easy-to-use tool to save space on their servers, for free.

## What's wrong with Minecraft worlds?

Minecraft stores worlds using the Anvil Region Format. This standard is just fine for most cases, but it's not really efficient. In fact, if you are just using a premade map for a minigame or a lobby, most of the data stored is unnecesary. Moreover, the Anvil Region Format uses Zlib, a 24-year-old compression library. Although this library works just fine, nowadays there are faster and easier alternatives. For more information about the issues with the Anvil Format, check out this video made by Minikloon:

[![Region File Demo](http://img.youtube.com/vi/fONu02AtoUc/0.jpg)](http://www.youtube.com/watch?v=fONu02AtoUc)

## How does this plugin work?

SMW is capable of loading worlds from various sources:
* File System. Worlds are stored inside a folder named 'slime_worlds' in your server's root directory. Every world is stored inside a single file, using the '.slime' extension.
* MySQL _(to be done)_. You can also connect SMW to a MySQL server of your choice and store your worlds there, so you can access them from multiple servers at once.
* SeaweedFS _(to be done)_. SMW can download worlds from a SeaweedFS server, and update them whenever necessary.

Even though you could technically load the same world on various different servers at the same time, this could lead to some issues if read-only is not enabled.

Once retrieved, every chunk is loaded and kept in memory, so SMW doesn't have to load the world again. For this reason, even though there are no hardcoded limitations for world size, the usage of this plugin for large worlds is disacouraged. The Slime Format is meant for small worlds, like lobbies or minigame maps, not for survival servers.

## How to convert Minecraft worlds to the Slime Format

To convert a world to the Slime Format, you can use [this tool](https://drive.google.com/file/d/1MC3SyjM4nV-VzzwzoDWyx6th5ImKasJ7/view?usp=sharing). To do so, just download it, open your command line and type `java -jar slimeworldmanager-importer-1.0.0.jar <path-to-your-world>`. It'll scan your world and generate a .slime file inside the same directory you placed it. That's it!

This tool is also inside this repository, so you can check out its source code if you want!

## Which Spigot versions is this compatible with?

Currently, SMW can run on these Minecraft versions:
* 1.8.8-R0.1.

## How can I help?

If you are a developer, you can open a Pull Request and I'll check it out. If you are a server administrator, you could [buy me a coffee](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=K6MHYRBPV5UD2&source=url).

## Credits

Thanks to [Minikloon](https://twitter.com/Minikloon) and all the [Hypixel](https://twitter.com/HypixelNetwork) team for developing this format and making it public so others can use it as well!