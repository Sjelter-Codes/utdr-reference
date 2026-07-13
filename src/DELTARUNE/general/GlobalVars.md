# Global Variables

## global.interact
global.interact is used inside Deltarune to determine the current state the game should be insde. The following is the usage for global.interact in DELTARUNE

`global.interact` | Description
--- | ---
`0` | Free movement.
`1` | Movement is locked due to dialogue.
`2` | The party is in a battle.
`3` | You are going through a room transition.
`4` | Unused. Kris is using their sword out of battle.
`5` | The menu is open.
`6` | Movement is locked due to dialogue. The movement will automatically unlock once obj_dialoguer doesn’t exist.
`7` | You are going through a room transition while climbing.


## global.cinstance[]
global.cinstance, standing for Character Instance, is an array containing the idThe following is the usage for global.cinstance in DELTARUNE
 The index is basically WHICH like in the list of the objects which index it is in that list and then the

 you can do .name and .x and .y to the things returned by cinstance[n]

 in terms of the value of cinstance[n] itself i think its 0 for kris, 1 for susie and i assume 2 for ralsei and 3 for noelle? IDK though
`global.cinstance` | Value at Game Start
--- | ---
`[0]` | 4854845464869464
`[1]` | 48548454648694644
`[2]` | 48548454648694649.
