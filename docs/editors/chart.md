---
label: Chart Editor
description: "FNF: Doido Engine Documentation"
---

# Chart Editor

![](https://doidoteam.github.io/img/chart.png){width=800}

FNF: Doido Engine also features an improved Chart Editor. Most of its features are the same as the legacy 0.2.7 charter so we wont get into as much detail, but there are still a couple of features to note.

## The Grid

![](https://doidoteam.github.io/img/grid.png){width=400}

The grid is the main part of the Chart Edior and where you place notes. Nothing much has changed but there are a set of things that are different.

### Controls

- `Left Mouse Click` on a note that's placed to select the note. You can then change its length and type!
- `Right Mouse Click` on a note to delete it.
- `Scroll Wheel`, `W` or `S` to move the grid bar
- Hold `SHIFT` to move the grid bar faster
- `A`, `D` or `Scroll Wheel` (WHILE HOLDING `CTRL`) to move between sections
- `R` to reload the current section
- `Left` and `Right` arrows to change grid snapping
- `Z` and `X` to change grid zoom
- `SHIFT` + `R` to return to the start of the song
- `SPACE` to play/pause the song
- `ESC` to test chart
- `ENTER` to play chart

## Editor Settings

Here's what a handfull of buttons in the Chart Editor do!

### Song

- `Mute Inst` and `Voices` mute the Instrumental and Vocal tracks
- `BF` and `Dad Hitsounds` enable hitsounds whenever notes are hit by the Player or the Opponent
- `Old Timer` changes the timer style. If enabled the current time will be displayed in seconds, as opposed to minutes
- `Clear Events`, `Notes` and `Song` clear the notes in the desired track. `Clear Song` will clear both the Events and Notes. These buttons will (auto-save)[/editors/chart/#autosaving] the chart.
- `Controls` displays a list of available controls

### Section

- `Copy last` and `Clear Section` copy or clear the desired sections
- The `Notes?` and `Events?` decide wether the notes or the events are the ones to get copied, cleared, etc...
- `Swap Section` switches the notes between the Player and the Opponent
- `Duet Section` copies the notes from the Player to the Opponent and vice-versa
- `Invert Dad` and `BF Side` swap the notes for each side (Ex. `Left` will become `Right`, `Up` will become `Down`, etc...)

### Note

- `Note Length` changes the length of the sustain of the selected note. (Also `Q` and `E`)
- `Note Type` opens the Chooser for the Note Type
- `Convert Note Types` lets you mass change the note types of the current section. The dropdown is able to select between `Dad Notes` and `BF Notes`.

## Events

For events, please check their own page!

[!ref](/basics/events/)

## Auto-Saving

![](https://doidoteam.github.io/img/autosave.png){width=800}

If you ever crash or exit the game without saving your chart, you can load it by using the "Auto-Saved Charts Station". By opening this SubState from the Chart Editor, you will be able to load one of 5 previously edited charts. The game auto-saves every 5 minutes, as well as every time you play or clear a chart!


