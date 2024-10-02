---
label: Custom Songs
description: "FNF: Doido Engine Documentation"
---

# Custom Songs

## Adding your assets

![](https://doidoteam.github.io/img/songs.png){width=700}

Firstly, place both your song and its chart in their own folder in `assets/songs/`. FNF: Doido Engine places all of its song related files in their respective folders so `.ogg` files as well as their Charts, Events or song-specific scripts all go here.

## Adding songs in-game

![](https://doidoteam.github.io/img/weeks.png){width=360}

To add new songs to either the Story Mode or the Freeplay menu, you need to add it to the weeks array in the **SongData** class. You can either use any preexisting weeks or the following example to create your own.
```
{
    songs: [
        // song name, icon for freeplay
        ["song-1", 			"dad"],
        ["song-2", 			"spooky"],
        ["song-3", 			"pico"],
    ],

    // folder where the characters are located
    weekFile: 'week1',

    chars: ['dad', 'bf', 'gf'],
    weekName: 'daddy dearest',
    diffs: ['easy', 'normal', 'hard', 'erect', 'nightmare'],

    // whether this week shows up only on the Story or Freeplay menu
    // please avoid using both of these
    storyModeOnly: false,
    freeplayOnly: false,
}
```