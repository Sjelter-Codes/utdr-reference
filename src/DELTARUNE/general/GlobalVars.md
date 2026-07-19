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
global.cinstance, standing for Character Instance, is an array containing the ids of the characters currently following the player in the overworld. It has a length of 3. The objects that the ids point to are instances of [obj_caterpillarchara](actors_and_caterpillars.md).

The order of which characters are at which indices changes based on the order in which they are following you. For example, in much of Chapter 1, the object representing Ralsei is in cinstance[0], since he is your only follower.


