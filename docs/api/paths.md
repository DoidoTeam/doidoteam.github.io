---
label: Paths
description: "FNF: Doido Engine Documentation"
order: -1
---

# Paths

![](https://doidoteam.github.io/img/paths.png){width=500}

The Paths class holds some new functions and variables that may be useful for creating mods:

- `getPath(path, library)` allows you to return a full path according to its library, if there is one.
- `fileExists(path, library)` allows you to check if a certain file exists.
- `clearMemory()` allows you to manually wipe the memory.
- `readDir(directory, type, removeType, library)` allows you to read the contents of a certain directory.
- `preloadPlayStuff()` allows you to preload PlayState related assets, such as the countdown and Hitsounds.
- `preloadGraphic(key, library)` and `preloadSound(key, library)` allow you to preload a certain image or sound.

## Libraries

One of FNF: Doido Engine's latest features is library support, similar to Psych Engine. This allows you to create folders inside of the `assets/` folder to better organize your own files. Simply make your own folder in `assets/`, create the necessary Paths (Ex. `images`, `sounds`) and then use the library on any supported Paths functions.

