---
label: Custom Stages
description: "FNF: Doido Engine Documentation"
order: -1
---

# Custom Stages

## Adding your assets

Assets for stages are usually placed in `assets/images/backgrounds/`, though you are free to place them wherever you want. No specific configuration is necessary for the assets side.

## Coding your stages

Code for the characters is handled by Stage.hx, which is situated in the gameObjects Source folder. For more info on how the Source folder is structured, click [here](/getting-started/source_structure).

### Example Stage
To add your new stage, you need to add a new case to the switch statement around line 84. Here's the basis on how it works. Feel free to copy this into your code and edit it accordingly.

```
case "stage":
    PlayState.defaultCamZoom = 0.7;

    gfPos.set(660, 580);
    dadPos.set(260, 700);
    bfPos.set(1100, 700);
    
    var bg = new FlxSprite(0, 0).loadGraphic(Paths.image("backgrounds/stage/image"));
    add(bg);
```

^NOTE: Check out the [official Flixel documentation](https://haxeflixel.com/documentation/flxsprite/) for more info on general FlxSprite usage.^

### Loading Stage
![](https://doidoteam.github.io/img/reloadstage.png){width=600}
The `reloadStageFromSong()` function is used to associate stages to songs. You can create an array of stages to be preloaded with the song that can later be changed between without any lag. The LAST stage in the array is the one thats gonna be loaded in last so keep that in mind.

## Advanced Stage features
### Animated Sprites
You can have also have animated sprites, for example:

```
// You need to initialize the variable in the Stage class
var sprite:FlxSprite;

sprite = new FlxSprite(0,0);
sprite.frames = Paths.getSparrowAtlas("backgrounds/stage/sprite");

// Replace this with your own animations
sprite.animation.addByPrefix('idle', 'idle', 24, false);

add(sprite);

// Play the animation
sprite.animation.play("idle");
```