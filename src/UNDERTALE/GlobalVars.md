# Global Variables

## global.interact
global.interact is used inside Undertale to determine the current state the game should be insde. The following is the usage for global.interact in UNDERTALE

`global.interact` | Description
--- | ---
`0 `|  Free movement, not interacting with anything
`1` | Cutscene or when interacting with an object
`2` | Specific to Ruins, post-spare Toriel cutscene in basement
`3` | Room transition (entering battle, shops, and some cutscenes count as well)
`4` | Used when falling through the floor. Examples are the cracked tiles in Ruins and falling off the Snowdin ice puzzle
`5` | Menu is open. Setting to any other value will close the menu if it is open
`6` | Specific to Ruins, used when Toriel leads you across the bridge of spikes
`99` | Specific to Ruins, used when you flip a “plot switch” (wall-mounted switch to disable spikes) and during Toriel’s hand-holding cutscene in her house.
