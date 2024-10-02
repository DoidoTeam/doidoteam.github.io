---
label: Assets Folder
description: "FNF: Doido Engine Documentation"
order: -2
---

# Assets Folder

![](https://doidoteam.github.io/img/assets.png){width=1000}

FNF: Doido Engine's Assets folder has been reorganized. Since we have our own custom loader, the engine doesn't require `preload` and `shared` paths and everything goes in `assets/`.

## Asset Libraries

### Images

`assets/images/` is where any sprites, backgrounds or other images go, as well as any other files related to them (Ex. Character JSONs and XMLs). Each of its folders should be pretty self explanatory.

### Music

`assets/music/` is where any non-playable songs go, such as menu, pause and game over themes. 

### Songs

`assets/songs/` is where any playable songs go. This folder holds their `.ogg` files as well as their Charts, Events or song-specific scripts, so if you've noticed the lack of a data folder this is where Charts go!

### Sounds
`assets/sounds/` is where any other `.ogg` sounds go, such as misses, countdowns, menu SFX and others.

### Fonts
`assets/fonts/` is where the fonts that get used in-game go. Currently, both `.ttf` and `.otf` fonts are supported.

### Scripts

`assets/scripts/` is where any other scripts go, that get loaded for every song.

### Extra Files

- `extra-songs.txt` allows you to add extra songs to the Freeplay that aren't in the SongData weeks array.
- `introText.txt` holds all the randomized texts that appear in the Title Screen.

## Libraries

For more information on Libraries, please check out the Paths API page.

[!ref](/api/paths/)

