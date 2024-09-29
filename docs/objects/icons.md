---
label: Health Icons
description: "FNF: Doido Engine Documentation"
---

# Health Icons

![](https://doidoteam.github.io/img/icons.png){width=900}

Icon are located in `assets/images/icons/` with the name `icon-YOUR_CHARACTER_NAME`.

### Configuring Health Bar color

![](https://doidoteam.github.io/img/getcolor.png){width=400}

You can edit the `getColor()` function, located in the HealthIcon class to add in the colors of your icons. Simply add a line to the map like this:
```
"character"	=> 0xFFFF0000,
```
The color needs to be in Hex format. You can use any image editing software or online service to get the correct color.

### Dynamic Icon states

![](https://doidoteam.github.io/img/iconstates.png){width=600}

FNF: Doido Engine currently supports icons with up to 3 states (Neutral, Losing, Winning). They are automatically detected based on the width of the icon graphic, so no configuration is required!

### Pixel Icons

If your icon ends in `-pixel`, the game will automatically set it as a pixelated sprite (disables antialiasing and enables isPixelSprite).
