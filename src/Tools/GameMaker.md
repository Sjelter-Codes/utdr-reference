# GameMaker Basic Overview

## Preface

This section is not meant to be a GameMaker tutorial, please refer to the [GameMaker Docs](https://manual.yoyogames.com/#t=Content.htm) if you are searching for in-depth help or specific functions. This section is simply meant to provide a quick albeit simple description of the elements of GameMaker you will most likely be interacting with.

## Elements of a GameMaker Game
---

### Sprites

Sprites[^1] are collections of images/textures, usually associated to an object. Sprites are usually prefixed with `spr`. The textures themselves are sourced from TexturePages.

### Sounds

Sounds[^2] are audio files, they are sometimes built into the game itself but other times can be found in either the game/chapter's folder or the /mus folder

### Objects
Objects[^3] may or may not contain sprites and contain code. Objects are usually prefixed with `obj`. An object can have 7 different types of code. 


1. CREATE

    It is run when the object is created, either by instance_create in some other code, or at the start of a room that contains the object.
2. STEP

    It is run once a frame. It contains the bulk of what the object does.
3. ALARM

    It is run when that particular alarm reaches 0. Alarms are always counting down when they aren't being explicitly set. Set it to 30, it'll count down 29.. 28.. and run the code when it hits 0. To set an alarm you would use `alarm[x] = frames_to_count_down_for`. 
    
    <span style="opacity: 0.6;"><i class="fa fa-exclamation-triangle"></i> Be warned, there can only be 12 alarms inside of an object.</span>

4. DRAW 
    It overrides the normal visual behavior of the object. Normally, it just checks if it's visible, and if it is, it draws its sprite at its position, every frame (the background is also redrawn, but you can get funny caterpillars if there's no background). 
    
    <span style="opacity: 0.6;"><i class="fa fa-exclamation-triangle"></i> Caution: Draw code still doesn't run if the object is not visible</span>

5. OTHER

    It is triggers under other conditions, like event_user() calls (10-19), being outside a room, etc

6. DESTROY

    It runs when the object is destroyed

7. COLLISION 

    It runs when the object collides with (touches; it won't necessarily stop motion) a specified object. You can set it to collide with a "parent" object, and assign that as the parent to other objects, and it will still count when it collides with the "children"

> 


<div style="font-size: 0.66em;">

> [!NOTE] Footnotes
> [^1]: [Sprites GameMaker Page](https://manual.gamemaker.io/lts/en/GameMaker_Language/GML_Reference/Asset_Management/Sprites/Sprites.htm)
> [^3]: [Objects GameMaker Page](https://manual.gamemaker.io/lts/en/GameMaker_Language/GML_Reference/Asset_Management/Objects/Objects.htm)

</div>
<div style="max-width: 300px; font-size: 0.66em;">

> [!CAUTION] Depracation Warning
> In modern GameMaker sound is depracated and as such the link page may contain functions which do not work when modding Undertale and Deltarune.
>
> Tread the page below with caution:
> [^2]: [Sounds GameMaker Page](https://manual.gamemaker.io/lts/en/GameMaker_Language/GML_Reference/Asset_Management/Audio/Audio.htm)
</div>