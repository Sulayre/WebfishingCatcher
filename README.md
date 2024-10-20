##This mod loader is currently deprecated, use [GDWeave]( https://github.com/NotNite/GDWeave) and [The Standalone Version of Lure for GDWeave](https://github.com/Sulayre/WebfishingLure) instead!

![Catcher Logo](https://media.discordapp.net/attachments/1297300581102391296/1297300581274091573/image.png?ex=67156cd1&is=67141b51&hm=4ed4eac2f276cab12e12c0109edf850bb33a3283183d98907cd88e3b6f66b5b1&=&format=webp&quality=lossless)
## _An external mod loader for Webfishing and asset replacer written in pure GDScript_
_(it also comes bundled with LureAPI, a basic WIP modding library)_
## Features (Catcher)

- Load pck files into the game that can reference base game classes and code flawlessly
- mod the game without having to recompile it (duh)
- automatically runs ```mod.gd``` and instances any .tscn file on root if its inside a 'Autoloads' folder, inside or outside the pck.

## Features (Lure)

- Automatically scans for item and cosmetic resource files on all mods currently installed, making basic modded content require no code and only editor use.


## Limitations
- function hooking is not possible as of right now, hopefully soon!

## Installation

- download the release then drag and drop into the game's exe folder, add the mods into Catcher > mods.

## Development

modding instructions are available inside the readme file of the release, proper wiki/documentation soon!
if you need additional assistance feel free to contact me through [Discord DMs](https://discordapp.com/users/227822955994939402) or the [Webfishing Community Discord](https://discord.gg/webfishers)
