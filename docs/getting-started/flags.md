---
label: Build Flags
description: "FNF: Doido Engine Documentation"
order: -1
---

![](https://doidoteam.github.io/img/flags.png)

There are a couple of Flags you can use when building the engine that can help you in development.

### How to use flags
To use flags, simply append them to the end of your `lime test PLATFORM` command, like this:
```
lime test windows -debug -DFREEPLAY
```
If you use VSCode, you can simply select a build preset from the platform list.

![](https://doidoteam.github.io/img/vscode_plat.png)

### List of available flags
- `-debug` can build the game in debug mode. This enables many debug features, such as the FlxDebugger and debugging through VSCode.
- `-DFREEPLAY` and `-DMENU` launch the game directly in the Freeplay and MainMenu states, respectively. These can't be used together.