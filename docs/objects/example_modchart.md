---
label: Example Modchart
description: "FNF: Doido Engine Documentation"
---

# Example Modchart

This Modchart is made with Bopeebo Erect in mind, so if you wish to test it out, create a new `.hxc` file in `songs/bopeebo/`.

^NOTE: This modchart only works on Nightmare difficulty.^

```
import backend.song.Conductor;
import backend.game.SaveData;
import objects.note.Strumline;
import flixel.FlxG;
import flixel.math.FlxMath;
import flixel.tweens.FlxTween;
import flixel.tweens.FlxEase;
import states.PlayState;

var isNight:Bool = false;
var downscroll:Bool = false;
var downMult:Int = 1;

var strumlines:Array<Strumline> = [];

var modParams = {
    noteRadius: 0,
    noteSpeed: 12,
};
var spinNotes:Bool = false;
var noteSin:Float = 0.0;

function createPost()
{
    isNight = (PlayState.songDiff.toLowerCase() == "nightmare"
            && PlayState.SONG.song.toLowerCase() == "bopeebo");
    if(isNight)
    {
        trace("the script worked");
        downscroll = SaveData.data.get("Downscroll");
        if(downscroll)
            downMult = -1;

        PlayState.hasModchart = true;
        for(strumline in PlayState.instance.strumlines.members)
            strumlines.push(strumline);
    }
}
function update(elapsed:Float)
{
    if(!isNight) return;
    //trace('hi!! ' + elapsed);
    if(spinNotes)
    {
        noteSin += elapsed * modParams.noteSpeed;
        for(strumline in strumlines)
        {
            for(strum in strumline.strumGroup)
            {
                strum.x = strum.initialPos.x + Math.sin(noteSin + strum.strumData) * modParams.noteRadius;
                strum.y = strum.initialPos.y + Math.cos(noteSin + strum.strumData) * modParams.noteRadius;
            }
        }
    }
}
function stepHit(curStep:Int)
{
    if(!isNight) return;
    
    if(curStep >= 0 && curStep < 64)
    {
        for(strumline in strumlines)
        {
            for(strum in strumline.strumGroup)
            {
                var isBack:Bool = (curStep % 4 == 2);
                if(curStep % 2 == 0)
                {
                    FlxTween.tween(
                        strum,
                        {y: isBack ? strum.initialPos.y : strum.initialPos.y + 300 * downMult},
                        stepToSec(2),
                        {ease: !isBack ? FlxEase.cubeIn : FlxEase.cubeOut}
                    );
                    if(isBack)
                    {
                        strum.scale.set(1.4 * strum.strumSize, 0.6 * strum.strumSize);
                        FlxTween.tween(
                            strum.scale,
                            {x: strum.strumSize, y: strum.strumSize},
                            stepToSec(2),
                            {ease: FlxEase.cubeOut}
                        );
                    }
                }
            }
        }
    }
    if(curStep == 68)
    {
        notesRainbow(false);
    }
    if(curStep == 128)
    {
        notesRainbow(true);
    }
    if(curStep == 192)
    {
        for(strum in strumlines[0].strumGroup)
            FlxTween.tween(strum, {
                    x: strum.initialPos.x,
                    y: strum.initialPos.y,
                    strumAngle: 0,
                    angle: 0,
                }, stepToSec(2),
                {ease: FlxEase.cubeOut}
            );

        // FlxMath
        for(strum in strumlines[1].strumGroup)
        {
            FlxTween.tween(strum, {
                x: FlxG.width - 100,
                y: FlxMath.lerp(190, FlxG.height - 190,
                    (downscroll ? 3 - strum.strumData : strum.strumData) / 3
                ),
                strumAngle: -90 * downMult,
                angle: 90 * downMult,
            }, stepToSec(4), {ease: FlxEase.cubeInOut});
        }
    }
    if(curStep == 224)
    {
        for(strum in strumlines[1].strumGroup)
        {
            FlxTween.tween(strum, {
                x: strum.initialPos.x,
                y: strum.initialPos.y,
                strumAngle: 0,
                angle: 0,
            }, stepToSec(16), {ease: FlxEase.cubeInOut});
        } 
    }
    if(curStep == 240)
    {
        spinNotes = true;
        FlxTween.tween(modParams, {noteRadius: 28, noteSpeed: 3}, stepToSec(16));
    }
}

function stepToSec(steps:Int):FLoat
{
    return Conductor.stepCrochet / 1000 * steps;
}

function notesRainbow(isOut:Bool = false)
{
    var rainMult:Int = (isOut ? -1 : 1) * downMult;
    for(strumline in strumlines)
    {
        for(strum in strumline.strumGroup)
        {
            var daAngle:Float = [15, 5, -5, -15][strum.strumData] * rainMult;
            FlxTween.tween(
                strum,
                {
                    y: strum.initialPos.y + [1,0,0,1][strum.strumData] * 20 * rainMult,
                    strumAngle: daAngle,
                    angle: -daAngle
                },
                stepToSec(2),
                {ease: FlxEase.cubeOut}
            );
        }
    }
}
```
