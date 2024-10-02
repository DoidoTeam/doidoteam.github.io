---
label: Events
description: "FNF: Doido Engine Documentation"
order: -3
---

# Events

![](https://doidoteam.github.io/img/events.png){width=800}

FNF: Doido Engine's Event JSONs work in a similar way to Psych Engine's, but there are a few differences. Here's a small guide of them.

### Note on JSONs

On FNF: Doido Engine, Events have their own JSON file, and thus will not be saved on the main chart JSON.

## Values

Each event can have up to 3 values, which are detailed on a case by case basis. The number stepper chooses which slot you are currently on and you can see a list of the events on each slot from the icons to the right of the Event Note.

You can also use the `Clear this Slot` and `Clear all Slots` buttons to clear the values and selected events of a single or every slot.

## Events by difficulty

You can name an event JSON using its difficulty to have it load only when you play that certain difficulty. For example, if you name a JSON `events-easy.json` it will only play those events on Easy.

## Adding Custom Events

![](https://doidoteam.github.io/img/possibleevents.png){width=800}

To create custom events, you simply need to add the Event to the `onEventHit()` function in PlayState. Then, to use these events, you will also need to add them to the `possibleEvents` array in the ChartingState class.

### Event Icon

While an icon isn't required for an event (there is a default icon that gets used if no icon exists), it helps you with knowing which events are on different slots. To add a custom icon, simply add the icon to `images/notes/events/`.

^NOTE: Icons are named in lowercase with underscores `_` replacing spaces.^

### Preloading Events

Some events might need preloading. To do this, add your preloading code to the `preloadEvents()` function in PlayState and it will be run for every event of the type in the `create()` function.