# GameMaker Basic Overview

## Preface

This section is not meant to be a GameMaker tutorial, please refer to the [GameMaker Docs](https://manual.yoyogames.com/#t=Content.htm) if you are searching for in-depth help or specific functions. This section is simply meant to provide a quick albeit simple description of the elements of GameMaker you will most likely be interacting with.

## What is GameMaker Studio?

GameMaker Studio is the game engine that UNDERTALE and DELTARUNE use to make the game.

## Elements of a GameMaker Game

### Objects
Objects may or may not contain sprites and contain code. An object can have 7 different types of code.

1. CREATE

    It is run when the object is created, either by instance_create in some other code, or at the start of a room that contains the object.
2. STEP

    It is run once a frame. It contains the bulk of what the object does.
3. ALARM

    It is run when that particular alarm reaches 0. Alarms are always counting down when they aren't being explicitly set. Set it to 30, it'll count down 29.. 28.. and run the code when it hits 0. To set an alarm you would use `alarm[x] = frames_to_count_down_for`. 
    > <i class="fa-solid fa-exclamation"></i> Caution: Be warned, there can only be 12 alarms inside of an object.

4. DRAW 
    It overrides the normal visual behavior of the object. Normally, it just checks if it's visible, and if it is, it draws its sprite at its position, every frame (the background is also redrawn, but you can get funny caterpillars if there's no background). 
    > <i class="fa-solid fa-exclamation"></i> Caution: Draw code still doesn't run if the object is not visible

5. OTHER

    It is triggers under other conditions, like event_user() calls (10-19), being outside a room, etc

6. DESTROY

    It runs when the object is destroyed

7. COLLISION 

    It runs when the object collides with (touches; it won't necessarily stop motion) a specified object. You can set it to collide with a "parent" object, and assign that as the parent to other objects, and it will still count when it collides with the "children"

### Sprites

