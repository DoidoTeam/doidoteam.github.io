---
label: Character Editor
description: "FNF: Doido Engine Documentation"
---

# Character Editor

![](https://doidoteam.github.io/img/char_main.png){width=800}

FNF: Doido Engine has it's own Character Editor, that can configure all the offsets of your characters! Though it might seem intimidating at first, it's very simple to use!

## The Editor

![](https://doidoteam.github.io/img/char_settings.png){width=340}

The `Characters` tab can be used to configure many things about the editor, the character and the ghost. Here is a list of what you can change.
- The `Character` and [`Ghost`](/editors/offset/#ghost) dropdowns (!) are used to select which character you are editing or which [ghost](/editors/offset/#ghost) you are seeing.
- The `Char FlipX` and `Ghost FlipX` checkboxes let you flip the character or [ghost](/editors/offset/#ghost) horizontally.
- The `Playable` checkbox lets you select if the character you are editing is Playable or not. If you don't use this correctly your offsets might be wrong in-game. (NOTE: This does not affect the [ghost](/editors/offset/#ghost), so you need to set `Ghost FlipX` separatly)
- The `Show Ghost` checkbox lets you enable or disable the [ghost](/editors/offset/#ghost).
- The `Focus on Character` checkbox decides if the camera is currently focusing on the character or not.
- The `Currently Editing` section decides which offset you are currently editing. You can also use the text fields to manually set an offset.
- The `Save` button lets you save your character's JSON file. See [`Saving your Character`](/editors/offset/#saving-your-character) section for info

### Controls
- `Arrow Keys` move the selected animation's offset
- Holding `Shift` will increment them by 10
- Holding `Ctrl` will increment them by 100
- `Middle mouse button` will move the camera WITHOUT changing its offset (Check Focus on Character to return it to the offset position)
- `Scroll Wheel` will change the zoom of the camera

### Ghost

![](https://doidoteam.github.io/img/char_ghost.png){width=340}

Under your character, there exists a slightly transparent version of them called a Ghost. This is meant as a reference for animation offsets, and you can select its animation or even swap them for a completely different character.

## Editing Offsets

In any of the next sections, please make sure you select the correct offset before editing.

### Animation Offsets

![](https://doidoteam.github.io/img/char_anim.png){width=240}

On the upper left corner of the screen, you will find the Animation selector. Simply click on any of the animations on the left to select the character's anim, and on the right to select the ghost's anim.

### Global Offsets

![](https://doidoteam.github.io/img/char_global.png){width=340}

Global offset is the overall position of the character in the stage. To help with this we recommend you align the global position with the red cross that's under the character. This way you can do character changes without having to worry about positions being buggy and they will automatically align to any stage you put them in!

### Rating Offsets

![](https://doidoteam.github.io/img/char_rating.png){width=340}

Rating offset is the position of the rating sprite when you hit a note as them. This is only able to be seen when you disable the `Ratings on HUD` option.


### Camera Offsets

Camera offset is where the camera is gonna be when your character is focused on in-game. It may be a little hard to set it up from the editor so you can also manually edit the JSON and restart the song from the pause menu to reload.

## Saving your Character

After you finish your character, you can press the `Save` button to export a JSON file, which you should save to `assets/images/characters/_offsets/`