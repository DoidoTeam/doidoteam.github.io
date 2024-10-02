---
label: Source Folder
description: "FNF: Doido Engine Documentation"
order: -3
---

# Source Folder

![](https://doidoteam.github.io/img/source_folders.png){width=1000}

Our Source folder is organized according to what function each .hx file has:
- `data/` holds important code relating to the engine's core functions and tools, such as Highscore, Timings, Discord and the CrashHandler. You will probably only use this to add Songs or change the Discord Status config. 
- `flixel/` has modified HaxeFlixel code that is optimized for Doido Engine. You probably won't need to use this.
- `gameObjects/` is where all the objects are stored, such as Characters, Stages, Notes and all the UI. This is something you will use a lot. It has a couple of subfolders specific to the HUD or menus.
- `shaders/` is where any graphical shaders are stored. Included in the engine is DistantNoteShader, but you might wanna add more, depending on your mod's needs.
- `states/` and `substates/` hold the code for the game's states, such as the PlayState or MainMenuState for `states/`, and the GameOverSubState or PauseSubState for `substates/`.
