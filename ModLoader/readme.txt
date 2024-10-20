HOW TO INSTALL:
drag and drop the contents of the rar into the game's base folder (where the exe is) its that easy
if you need to debug open the game with the bat file, otherwise using purely the exe works.

- DOCUMENTATION -

MODDING BASICS:
install godotsteam 3.5.2 (https://github.com/GodotSteam/GodotSteam/releases/tag/v3.21)

decompile the game with gdsdecomp (https://github.com/bruvzg/gdsdecomp) this is so you can study the source code and work with the game's base 
classes, later you will only have to export a pck with the mod's content, DO NOT RECOMPILE THE WHOLE GAME.

download Catcher, it comes bundled with Lure, the main API for Catcher

copy the 'steam_appid.txt' file from the base game and paste it on the root of the project's files

drag the 'Catcher' folder from the zip into the game's res:// inside the editor where all the other game files are, this is so when we export the path of the resources in and out of editor are the same, then delete the packed version of lure inside the mods folder of the project and replace it with the unpacked version of Lure found in a separate folder inside the zip, this is because godot can't open pck files from inside the editor, if you need to load a mod in the editor, make sure its unpacked.

open the decompiled game's Project Settings, go to run and change the main scene to catcher.tscn, since we can't use override.cfg in the editor. This step is optional sometimes it works on it's own no idea why maybe override.cfg works lol

copy the 'Mod Template' folder from the zip and paste it into the mods folder inside your godot project

res://
> Catcher
	> mods
		> the folder goes here

now you can start coding! start with the mod.gd file and it's _initialize function, this code will run as soon as the mod is loaded, Reference files are pure code and have their limitations, but if you need to access the node tree you can use the argument passed onto the function, if you need more advanced utility such as making an autoload that behaves like a node, you'll read the solution in a moment.

once your mod is done, open the export menu, select windows as platform and load the corresponding export templates from godotsteam's files, then go to the resources tab and select "Export selected resources (and their dependencies)" select all the folders and files (except mod.gd + GUMMUtil.gd, mod.cfg and icon.png) and export, then save the .pck file on the mod's folder as mod.pck

install Catcher on the base folder of the original game next to the .exe, now copy your mod's folder to the exported game's mod folder and remove all files except mod.gd + GUMMUtil.gd, mod.cfg,  icon.png and mod.pck, this is because the
pck file contains all the assets and resources that you created in the editor, saving space and allowing godot to load every single asset at once with little issue.

EXTRA FUNCTIONALITY/NOTES:
If your pck contains an "Autoload" folder, every since .tscn file inside it will be turned into a child of the game's root node after init, just like an autoload script, these are loaded and moved after the game's base autoload scripts/nodes.

If your pck contains a "Resources" folder with .tres files inside any of it's subfolders Lure will automatically load them if they're item resources such as custom fish, props, cosmetics etc, this may change in the future.

lets you patch/replace base game files if the replacement has the same path inside the pck as a base game asset (EXPERIMENTAL/BUGGY)