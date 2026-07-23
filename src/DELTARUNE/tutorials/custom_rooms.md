# Custom Rooms

> [!NOTE]
> This page is a work in progress since rooms are a complicated topic, feel free to contribute to the wiki at any time

## Room Setup
A room needs a couple things to make sure it doesn't fall apart.

The most important one of course is `obj_mainchara` also known as the player character.
 
## Room Transitions
> [!WARN]
> This does not work in Deltarune Chapter 1, that uses the archaic Undertale variant of the code. Please see the totally existant page on creating a Room in Undertale for that
To create a room transition you will need two objects

1. A `obj_doorAny` object
2. A `obj_markerAny` object


### Setup

#### obj_doorAny
This object is used for the transistion itself, it requires the same type of door/`doorEntrance` on both of them to work correctly.

In the PreCreate for the `obj_doorAny` you must set the room the entry connects to, which "door" object to connect to and wether or not the music should fade by using this object.

##### Example Usage
```js
doorRoom = room_runes_statues;
doorEntrance = 1;
doorFadeMusic = true;
```
#### obj_markerAny
This object determines where the player will be following a door transition event. No code is required to set this up, all you'll need to do is change the `image_index` to the coresponding `obj_doorAny` entrance, the one that shows up as A-1 is 1 the one that shows up as B-2 is 2 and so on.