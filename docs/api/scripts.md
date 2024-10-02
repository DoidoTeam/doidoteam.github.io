---
label: PlayState Scripts
description: "FNF: Doido Engine Documentation"
---

# PlayState Scripts

![](https://doidoteam.github.io/img/scripts.png){width=500}

FNF: Doido Engine uses [HScript-Iris](https://github.com/crowplexus/hscript-iris) to have user-made scripts that are ran from the Playstate. It is currently developed to make modcharts, but you are also able to do other things using it. Any regular events should be done using JSON events.

## Paths

Any scripts in `.hxc` format placed in a song folder will automatically be loaded, regardless of name.

^NOTE: If you wish to use scripts in HTML5, you will have to manually push scripts to the scriptPaths array. (Ex. `scriptPaths.push("songs/bopeebo/script.hxc");`)^
## Functions

The following functions are called from PlayState, which you can use to create scripts. More will be added in the future.

```
// State Functions
function create() {}
function createPost() {}
function update(elapsed:Float) {}
function updatePost(elapsed:Float) {}

// Conductor Functions
function beatHit(curBeat:Float) {}
function stepHit(curStep:Float) {}

// Note Functions
function onNoteHit(note:Note, strumline:Strumline) {}
function onNoteMiss(note:Note, strumline:Strumline, ghostTap:Bool) {}
function onNoteHold(note:Note, strumline:Strumline) {}
```

^NOTE: `create()` and `update()` are both called from the beginning of the functions, while `createPost()` and `updatePost()` are called from the end of the function.^

You can also create your own functions, as shown here:

```
function stepToSec(steps:Int):Float {
    return Conductor.stepCrochet / 1000 * steps;
}
```

## Imports

You can also import Classes from the game. You are able to call most Classes, as long as they are imported somewhere in the code.

```
import flixel.FlxG;
import flixel.math.FlxMath;
import flixel.tweens.FlxTween;
import flixel.tweens.FlxEase;
import states.PlayState;
```

^NOTE: Currently, the `using` keyword (Ex. `using StringTools`) is unavailable due to limitations in HScript Iris. As soon as it gets added you will probably be able to use it in your scripts.^

## Modcharts

### Manipulating notes

To manipulate notes, you can modify the individual strums and the notes will automatically "lock onto" them. Here are a couple of fields you can use.

```
// Which strum 
strum.strumData = 0;

// Current position
strum.x = x;
strum.y = y;

// Default position (DO NOT CHANGE, ONLY TO USE FOR REFERENCE)
strum.initialPos.x = x;
strum.initialPos.y = y;

// Scale
strum.scale.set(1,1);

// Angle
strumAngle = 0;
```

### hasModchart

Some modcharts might break when changing Downscroll or Middlescroll in the options. The `hasModchart` variable allows you to stop the player from changing these options mid-song, to avoid bugs.
```
import states.PlayState;

function create() {
    PlayState.hasModchart = true;
}
```

### Example Modchart

Here's a silly little modchart example, made for Bopeebo Erect. You can use this to base your own modcharts off of.

[!ref](/objects/example_modchart/)

## Other Examples

### Difficulty specific code

To have code run on a specific difficulty, you can detect it with a boolean. Here's an example of how to do this.
```
var isErect:Bool = false;

function createPost() {
    isErect = (PlayState.songDiff.toLowerCase() == "erect" || PlayState.songDiff.toLowerCase() == "nightmare");
    if(isErect)
        trace("its an erect remix!");
}
```

## Other Uses

- For other, simpler events, please checkout the Events guide.
- For other possible uses of HScript-Iris, please visit their repository to learn more!

[!ref](/basics/events/)
[!ref](https://github.com/crowplexus/hscript-iris)

