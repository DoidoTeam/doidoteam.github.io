---
label: Custom Stages
description: "FNF: Doido Engine Documentation"
order: -1
---

# Custom Stages

## Adding your assets

![](https://doidoteam.github.io/img/stages.png){width=600}

Assets for stages are usually placed in `assets/images/backgrounds/`, though you are free to place them wherever you want. No specific configuration is necessary for the assets side.

## Coding your stages

Code for the characters is handled by Stage.hx, which is situated in the gameObjects Source folder. For more info on how the Source folder is structured, click [here](/getting-started/source_structure).

### Example Stage
Here is a simple example stage you can use to make your own. Copy this to the switch statement around line 85. 

```
case "stage":
    PlayState.defaultCamZoom = 0.7;

    gfPos.set(660, 580);
    dadPos.set(260, 700);
    bfPos.set(1100, 700);
    
    var bg = new FlxSprite(0, 0).loadGraphic(Paths.image("backgrounds/stage/image"));
    add(bg);
```

You can add your own sprites like our example `bg`, set the positions of each characters and set the `defaultCamZoom`.

^NOTE: Check out the [official Flixel documentation](https://haxeflixel.com/documentation/flxsprite/) for more info on general FlxSprite usage.^

### Loading Stage
![](https://doidoteam.github.io/img/reloadstage.png){width=600}
The `reloadStageFromSong()` function is used to associate stages to songs. You can create an array of stages to be preloaded with the song that can later be changed between without any lag. The LAST stage in the array is the one thats gonna be loaded in last so keep that in mind.

## Advanced Stage features

### GF Version
![](https://doidoteam.github.io/img/gfversion.png){width=400}

You can choose which Character is going in the GF position. By default this is "gf" but you can change it to any character you wish.
NOTE: If you want to have no GF, you can set her version to "no-gf", which is a placeholder empty character.

### Foreground Layer

You can choose to render Sprites on a foreground layer (above the characters) by adding the sprite like this:
```
foreground.add(sprite);
```
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

### stepHit and Update functions
![](https://doidoteam.github.io/img/stephit.png){width=300}
You can set your own code to run on the stepHit (in sync with the song) or Update (constant) functions. There is also a conditional in stepHit that allows you to run a smaller beatHit function. This can be useful for animated sprites, for example.
^NOTE: Make sure you initialize your variables in the Stage class to do this.^

### Accessing Sprites from other classes (PlayState)

You are able to access sprites created in the Stage class from the PlayState or other classes. To do so, you can append `stageBuild` to the beginning of the sprite, like so:
```
stageBuild.sprite.alpha = 0;
```