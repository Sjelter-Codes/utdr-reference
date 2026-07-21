# Global Variables

## global.plot
In UT/DR global.plot is a `float` used to determine where in the plot the game is in, 0 being the start. 

### Example Usage
```js
if (global.plot < 12)
    global.plot = 12;
```
## global.flag
global.flag is an `array` used for pretty much anything that can happen. From decisions to storing specific values flags can be extremly diverse with their usage.

### Example Usage

```js
if (global.flag[23])
    global.flag[920]++
```

<details>
<summary>All Flags in UNDERTALE</summary>

The following data is sourced from [tomat.dev](https://tomat.dev/undertale/flags)

Volatile values are flags that are changed often at runtime, so not easy to manually set. 

Bool values are true/false conditions. 

Range values can be any number. 

Counter values increment as the condition is met.

> [!CAUTION]
> The names in the following section are fan-given, searching for them will not net any results.

<div id="undertale-flags">(Loading UNDERTALE flags...)</div>

<script>
const div = document.getElementById('undertale-flags');
try 
{
  var request = new XMLHttpRequest();
  request.open("GET", "https://tomat.dev/undertale/flags", true);
  request.send(null);
  request.onreadystatechange = function() {
    if (request.readyState == 4)
    {
      const parser = new DOMParser();
      const doc = parser.parseFromString(request.responseText, "text/html");
      const table = doc.querySelector("table");
      if (table) {
        div.innerHTML = table.outerHTML;
      }
      else {
        div.innerHTML = "Failed to load UNDERTALE flags."
      }
    }
  };
} 
catch (error) {
  console.error("An error occurred loading the UNDERTALE flags:", error.message);
  div.innerHTML = "Failed to load UNDERTALE flags."
}
</script>

</details>

<details>
<summary>All Flags in DELTARUNE</summary>

The following data is sourced from [Tenna Save Editor](https://github.com/tennaproject/tenna-editor/blob/main/src/data/flags.ts)

Volatile values are flags that are changed often at runtime, so not easy to manually set. 

Bool values are true/false conditions. 

Number values can be any number. 

Map values map to certain specific values as outlined in their description.

> [!CAUTION]
> The names in the following section are fan-given, searching for them will not net any resuts

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Flag</th>
      <th>Name</th>
      <th>Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>6</td>
      <td>TEXT_SKIP_DISABLED - Disable text skip -</td>
      <td>volatile <br> bool</td>
      <td>Volatile. Prevents you from skipping text in some cutscenes. <br></td>
    </tr>
    <tr>
      <td>7</td>
      <td>DARK_WORLD_MENU_DISABLED - Disable Dark World menu -</td>
      <td>bool</td>
      <td>Prevents you from opening the Dark World menu and affects music when leaving shops. <br></td>
    </tr>
    <tr>
      <td>8</td>
      <td>SIMPLIFIED_VFX_ENABLED - Simplify VFX -</td>
      <td>bool</td>
      <td>Set from the Dark World menu. <br></td>
    </tr>
    <tr>
      <td>9</td>
      <td>BATTLE_MUSIC_STATE - Battle music -</td>
      <td>map</td>
      <td>Volatile. Allows or prevents the game from playing Rude Buster at the start of an encounter. <br>0 = Default state<br>1 = In battle<br>2 = Starting boss music<br></td>
    </tr>
    <tr>
      <td>10</td>
      <td>WRIST_PROTECTOR_ENABLED - Wrist Protector -</td>
      <td>bool</td>
      <td>Whether you have the Wrist Protector. Enabled by default since the Chapter 1&2 release. <br></td>
    </tr>
    <tr>
      <td>11</td>
      <td>AUTO_RUN_ENABLED - Auto-run -</td>
      <td>bool</td>
      <td>Whether you have enabled auto-run. <br></td>
    </tr>
    <tr>
      <td>12</td>
      <td>SCREEN_SHAKE_DISABLED - Disable screen shake -</td>
      <td>bool</td>
      <td>Keeps the game screen from shaking. Intended to be set from the Dark World menu. <br></td>
    </tr>
    <tr>
      <td>13</td>
      <td>OLD_ATTACK_CONTROLS_ENABLED - Old attack controls -</td>
      <td>bool</td>
      <td>Use Z, X, and C, not just Z, to time attacks. <br></td>
    </tr>
    <tr>
      <td>14</td>
      <td>BATTLE_MENU_SELECTION_REMEMBERED - Remember battle selection -</td>
      <td>bool</td>
      <td>Prevents the game from resetting your selection to "FIGHT" each turn. <br></td>
    </tr>
    <tr>
      <td>15</td>
      <td>SOUND_VOLUME - Sound effect volume -</td>
      <td>number</td>
      <td>Volume of sound effects. <br></td>
    </tr>
    <tr>
      <td>16</td>
      <td>MUSIC_VOLUME - Music volume -</td>
      <td>number</td>
      <td>Volume of music. <br></td>
    </tr>
    <tr>
      <td>17</td>
      <td>AUDIO_VOLUME - Master audio volume -</td>
      <td>number</td>
      <td>Volume of all audio. <br></td>
    </tr>
    <tr>
      <td>20</td>
      <td>OTHER_TEXT_COMMAND - Other text command -</td>
      <td>volatile <br> number</td>
      <td>Volatile. Controls how some characters' overworld sprites interact with their dialogue, among other things. <br></td>
    </tr>
    <tr>
      <td>21</td>
      <td>DOOR_FREEZE_TIMER - Door freeze timer -</td>
      <td>volatile <br> number</td>
      <td>Volatile. Controls timing of room fades. <br></td>
    </tr>
    <tr>
      <td>22</td>
      <td>X_SLOWING_DISABLED - Disable X slowing -</td>
      <td>bool</td>
      <td>Added in 1.08. Pressing Z while holding C in combat toggles it. Becomes debug-only in 1.09. <br></td>
    </tr>
    <tr>
      <td>23</td>
      <td>CAN_CLIMB - Climb unlocked -</td>
      <td>bool</td>
      <td>Whether you can climb walls using the Claimb Claws. <br></td>
    </tr>
    <tr>
      <td>29</td>
      <td>SUSIE_SHOW_EYES - Susie shows eyes -</td>
      <td>bool</td>
      <td>Makes Susie show her eyes at the end of Chapter 1. Ignored in Chapter 2; she shows her eyes anyway. <br></td>
    </tr>
    <tr>
      <td>30</td>
      <td>RALSEI_HAT_STATE - Ralsei hat state -</td>
      <td>map</td>
      <td>Controls Ralsei's face selection. Ignored in Chapter 2; he's hatless anyway. <br>0 = Hat<br>1 = Hood<br>2 = Hatless<br></td>
    </tr>
    <tr>
      <td>31</td>
      <td>LOUD_STEPS_DISABLED - Disable loud steps -</td>
      <td>bool</td>
      <td>Stops the echoing step sound found in the ?????? area, Great Door field, and Jevil's room. <br></td>
    </tr>
    <tr>
      <td>32</td>
      <td>EQUIP_COMMENTS_HIDDEN - Hide equip comments -</td>
      <td>bool</td>
      <td>Prevents Susie and Ralsei from commenting on items you give them when in room_man. <br></td>
    </tr>
    <tr>
      <td>33</td>
      <td>CHOICE_TIME_TAKEN - Choice time taken -</td>
      <td>volatile <br> number</td>
      <td>Volatile. The time, in frames, you take to make a choice. Used by Sans. <br></td>
    </tr>
    <tr>
      <td>34</td>
      <td>PARTY_ACTS_DISABLED - Party ACTs disabled -</td>
      <td>bool</td>
      <td>Initialized to 1, reset to 0 when unlocking S-Action and R-Action. <br></td>
    </tr>
    <tr>
      <td>35</td>
      <td>GAME_OVER_MODE - Game over mode -</td>
      <td>map</td>
      <td>Controls what the game does on game over. Usually 0. <br>0 = Normal Game Over<br>1 = Party Dojo<br>2 = Immediate respawn?<br></td>
    </tr>
    <tr>
      <td>36</td>
      <td>DOJO_FAILURE - Dojo failure -</td>
      <td>bool</td>
      <td>Set when losing Party Dojo battles (i.e. when flag 35 is 1). Affects prize and dialogue. <br></td>
    </tr>
    <tr>
      <td>37</td>
      <td>DOJO_ACTIVE - Dojo battle active -</td>
      <td>bool</td>
      <td>Alters battle win text and prevents you from gaining money outside of prizes. <br></td>
    </tr>
    <tr>
      <td>38</td>
      <td>BATTLE_END_MESSAGE_DISABLED - Hide battle-end message -</td>
      <td>bool</td>
      <td>Disables the battle end message. Used for SnowGraving Berdly and Party Dojo. <br></td>
    </tr>
    <tr>
      <td>39</td>
      <td>DOJO_BATTLE_ABORTED - Dojo aborted -</td>
      <td>bool</td>
      <td>Something to do with immediately ending Party Dojo battles, also used in the Jackenstein fight. <br></td>
    </tr>
    <tr>
      <td>40</td>
      <td>VIOLENCE_COUNT - Violences -</td>
      <td>number</td>
      <td>Total number of enemies defeated through FIGHTing. Can be reduced by obtaining forgiveness from Rudinn or Hathy. <br></td>
    </tr>
    <tr>
      <td>41</td>
      <td>SPARE_COUNT - Spares -</td>
      <td>number</td>
      <td>Total number of enemies SPAREd. Unaccessed. <br></td>
    </tr>
    <tr>
      <td>42</td>
      <td>PACIFY_COUNT - Pacifies -</td>
      <td>number</td>
      <td>Total number of enemies Pacify/Sleep Mist-ed. Unaccessed. <br></td>
    </tr>
    <tr>
      <td>43</td>
      <td>UNCONTROLLED_SUSIE_VIOLENCE_COUNT - Susie auto-violences -</td>
      <td>number</td>
      <td>Violences committed by Susie while not under player control. In SURVEY_PROGRAM and Chapter 1&2 it's never set due to a bug. It is possible to get the Chapter 1 Overthrow ending even if this is 1. <br></td>
    </tr>
    <tr>
      <td>44</td>
      <td>KILL_COUNT - Kills -</td>
      <td>number</td>
      <td>Total number of enemies you killed. Includes SnowGrave and killing Pipis. <br></td>
    </tr>
    <tr>
      <td>45</td>
      <td>FREEZE_COUNT - Freezes -</td>
      <td>number</td>
      <td>Total number of enemies you froze. <br></td>
    </tr>
    <tr>
      <td>49</td>
      <td>LAST_ENCOUNTER_TP - Last battle TP -</td>
      <td>number</td>
      <td>Amount of TP gained in last encounter, used for Tenna's scoring system. <br></td>
    </tr>
    <tr>
      <td>50</td>
      <td>LAST_ENCOUNTER_OUTCOME - Last battle result -</td>
      <td>map</td>
      <td>Volatile. Contains what you did in the last encounter. For multiple enemies, priority is Violence > Spare > Pacify > IceShock. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>51</td>
      <td>LAST_ENEMY_1_OUTCOME - Enemy 1 result -</td>
      <td>map</td>
      <td>Volatile. What you did to the top monster in the last encounter. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>52</td>
      <td>LAST_ENEMY_2_OUTCOME - Enemy 2 result -</td>
      <td>map</td>
      <td>Volatile. What you did to the middle monster in the last encounter. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>53</td>
      <td>LAST_ENEMY_3_OUTCOME - Enemy 3 result -</td>
      <td>map</td>
      <td>Volatile. What you did to the bottom monster in the last encounter. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>54</td>
      <td>ENCOUNTER_RESULT_FLAG_ID - Battle-result pointer -</td>
      <td>volatile <br> number</td>
      <td>Volatile. Contains a numerical value representing the current encounter, which is used to permanently store the outcome of that encounter in a flag. <br></td>
    </tr>
    <tr>
      <td>55</td>
      <td>FROZEN_ENEMY_X - Frozen enemy X -</td>
      <td>volatile <br> number</td>
      <td>Volatile. Used to return enemies to the correct spot in the overworld when frozen. <br></td>
    </tr>
    <tr>
      <td>56</td>
      <td>FROZEN_ENEMY_Y - Frozen enemy Y -</td>
      <td>volatile <br> number</td>
      <td>Volatile. Used to return enemies to the correct spot in the overworld when frozen. <br></td>
    </tr>
    <tr>
      <td>60</td>
      <td>DOJO_NEXT_ENCOUNTER - Dojo next encounter -</td>
      <td>map</td>
      <td>Volatile. Used to chain encounters for the Party Dojo All Stars challenge. <br>0 = Default state<br>90 = Werewires<br>91 = Smorgasbord<br>92 = Tasques + Maus<br>93 = Swatchlings<br>94 = Werewerewires<br></td>
    </tr>
    <tr>
      <td>61</td>
      <td>RECRUITING_DISABLED - Recruiting disabled -</td>
      <td>bool</td>
      <td>Prevents you from recruiting enemies in Party Dojo battles. <br></td>
    </tr>
    <tr>
      <td>62</td>
      <td>NON_NARRATIVE_BATTLE_INTRO - Non-narrative intro -</td>
      <td>bool</td>
      <td>Used when Noelle enters her first battle and when Susie wants to demonstrate UltimateHeal to not use the normal battle introduction typer. <br></td>
    </tr>
    <tr>
      <td>63</td>
      <td>LAST_ENEMY_WAS_VIOLENCED - Last enemy violenced -</td>
      <td>volatile <br> bool</td>
      <td>Volatile. Triggers "You/Noelle became stronger" when violencing enemies. <br></td>
    </tr>
    <tr>
      <td>64</td>
      <td>STORAGE_CAPACITY - Storage capacity -</td>
      <td>number</td>
      <td>The amount of items you can keep in your pockets. Always 24 in Chapters 2 and 3, 36 in Chapter 4, code exists to set it to 48 in Chapter 6 and later. <br></td>
    </tr>
    <tr>
      <td>65</td>
      <td>LEVEL_UP_COUNT_CH2 - Level-ups -</td>
      <td>number</td>
      <td>The number of times you have leveled up by violently defeating an encounter. Used for certain increases that only occur every 2, 4, or 10 encounters. <br></td>
    </tr>
    <tr>
      <td>66</td>
      <td>AT_MAGIC_GAIN_COUNT_CH2 - AT/Magic gains -</td>
      <td>number</td>
      <td>The number of times your AT and Magic have increased due to leveling up (every ten encounters). Used to prevent overly increasing them when sealing the fountain. <br></td>
    </tr>
    <tr>
      <td>100</td>
      <td>OBTAINED_GLOWSHARD - Got Glowshard -</td>
      <td>bool</td>
      <td>Whether you obtained the Glowshard. Prevents it from re-appearing. <br></td>
    </tr>
    <tr>
      <td>101</td>
      <td>DARK_CANDY_TREE_1_TAKEN - First candy tree -</td>
      <td>map</td>
      <td>How much Dark Candy you've taken from the first Dark Candy tree. <br>0 = None<br>1 = One candy<br>2 = Both candies<br></td>
    </tr>
    <tr>
      <td>102</td>
      <td>DARK_CANDY_TREE_2_TAKEN - Second candy tree -</td>
      <td>map</td>
      <td>How much Dark Candy you've taken from the second Dark Candy tree. <br>0 = None<br>1 = One candy<br>2 = Both candies<br></td>
    </tr>
    <tr>
      <td>103</td>
      <td>OBTAINED_BROKEN_CAKE_PIECE - Got Broken Cake -</td>
      <td>bool</td>
      <td>Whether you took a piece of the Broken Cake. <br></td>
    </tr>
    <tr>
      <td>104</td>
      <td>OBTAINED_WHITE_RIBBON - Got White Ribbon -</td>
      <td>bool</td>
      <td>Whether you got the White Ribbon. <br></td>
    </tr>
    <tr>
      <td>105</td>
      <td>OBTAINED_IRON_SHACKLE - Got Iron Shackle -</td>
      <td>bool</td>
      <td>Whether you took the Iron Shackle. <br></td>
    </tr>
    <tr>
      <td>106</td>
      <td>ATE_MOSS_CH1 - Ate Moss -</td>
      <td>bool</td>
      <td>Whether you ate the moss in Chapter 1. Allows you to obtain the Moss Finder title. <br></td>
    </tr>
    <tr>
      <td>107</td>
      <td>OBTAINED_DANCER_REVIVE_MINT - Got the dancer-room Revive Mint -</td>
      <td>bool</td>
      <td>Whether you got the Revive Mint from the Scissor Dancers room. <br></td>
    </tr>
    <tr>
      <td>108</td>
      <td>OBTAINED_RAGGER - Got Ragger -</td>
      <td>bool</td>
      <td>Whether you got the Ragger. Affects the Royal Coat Rack's dialogue about it. <br></td>
    </tr>
    <tr>
      <td>109</td>
      <td>OBTAINED_DICE_BRACE - Got Dice Brace -</td>
      <td>bool</td>
      <td>Whether you got the Dice Brace. <br></td>
    </tr>
    <tr>
      <td>110</td>
      <td>OBTAINED_BLOXER_ROOM_MONEY - Got the Bloxer-room money -</td>
      <td>bool</td>
      <td>Whether you got the 40D$ from that room with Bloxers. <br></td>
    </tr>
    <tr>
      <td>111</td>
      <td>UNUSED_BLOXER_ROOM_REVIVE_MINT - Got Bloxer Mint -</td>
      <td>bool</td>
      <td>Whether you got a Revive Mint from that room with Bloxers. Unused because there isn't actually a Revive Mint chest in that room. <br></td>
    </tr>
    <tr>
      <td>112</td>
      <td>OBTAINED_JEVIL_REWARD - Got Jevil reward -</td>
      <td>bool</td>
      <td>Whether you got the Jevilstail/Devilsknife from a chest. It appears outside the room if your inventory is full after the battle. <br></td>
    </tr>
    <tr>
      <td>113</td>
      <td>OBTAINED_CLUBS_SANDWICH - Got Clubswich -</td>
      <td>bool</td>
      <td>Whether you got the Clubs Sandwich. <br></td>
    </tr>
    <tr>
      <td>114</td>
      <td>OBTAINED_CASTLE_REVIVE_MINT - Got the Card Castle Revive Mint -</td>
      <td>bool</td>
      <td>Whether you got the Revive Mint from that chest that appears when you interact with the portraits. <br></td>
    </tr>
    <tr>
      <td>115</td>
      <td>OBTAINED_BROKEN_KEY_A - Got Key A -</td>
      <td>bool</td>
      <td>Whether you got the Broken Key A. Also set if you defeat the Knight in Chapter 3 due to an encounterflag reuse. <br></td>
    </tr>
    <tr>
      <td>116</td>
      <td>OBTAINED_BROKEN_KEY_B - Got Key B -</td>
      <td>bool</td>
      <td>Whether you got the Broken Key B. <br></td>
    </tr>
    <tr>
      <td>117</td>
      <td>OBTAINED_BROKEN_KEY_C - Got Key C -</td>
      <td>bool</td>
      <td>Whether you got the Broken Key C. <br></td>
    </tr>
    <tr>
      <td>118</td>
      <td>OBTAINED_FIRST_GLOW_WRIST - Got the first Glow Wrist -</td>
      <td>bool</td>
      <td>Whether you got the first Glow Wrist. <br></td>
    </tr>
    <tr>
      <td>119</td>
      <td>OBTAINED_NUBERT_TREASURE - Got Nubert's Fiber Scarf -</td>
      <td>bool</td>
      <td>Whether you got the Fiber Scarf. <br></td>
    </tr>
    <tr>
      <td>120</td>
      <td>OBTAINED_SECOND_GLOW_WRIST - Got the second Glow Wrist -</td>
      <td>bool</td>
      <td>Whether you got that other Glow Wrist. <br></td>
    </tr>
    <tr>
      <td>121</td>
      <td>TENNA_ENCOUNTER_OUTCOME - Tenna -</td>
      <td>map</td>
      <td>Tracks the state of the Tenna battle. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>122</td>
      <td>OBTAINED_TENSION_BIT - Got Tension Bit -</td>
      <td>bool</td>
      <td>Whether you got the Tension Bit. <br></td>
    </tr>
    <tr>
      <td>123</td>
      <td>OBTAINED_THIRD_REVIVE_MINT_CH2 - Got the third Revive Mint -</td>
      <td>bool</td>
      <td>Whether you got the THIRD Revive Mint. <br></td>
    </tr>
    <tr>
      <td>125</td>
      <td>UNUSED_REVIVE_DUST_FLAG - Revive Dust flag -</td>
      <td>number</td>
      <td>Unused. Intended for obtaining the Revive Dust, but overwritten by 137. <br></td>
    </tr>
    <tr>
      <td>126</td>
      <td>OBTAINED_TRASH_CAN_20_DOLLARS - Got $20 from the trash can -</td>
      <td>bool</td>
      <td>Whether you got 20D$ from the twenty-dollar trash can. <br></td>
    </tr>
    <tr>
      <td>127</td>
      <td>OBTAINED_TRASH_CAN_80_DOLLARS - Got $80 from the trash can -</td>
      <td>bool</td>
      <td>Whether you got 80D$ from the eighty-dollar trash can. <br></td>
    </tr>
    <tr>
      <td>128</td>
      <td>OBTAINED_TRASH_CAN_CD_BAGEL - Got a CD Bagel from the trash can -</td>
      <td>bool</td>
      <td>Whether you got a CD Bagel from the CD Bagel trash can. <br></td>
    </tr>
    <tr>
      <td>129</td>
      <td>OBTAINED_RAGGER_2 - Got Ragger 2 -</td>
      <td>bool</td>
      <td>Whether you got the Ragger2. <br></td>
    </tr>
    <tr>
      <td>130</td>
      <td>OBTAINED_BOUNCE_BLADE - Got Bounce Blade -</td>
      <td>bool</td>
      <td>Whether you got the Bounce Blade. <br></td>
    </tr>
    <tr>
      <td>131</td>
      <td>OBTAINED_SECOND_TRASH_CAN_20_DOLLARS - Got the second trash-can $20 -</td>
      <td>bool</td>
      <td>Whether you got 20D$ from the other twenty-dollar trash can. <br></td>
    </tr>
    <tr>
      <td>132</td>
      <td>OBTAINED_SECOND_TRASH_CAN_CD_BAGEL - Got the second trash-can CD Bagel -</td>
      <td>bool</td>
      <td>Whether you got a CD Bagel from the other CD Bagel trash can. <br></td>
    </tr>
    <tr>
      <td>133</td>
      <td>OBTAINED_ONE_DOLLAR_CHEST - Got $1 from the chest -</td>
      <td>bool</td>
      <td>Whether you got the $1 from the one-dollar treasure chest. <br></td>
    </tr>
    <tr>
      <td>134</td>
      <td>OBTAINED_PINK_RIBBON - Got Pink Ribbon -</td>
      <td>bool</td>
      <td>Whether you got the Pink Ribbon. <br></td>
    </tr>
    <tr>
      <td>135</td>
      <td>OBTAINED_CD_BAGEL_CHEST - Got the CD Bagel chest -</td>
      <td>bool</td>
      <td>Whether you got a CD Bagel from the CD Bagel treasure chest. <br></td>
    </tr>
    <tr>
      <td>136</td>
      <td>OBTAINED_SECRET_DARK_CANDY - Got the secret Dark Candy -</td>
      <td>bool</td>
      <td>Whether you got a Dark Candy from the secret Dark Candy location. <br></td>
    </tr>
    <tr>
      <td>137</td>
      <td>OBTAINED_REVIVE_DUST - Got Revive Dust -</td>
      <td>bool</td>
      <td>Whether you got the Revive Dust. <br></td>
    </tr>
    <tr>
      <td>138</td>
      <td>OBTAINED_FOURTH_REVIVE_MINT - Got the fourth Revive Mint -</td>
      <td>bool</td>
      <td>Whether you got the fourth Revive Mint from a painting. <br></td>
    </tr>
    <tr>
      <td>139</td>
      <td>OBTAINED_MANSION_GLOWSHARD - Got the Mansion Glowshard -</td>
      <td>bool</td>
      <td>Whether you got the Glowshard in Queen's Mansion, found by activating all the platters behind the door on the 2F moving vases room. <br></td>
    </tr>
    <tr>
      <td>140</td>
      <td>OBTAINED_TRASH_CAN_DARK_CANDY - Got Dark Candy from the trash can -</td>
      <td>bool</td>
      <td>Whether you got a Dark Candy from the Dark Candy trash can. <br></td>
    </tr>
    <tr>
      <td>141</td>
      <td>OBTAINED_CHAIN_MAIL - Got Chain Mail -</td>
      <td>bool</td>
      <td>Whether you got the Chain Mail armor. <br></td>
    </tr>
    <tr>
      <td>142</td>
      <td>OBTAINED_SPAMTON_REWARD - Got Spamton reward -</td>
      <td>bool</td>
      <td>Whether you got the Dealmaker/Puppet Scarf from a chest. There's one immediately after you beat Spamton, and one back at My Castle Town. <br></td>
    </tr>
    <tr>
      <td>176</td>
      <td>SOUND_OF_JUSTICE_SUSIE_ENCOUNTER_OUTCOME - Susie -</td>
      <td>map</td>
      <td>Tracks the state of the Susie-only stage of the Sound of Justice Battle, always 2. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>177</td>
      <td>TITAN_SPAWN_ENCOUNTER_OUTCOME - Spawn -</td>
      <td>map</td>
      <td>Tracks the state of the Titan Spawn encounter. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>186</td>
      <td>SOUND_OF_JUSTICE_KRIS_ENCOUNTER_OUTCOME - Kris -</td>
      <td>map</td>
      <td>Tracks the state of the Kris stage of the Sound of Justice Battle, always 2. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>200</td>
      <td>RAN_IN_SCHOOL - Ran to Susie at school -</td>
      <td>bool</td>
      <td>Whether you ran to Susie in the Chapter 1 school scene. Unaccessed. <br></td>
    </tr>
    <tr>
      <td>201</td>
      <td>SOLVED_EYE_PUZZLE - Solved the eye puzzle -</td>
      <td>bool</td>
      <td>Whether you solved the eye puzzle in the ?????? area. <br></td>
    </tr>
    <tr>
      <td>202</td>
      <td>DARK_AREA_MOVEMENT_CHOICE - Susie approach -</td>
      <td>map</td>
      <td>How you proceeded once finding Susie in the ?????? area. <br>0 = Walked<br>1 = Ran<br>2 = Wrong way<br></td>
    </tr>
    <tr>
      <td>203</td>
      <td>SKIPPED_PROPHECY - Skipped -</td>
      <td>bool</td>
      <td>Whether you skipped Ralsei's prophecy. Lancer explains it instead. <br></td>
    </tr>
    <tr>
      <td>204</td>
      <td>RALSEI_SUBJECT_RESPONSE - Ralsei subject answer -</td>
      <td>map</td>
      <td>How you answered Ralsei when he said he had no subjects... that is, unused. <br>0 = Default state<br>1 = I'll be your subject<br>2 = Keep dreaming<br></td>
    </tr>
    <tr>
      <td>205</td>
      <td>RALSEI_TUTORIAL_OUTCOME - Outcome -</td>
      <td>map</td>
      <td>What happened during Ralsei's tutorial. <br>0 = Skipped tutorial<br>1 = Success<br>2 = Hug Ralsei (in unused version of tutorial)<br>3 = Beat up Ralsei<br>4 = Beat up dummy<br>5 = Continued defending<br>6 = Missed dummy<br></td>
    </tr>
    <tr>
      <td>206</td>
      <td>LEARNED_TO_RUN - Learned to run -</td>
      <td>bool</td>
      <td>Set to 1 whether Ralsei explains it or you demonstrate. Just prevents him from asking again. <br></td>
    </tr>
    <tr>
      <td>207</td>
      <td>MANUAL_DISPOSAL_PROGRESS - Manual disposal -</td>
      <td>map</td>
      <td>Your progress on being a terrible person. Ralsei gives you a trash can for the manual instead of a stand, in case you ever want to trash it again. <br>0 = Default state<br>1 = Dropped once<br>2 = Dropped twice<br></td>
    </tr>
    <tr>
      <td>208</td>
      <td>RE_CONVINCED_RUDINN - Re-convinced Rudinn -</td>
      <td>bool</td>
      <td>Whether you Convinced Rudinn after failing to do. Unused, since it works first try now. <br></td>
    </tr>
    <tr>
      <td>209</td>
      <td>SAW_FIELD_SONG - Saw the Field title card -</td>
      <td>bool</td>
      <td>Prevents you from seeing the Field of Hopes and Dreams title every single room. <br></td>
    </tr>
    <tr>
      <td>210</td>
      <td>LANCER_PRE_HATHY_DIALOGUE - Lancer dialogue -</td>
      <td>map</td>
      <td>Alters Lancer's dialogue if interacted with prior to the triple Hathy fight. <br>0 = Default state<br>1 = Talked<br>2 = Did not talk<br></td>
    </tr>
    <tr>
      <td>211</td>
      <td>C_ROUND_OUTCOME - Outcome -</td>
      <td>map</td>
      <td>What happened to C. Round. Can skip Ralsei telling Susie not to fight. <br>0 = Default state<br>1 = Complimented by Susie<br>2 = Warned<br>3 = Attacked by Kris/Ralsei<br></td>
    </tr>
    <tr>
      <td>212</td>
      <td>VANDALIZED_BOX_PUZZLE_STATE - Progress -</td>
      <td>map</td>
      <td>Progress on the vandalized box puzzle. <br>0 = Default state<br>1 = Initiated puzzle<br>2 = Failure (unused)<br></td>
    </tr>
    <tr>
      <td>214</td>
      <td>TEAM_NAME - Team name -</td>
      <td>map</td>
      <td>The name of your team. <br>0 = The Guys<br>1 = The $!$? Squad<br>2 = The Lancer Fan Club<br>3 = The Fun Gang<br></td>
    </tr>
    <tr>
      <td>215</td>
      <td>TALKED_TO_JIGSAW_JOE - Talked to Jigsaw Joe -</td>
      <td>bool</td>
      <td>Whether you talked to Joe (and were inevitably offered a tutorial). Makes him help with the Warp Door. <br></td>
    </tr>
    <tr>
      <td>216</td>
      <td>DONATED_TO_HOLE - Donated to the hole -</td>
      <td>bool</td>
      <td>Whether you put a dollar in the donation hole. <br></td>
    </tr>
    <tr>
      <td>217</td>
      <td>SOLVED_FIRST_ROUXLS_PUZZLE - Solved Rouxls's first puzzle -</td>
      <td>bool</td>
      <td>Whether you solved Rouxls's first puzzle. <br></td>
    </tr>
    <tr>
      <td>218</td>
      <td>SOLVED_SECOND_ROUXLS_PUZZLE - Solved Rouxls's second puzzle -</td>
      <td>bool</td>
      <td>Whether you solved Rouxls's second puzzle. <br></td>
    </tr>
    <tr>
      <td>220</td>
      <td>THRASH_MACHINE_HEAD - Head -</td>
      <td>map</td>
      <td>Your Thrash Machine's head. <br>0 = Laser<br>1 = Sword<br>2 = Flame<br>3 = Duck<br>-1 = In design<br></td>
    </tr>
    <tr>
      <td>221</td>
      <td>THRASH_MACHINE_BODY - Body -</td>
      <td>map</td>
      <td>Your Thrash Machine's chassis. <br>0 = Plain<br>1 = Wheel<br>2 = Tank<br>3 = Duck<br>-1 = In design<br></td>
    </tr>
    <tr>
      <td>222</td>
      <td>THRASH_MACHINE_SHOE - Shoe -</td>
      <td>map</td>
      <td>Your Thrash Machine's... well, there's a lot of variance here. <br>0 = Shoes<br>1 = Wheels<br>2 = Treads<br>3 = Duck<br>-1 = In design<br></td>
    </tr>
    <tr>
      <td>223</td>
      <td>THRASH_MACHINE_HEAD_COLOR - Head color -</td>
      <td>color</td>
      <td>Your Thrash Machine's head color. <br></td>
    </tr>
    <tr>
      <td>224</td>
      <td>THRASH_MACHINE_BODY_COLOR - Body color -</td>
      <td>color</td>
      <td>Your Thrash Machine's chassis color. <br></td>
    </tr>
    <tr>
      <td>225</td>
      <td>THRASH_MACHINE_SHOE_COLOR - Shoe color -</td>
      <td>color</td>
      <td>Your Thrash Machine's shoe color. <br></td>
    </tr>
    <tr>
      <td>226</td>
      <td>MADE_THRASH_MACHINE - Designed the Thrash Machine -</td>
      <td>bool</td>
      <td>Whether you designed the Thrash Machine yet. <br></td>
    </tr>
    <tr>
      <td>229</td>
      <td>LANCER_FOLLOW_DIALOGUE_PROGRESS - Lancer dialogue -</td>
      <td>map</td>
      <td>How far Lancer has followed you after joining the team. <br>0 = Default state<br>1 = Monogrammed track jackets<br>3 = Just chill with us<br>4 = Stop making fun of me<br>5 = Darkberry Teacakes (unused)<br>6 = A candy tree!<br>7 = My teeth are disintegrating!<br>8 = Does your dad seem happy?<br>9 = I also feel kinda...<br>10 = ...maybe.<br>11 = That's the FOUNTAIN!<br>12 = All we gotta do is crush them.<br>99 = Max value (unused)<br></td>
    </tr>
    <tr>
      <td>231</td>
      <td>JAIL_INTERACTION_COUNT - Object interactions -</td>
      <td>number</td>
      <td>The number of times you have interacted with objects while in jail. The cutscene is triggered by talking to Ralsei after 3+ interactions. <br></td>
    </tr>
    <tr>
      <td>232</td>
      <td>INTERACTED_WITH_SALSA - Interacted with the salsa stump -</td>
      <td>bool</td>
      <td>Whether you interacted with the salsa stump. NOT what you actually did; that isn't saved. <br></td>
    </tr>
    <tr>
      <td>233</td>
      <td>ASKED_ROYAL_COAT_RACK_ABOUT_CHEST - Asked the Royal Coat Rack about the chest -</td>
      <td>bool</td>
      <td>Whether you talked to the Royal Coat Rack before taking the Ragger. Changes their dialogue if you take it without asking. <br></td>
    </tr>
    <tr>
      <td>234</td>
      <td>SOLVED_CLOVER_PUZZLE - Solved the Clover suit puzzle -</td>
      <td>bool</td>
      <td>Whether you solved the suits puzzle before the Clover fight. <br></td>
    </tr>
    <tr>
      <td>235</td>
      <td>UNUSED_CLOVER_PUZZLE_BARRIER_FLAG - Clover puzzle barrier -</td>
      <td>bool</td>
      <td>Unused barrier flag for the suits puzzle before the Clover fight. <br></td>
    </tr>
    <tr>
      <td>236</td>
      <td>TALKED_TO_ALL_CLOVER_HEADS - Talked to all Clover faces -</td>
      <td>bool</td>
      <td>Set when talking to all of Clover before her fight. Alters her dialogue. <br></td>
    </tr>
    <tr>
      <td>237</td>
      <td>SOLVED_DARK_PUZZLE - Solved -</td>
      <td>bool</td>
      <td>Whether you solved the puzzle in the darknening room. It does not save if you did it without going in the middle. <br></td>
    </tr>
    <tr>
      <td>238</td>
      <td>SUSIE_BOUGHT_SNACK - Susie's snack -</td>
      <td>bool</td>
      <td>Whether Susie and Lancer bought their Hearts Donut yet. <br></td>
    </tr>
    <tr>
      <td>239</td>
      <td>CARD_CASTLE_ELEVATOR_FLOOR - Elevator floor -</td>
      <td>map</td>
      <td>Volatile. Tracks the floor you're currently on when in elevators. <br>0 = Basement B1<br>1 = Floor 1F<br>2 = Floor 5F<br>3 = ???? (JEVIL)<br></td>
    </tr>
    <tr>
      <td>240</td>
      <td>CARD_CASTLE_ELEVATOR_UNLOCKED - Unlocked -</td>
      <td>bool</td>
      <td>Whether you have unlocked the Card Castle elevator by going to floor 5F. <br></td>
    </tr>
    <tr>
      <td>241</td>
      <td>JEVIL_PROGRESS - Progress -</td>
      <td>map</td>
      <td>Your progress with JEVIL. Alters Seam's dialogue. <br>0 = Default state<br>1 = Talked to JEVIL<br>5 = Opened door<br>6 = Fought<br>7 = Spared<br></td>
    </tr>
    <tr>
      <td>242</td>
      <td>JEVIL_REWARD_CHEST_ITEM - Overflow chest -</td>
      <td>map</td>
      <td>The item in the chest outside JEVIL's room, if you don't have enough storage space for it. See also flag 112. <br>0 = Default state<br>1 = Devilsknife<br>2 = Jevilstail<br></td>
    </tr>
    <tr>
      <td>243</td>
      <td>RUDINN_DIALOGUE_OUTCOME - Rudinn -</td>
      <td>map</td>
      <td>The status of your talking to Rudinn in Card Castle. Special dialogue if set to 3 but you then hurt Rudinns. <br>0 = Default state<br>1 = Apologized<br>2 = Did not apologize<br>3 = Did not need to apologize<br></td>
    </tr>
    <tr>
      <td>244</td>
      <td>TALKED_TO_HATHY - Talked to Hathy -</td>
      <td>bool</td>
      <td>Whether you talked to Hathy in Card Castle. Only set if you had two or fewer Hathy kills. <br></td>
    </tr>
    <tr>
      <td>245</td>
      <td>SUMMONED_BLUH_CHEST - Summoned the Bluh Chest -</td>
      <td>bool</td>
      <td>Whether you interacted with all four Bluh Paintings, summoning the Bluh Chest. <br></td>
    </tr>
    <tr>
      <td>246</td>
      <td>CHECKED_K_ROUND - Checked K. Round -</td>
      <td>bool</td>
      <td>Whether you Checked K. Round the first time, changing its act to Checkers (including in the second fight). <br></td>
    </tr>
    <tr>
      <td>247</td>
      <td>SPARED_KING - Spared King -</td>
      <td>bool</td>
      <td>Whether you exhausted King rather than fighting him. <br></td>
    </tr>
    <tr>
      <td>248</td>
      <td>VIOLENT_ENDING_CH1 - Violent ending -</td>
      <td>bool</td>
      <td>Whether you got the bad (beat people up) ending in Chapter 1. Minor dialogue differences in Castle Town. <br></td>
    </tr>
    <tr>
      <td>249</td>
      <td>SPARED_LANCER - Spared Lancer and Susie -</td>
      <td>bool</td>
      <td>Whether you spared Lancer and Susie. <br></td>
    </tr>
    <tr>
      <td>250</td>
      <td>THRASH_MACHINE_REMATCH_COUNT - Rematches -</td>
      <td>number</td>
      <td>The number of times you fought Lancer and Susie, thus requiring them to blow up a Thrash Machine. Unique dialogue at 1 and 2. <br></td>
    </tr>
    <tr>
      <td>251</td>
      <td>SHORTCUT_DOOR_HELP - Warp Door restored -</td>
      <td>bool</td>
      <td>Whether Jigsaw Joe helped restore the Warp Door. No functional change. <br></td>
    </tr>
    <tr>
      <td>252</td>
      <td>INSPECTED_BEDS_CH1 - Inspected the beds -</td>
      <td>bool</td>
      <td>Whether you inspected all four beds in Chapter 1, becoming a Bed Inspector. <br></td>
    </tr>
    <tr>
      <td>253</td>
      <td>TRADED_TOP_CAKE - Traded the Top Cake -</td>
      <td>bool</td>
      <td>Whether you returned the TopCake, receiving a SpinCake in its place. <br></td>
    </tr>
    <tr>
      <td>254</td>
      <td>TALKED_TO_STARWALKER_CH1 - Talked to original &ensp;*Starwalker* -</td>
      <td>bool</td>
      <td>Whether you talked to the original Starwalker. That's foresight. <br></td>
    </tr>
    <tr>
      <td>255</td>
      <td>RUDY_DIALOGUE_PROGRESS_CH1 - Dialogue progress -</td>
      <td>map</td>
      <td>Progress talking with Rudolph Holiday in Chapter 1. <br>0 = Default state<br>1 = Noelle left<br>2 = Talked to Rudy<br></td>
    </tr>
    <tr>
      <td>256</td>
      <td>TALKED_TO_BERDLY_AT_HOSPITAL_WINDOW - Talked to Berdly at the hospital window -</td>
      <td>bool</td>
      <td>Whether you talked to Berdly about visiting the hospital window to have something thrown at him. Slightly alters his dialogue about How to Draw Dragons. <br></td>
    </tr>
    <tr>
      <td>257</td>
      <td>PUT_FINGERS_IN_PICNIC_TABLE - Put fingers in the picnic table -</td>
      <td>bool</td>
      <td>Whether you tried to put your fingers in the picnic table. <br></td>
    </tr>
    <tr>
      <td>258</td>
      <td>ONION_STATUS_CH1 - Friendship -</td>
      <td>map</td>
      <td>Onion's status. <br>0 = Default state<br>1 = Talking (volatile)<br>2 = Befriended<br>3 = Rejected<br></td>
    </tr>
    <tr>
      <td>259</td>
      <td>ONION_PLAYER_NAME - Your name -</td>
      <td>map</td>
      <td>The name you told Onion was yours. <br>0 = Default state<br>1 = Kris<br>2 = Hippopotamus<br></td>
    </tr>
    <tr>
      <td>260</td>
      <td>ONION_NAME - Onion's name -</td>
      <td>map</td>
      <td>The name you told Onion was theirs. <br>0 = Default state<br>1 = Onion<br>2 = Beauty<br>3 = Asriel II<br>4 = Disgusting<br></td>
    </tr>
    <tr>
      <td>261</td>
      <td>QC_DIALOGUE_PROGRESS_CH1 - Dialogue progress -</td>
      <td>map</td>
      <td>Tracks your talking with QC. <br>0 = Default state<br>1 = Received Hot Chocolate<br>2 = Full inventory<br></td>
    </tr>
    <tr>
      <td>262</td>
      <td>BOUQUET_QUEST_PROGRESS_CH1 - Bouquet quest -</td>
      <td>map</td>
      <td>Progress toward failing to redeem Toriel and Asgore's relationship in Chapter 1. <br>0 = Default state<br>1 = In flower shop<br>2 = Received bouquet<br>3 = Gave to Toriel<br>4 = Disposed of<br></td>
    </tr>
    <tr>
      <td>263</td>
      <td>ASGORE_FRIDGE_EGG_STATUS - Fridge egg -</td>
      <td>map</td>
      <td>The Chapter 1 egg status, with regards to Asgore's fridge. Each stage correlates with an egg quantity in the fridge. <br>0 = (0) Default state<br>1 = (1) Egg dropped/fridge inspected eggless<br>2 = (2) Egg put in fridge<br></td>
    </tr>
    <tr>
      <td>264</td>
      <td>ASGORE_STAIRS_ENTRY_X - Asgore stairs door side -</td>
      <td>volatile <br> number</td>
      <td>Volatile. Persists the different door sides when going upstairs in Asgore's fridge via Kris's x-coordinate. <br></td>
    </tr>
    <tr>
      <td>265</td>
      <td>TALKED_TO_CATTY_CH1 - Talked to Catty -</td>
      <td>bool</td>
      <td>Whether you talked to Catty in Chapter 1. <br></td>
    </tr>
    <tr>
      <td>267</td>
      <td>UNUSED_TORIEL_DIALOGUE_PROGRESS - Toriel talk -</td>
      <td>map</td>
      <td>Progress talking to Toriel in an unused variant. <br>0 = Headband<br>1 = Go to bed<br>-10 = Kris...?<br></td>
    </tr>
    <tr>
      <td>268</td>
      <td>CALLED_TORIEL_FROM_HOME - Called home from house -</td>
      <td>bool</td>
      <td>Whether you called Toriel's home phone, while at home. Unaccessed. <br></td>
    </tr>
    <tr>
      <td>269</td>
      <td>TALKED_TO_ALPHYS_CH1 - Talked to Alphys -</td>
      <td>bool</td>
      <td>Whether you met Alphys after school in Chapter 1. Alters her dialogue the morning of Chapter 2. <br></td>
    </tr>
    <tr>
      <td>270</td>
      <td>TALKED_TO_UNDYNE_CH1 - Talked to Undyne -</td>
      <td>bool</td>
      <td>Whether you met Undyne in Chapter 1. <br></td>
    </tr>
    <tr>
      <td>271</td>
      <td>BURGERPANTS_DIALOGUE_PROGRESS_CH1 - Burgerpants -</td>
      <td>map</td>
      <td>Progress chatting with BurgerPizzaSodaCandyPants. <br>0 = Default state<br>1 = Mask off<br>2 = Talked<br></td>
    </tr>
    <tr>
      <td>272</td>
      <td>TORIEL_CALL_COUNT - Toriel calls -</td>
      <td>number</td>
      <td>The number of times you called Toriel after school. If zero when leaving the school, she calls you instead, incrementing the flag. <br></td>
    </tr>
    <tr>
      <td>273</td>
      <td>SANS_DIALOGUE_PROGRESS_CH1 - Dialogue progress -</td>
      <td>map</td>
      <td>Progress chatting up the funny bone man in Chapter 1. <br>0 = Default state<br>1 = Talked<br>2 = Invited over<br></td>
    </tr>
    <tr>
      <td>274</td>
      <td>SANS_PHONE_PROGRESS - Phone number -</td>
      <td>map</td>
      <td>Your progress toward being called an idiot baby. <br>0 = Default state<br>1 = Received number<br>2 = Called<br></td>
    </tr>
    <tr>
      <td>275</td>
      <td>IDIOT_BABY_STATUS - Idiot baby -</td>
      <td>map</td>
      <td>What you are. <br>0 = None<br>1 = Idiot<br>2 = Baby<br>3 = Idiot Baby<br></td>
    </tr>
    <tr>
      <td>276</td>
      <td>NOELLE_DIALOGUE_PROGRESS_CH1 - Dialogue progress -</td>
      <td>map</td>
      <td>Your progress talking to Noelle outside her house in Chapter 1. If 2, she gives Susie the Light Candy in Chapter 2. <br>0 = Default state<br>1 = Talked<br>2 = Talked about Susie<br></td>
    </tr>
    <tr>
      <td>277</td>
      <td>HOME_RETURN_COUNT_CH1 - Returns -</td>
      <td>number</td>
      <td>The number of times you have returned home at the end of Chapter 1. Special dialogue at 0, 1, and 7; stops counting at 8. <br></td>
    </tr>
    <tr>
      <td>278</td>
      <td>USED_RUDY_SINK_CH1 - Used Rudy's sink -</td>
      <td>bool</td>
      <td>Whether you used the sink in Chapter 1 (of the 1&2 demo). Rudy comments on you "loving that sink". <br></td>
    </tr>
    <tr>
      <td>279</td>
      <td>LOADED_LEGACY_FILE - Loaded legacy file -</td>
      <td>bool</td>
      <td>Set to 1 while loading a Chapter 1 file (which has different room offsets). If 1 on an old file, you might load into a Chapter 2 room. <br></td>
    </tr>
    <tr>
      <td>280</td>
      <td>SHADOW_CRYSTAL_USE_CH1 - Shadow Crystal usage -</td>
      <td>map</td>
      <td>Your Shadow Crystal usage in Chapter 1. Unique dialogue if less than 2. <br>0 = Default state<br>1 = Saw toys<br>2 = Not useful<br></td>
    </tr>
    <tr>
      <td>281</td>
      <td>GLASS_USE_ALONE_CH1 - Glass usage without Susie -</td>
      <td>map</td>
      <td>Your Glass usage without Susie around/in Chapter 1. <br>0 = Default state<br>1 = Saw through hand<br>2 = Not useful (Ch1)<br></td>
    </tr>
    <tr>
      <td>290</td>
      <td>SOLVED_DICE_BRACE_PUZZLE - Solved the Dice Brace puzzle -</td>
      <td>bool</td>
      <td>Whether you solved the suits puzzle to obtain Dice Brace. <br></td>
    </tr>
    <tr>
      <td>291</td>
      <td>FOREST_MAZE_PROGRESS - Forest maze progress -</td>
      <td>volatile <br> number</td>
      <td>Volatile. Counts the number of correct rooms you've gone through in the maze. Find Susie at 4, done at 9. <br></td>
    </tr>
    <tr>
      <td>292</td>
      <td>FOREST_MAZE_FAILURE_COUNT - Forest maze wrong turns -</td>
      <td>volatile <br> number</td>
      <td>Volatile. Counts how much you've taken the wrong choice in the forest maze. Jumps straight to 3 (dead end) if you got lost before or found Susie. <br></td>
    </tr>
    <tr>
      <td>293</td>
      <td>LANCER_DEAD_END_COUNT - Lancer dead ends -</td>
      <td>number</td>
      <td>The number of times you found the Lancer dead end. <br></td>
    </tr>
    <tr>
      <td>294</td>
      <td>SUSIE_DEAD_END_COUNT - Susie dead ends -</td>
      <td>number</td>
      <td>The number of times you found the Susie dead end. <br></td>
    </tr>
    <tr>
      <td>295</td>
      <td>TALKED_TO_TOPCHEF_AFTER_RETURNING_TOP_CAKE - Talked to Topchef after returning the Top Cake -</td>
      <td>bool</td>
      <td>Whether you talked to Topchef in the pacifist end after returning the Topcake. He thinks Susie is Clover's mom. <br></td>
    </tr>
    <tr>
      <td>296</td>
      <td>VISITED_JAIL - Visited jail -</td>
      <td>bool</td>
      <td>Whether you visited the jail. No effects in the Chapter 1&2 demo. <br></td>
    </tr>
    <tr>
      <td>300</td>
      <td>HUGGED_DUMMY_CH2 - Hugged -</td>
      <td>bool</td>
      <td>Whether you hugged the dummy in Chapter 2. Some slight dialogue changes. <br></td>
    </tr>
    <tr>
      <td>301</td>
      <td>KING_JAIL_DIALOGUE_PROGRESS - King dialogue -</td>
      <td>map</td>
      <td>Whether you talked to King in jail before visiting Cyber World. <br>0 = Default state<br>1 = Talked<br>2 = Left<br></td>
    </tr>
    <tr>
      <td>302</td>
      <td>TOY_DELIVER_PROGRESS - Toy delivery -</td>
      <td>map</td>
      <td>Your progress in delivering Ralsei's first batch of subjects. <br>0 = Default state<br>1 = Ball on head<br>2 = Toys delivered<br></td>
    </tr>
    <tr>
      <td>303</td>
      <td>BEEN_CALLED_NORMAL - Saw Alphys and Toriel talk -</td>
      <td>bool</td>
      <td>Whether you saw Alphys and Toriel talking about you. Alters Toriel's dialogue if called. <br></td>
    </tr>
    <tr>
      <td>304</td>
      <td>SUSIE_ATE_CAKE - Susie ate the cake -</td>
      <td>bool</td>
      <td>Whether Susie ate Ralsei's entire cake (yet). <br></td>
    </tr>
    <tr>
      <td>305</td>
      <td>TOLD_MOM_STUDYING - Told Toriel about studying -</td>
      <td>bool</td>
      <td>Whether you told Toriel you were going to be studying with Susie over the phone, with or without mentioning the trash orb. <br></td>
    </tr>
    <tr>
      <td>306</td>
      <td>TOLD_MOM_ORB - Called Toriel with the trash orb -</td>
      <td>bool</td>
      <td>Whether you called Toriel while just around the corner with a trash orb on your head. Also sets flag 305. <br></td>
    </tr>
    <tr>
      <td>307</td>
      <td>PLUSH_RECIPIENT - Plush recipient -</td>
      <td>map</td>
      <td>Records who you gave the plush to. In pre-1.08 versions, there's a bug resetting it to 1 before the acid river ride <br>0 = Default state<br>1 = Ralsei<br>2 = Susie<br>3 = Noelle<br>4 = Berdly<br></td>
    </tr>
    <tr>
      <td>308</td>
      <td>SAW_EGGS_HUSBAND - Saw the Asgore egg scene -</td>
      <td>bool</td>
      <td>Whether you've seen Asgore make a fool of himself in public. <br></td>
    </tr>
    <tr>
      <td>309</td>
      <td>SPAMTON_QUEST_PROGRESS - Quest progress -</td>
      <td>map</td>
      <td>Your progress in learning about the power of NEO. <br>0 = Default state<br>1 = Spared Spamton<br>3 = Purchased KeyGen<br>4 = Used KeyGen<br>5 = Entered basement<br>7 = Disk Loaded<br>8 = Disk inserted<br>9 = Defeated Spamton NEO<br></td>
    </tr>
    <tr>
      <td>310</td>
      <td>FIRST_CHEESE_DESTROYED - First cheese destroyed -</td>
      <td>bool</td>
      <td>Whether the first cheese on the left was destroyed. <br></td>
    </tr>
    <tr>
      <td>311</td>
      <td>DESTROYED_CHEESE_ALONE - Triggered first cheese alone -</td>
      <td>bool</td>
      <td>Whether you triggered the first cheese without Noelle, prompting slightly different text when interacting with it. <br></td>
    </tr>
    <tr>
      <td>312</td>
      <td>TALKED_TO_SEAM_CH2 - Talked to Seam -</td>
      <td>bool</td>
      <td>Set when you talk to Seam in Chapter 2, preventing them from repeating themselves. <br></td>
    </tr>
    <tr>
      <td>313</td>
      <td>OBTAINED_SPINCAKE_CH2 - Got SpinCake (fresh) -</td>
      <td>bool</td>
      <td>Whether you received a fresh Spincake since Chapter 2. <br></td>
    </tr>
    <tr>
      <td>314</td>
      <td>MR_SOCIETY_LEFT - Mr. Society -</td>
      <td>bool</td>
      <td>Whether Mr. Society, the bishop, flew up the cliff after being talked to. <br></td>
    </tr>
    <tr>
      <td>315</td>
      <td>SAW_SHELTER_SCENE - Saw the shelter scene -</td>
      <td>bool</td>
      <td>Whether Monster Kid and Snowy fled Susie at the bunker. They go home. <br></td>
    </tr>
    <tr>
      <td>316</td>
      <td>SAW_HOSPITAL_SCENE - Saw hospital scene -</td>
      <td>bool</td>
      <td>Whether Noelle went home in Chapter 2 yet (yes, either route). <br></td>
    </tr>
    <tr>
      <td>317</td>
      <td>POLICE_SCENE_PROGRESS - Dogs -</td>
      <td>map</td>
      <td>Tracks the state of the police station dog scene. <br>0 = Default state<br>1 = Dogs escaped<br>2 = Alarm playing<br></td>
    </tr>
    <tr>
      <td>319</td>
      <td>FERRIS_WHEEL_SCENE_PROGRESS - Ferris wheel scene state -</td>
      <td>map</td>
      <td>Tracks progress through the Ferris wheel scene. <br>0 = Default state<br>1 = On Ferris wheel<br>2 = Off Ferris wheel<br>3 = WHAT? WHAT? WHAT?<br></td>
    </tr>
    <tr>
      <td>320</td>
      <td>SAW_KING_QUEEN_REUNION - Saw King and Queen reunite -</td>
      <td>bool</td>
      <td>Whether you've seen the touching reunion of King and Queen. <br></td>
    </tr>
    <tr>
      <td>324</td>
      <td>SPAMTON_STRESS_RESPONSE - Post-NEO stress response -</td>
      <td>map</td>
      <td>What you said- made Kris say- after fighting Spamton NEO. <br>0 = Default state<br>1 = OK<br>2 = Not OK<br></td>
    </tr>
    <tr>
      <td>325</td>
      <td>RALSEI_PHOTO_STATE - Photo -</td>
      <td>map</td>
      <td>The purty picture you took with Ralsei. Affects his title and whether he hugs Kris after Spamton NEO. <br>0 = Default state<br>1 = Hugged<br>2 = Peace sign<br>3 = Rude gesture<br>4 = No pose<br></td>
    </tr>
    <tr>
      <td>326</td>
      <td>ROUXLS_PIRATE_HAT - Rouxls wearing pirate hat -</td>
      <td>bool</td>
      <td>Whether Rouxls Kaard is currently wearing a pirate hat. <br></td>
    </tr>
    <tr>
      <td>327</td>
      <td>SEATED_HEAD_HATHY_WITH_WEREWEREWIRE - Seated Head Hathy with Werewerewire -</td>
      <td>bool</td>
      <td>Whether you interacted with a Head Hathy or Werewerewire together at the cafe. Alters Werewerewire narration if subsequently moved away from Head Hathy. <br></td>
    </tr>
    <tr>
      <td>329</td>
      <td>TALKED_TO_SPAMTON_ABOUT_KNIGHT - Talked to Spamton about the Knight -</td>
      <td>bool</td>
      <td>Whether you talked with Spamton about the Knight, changing his talk option to Friends. <br></td>
    </tr>
    <tr>
      <td>330</td>
      <td>FOUND_TASQUE_SWITCH - Found the Tasque-maze switch -</td>
      <td>bool</td>
      <td>Whether you found the switch that controls the faint hint in the Tasque maze. <br></td>
    </tr>
    <tr>
      <td>331</td>
      <td>SAW_FERRIS_SCENE - Saw the Ferris wheel scene -</td>
      <td>bool</td>
      <td>Set to 1 after the Ferris wheel scene, even if skipped. <br></td>
    </tr>
    <tr>
      <td>332</td>
      <td>FOUND_MAZE_SWITCH - Found the old maze switch -</td>
      <td>bool</td>
      <td>Whether you found the old variant of the Tasque-maze switch. <br></td>
    </tr>
    <tr>
      <td>333</td>
      <td>SOLVED_AGREE2ALL_PUZZLE - Solved AGREE2ALL puzzle -</td>
      <td>bool</td>
      <td>Whether you solved the AGREE2ALL puzzle. <br></td>
    </tr>
    <tr>
      <td>335</td>
      <td>SHOVEL_DOOR_OPEN - Opened the shovel door -</td>
      <td>bool</td>
      <td>Whether you opened the door to the room filled with 999 shovels. <br></td>
    </tr>
    <tr>
      <td>336</td>
      <td>SUSIE_AVOID_ALPHYS - Susie avoiding Alphys -</td>
      <td>bool</td>
      <td>Whether Susie is waiting due east of you rather than come close to Alphys. <br></td>
    </tr>
    <tr>
      <td>337</td>
      <td>ALVIN_DIALOGUE_PROGRESS - Alvin -</td>
      <td>map</td>
      <td>Tracks how much you talk to Alvin about his father and the hammer, and whether he mumbles to himself as you leave. <br>0 = Default state<br>1 = Talked once<br>2 = Talked twice<br>3 = Heard mumbling<br></td>
    </tr>
    <tr>
      <td>339</td>
      <td>FOUND_BASEMENT_SWITCH - Found the basement switch -</td>
      <td>bool</td>
      <td>Whether you activated the secret backdoor to the mansion's basement. Alter's Hacker's dialogue. <br></td>
    </tr>
    <tr>
      <td>340</td>
      <td>FOUND_SHORTCUT_OUT - Found the basement shortcut -</td>
      <td>bool</td>
      <td>Whether you flipped the less-secret switch to connect the basement to the foyer. Also set on entry into the foyer on Snowgrave. <br></td>
    </tr>
    <tr>
      <td>341</td>
      <td>SUSIE_AVOID_CATTI - Susie avoiding diner -</td>
      <td>bool</td>
      <td>Whether Susie has told you she isn't going into the diner (Catti's working there!) <br></td>
    </tr>
    <tr>
      <td>342</td>
      <td>CHOCOLATE_RECIPIENT - Chocolate recipient -</td>
      <td>map</td>
      <td>Who did you give the Box of Heart-Shaped Chocolates to? <br>0 = Default value<br>1 = Ate alone<br>2 = Shared with Susie<br>3 = Gave to Alphys<br>4 = Returned to Sans<br></td>
    </tr>
    <tr>
      <td>343</td>
      <td>MADE_HIGH_FIVE - Made the giant high-five -</td>
      <td>bool</td>
      <td>Whether you pulled the lever to make a giant high-five and progress the swan ride. <br></td>
    </tr>
    <tr>
      <td>344</td>
      <td>SOLVED_FIRST_SAUCER_PUZZLE - Solved first saucer puzzle -</td>
      <td>bool</td>
      <td>Looks to be set to 1 when completing the first shell game-style saucer puzzle. <br></td>
    </tr>
    <tr>
      <td>345</td>
      <td>SAW_TOILET_STATUE - Checked the Berdly toilet statue -</td>
      <td>bool</td>
      <td>Whether you interacted with the Berdly statue in the toilet. Spawns the NPC outside waiting for the statue to finish in there. <br></td>
    </tr>
    <tr>
      <td>346</td>
      <td>SOLVED_SAUCER_SHORTCUT - Solved the saucer shortcut -</td>
      <td>bool</td>
      <td>Whether you've unlocked a shortcut in Mansion by doing a saucer puzzle. I don't know which. <br></td>
    </tr>
    <tr>
      <td>347</td>
      <td>SEEN_STATUE_COUNT - Toilet statue interactions -</td>
      <td>number</td>
      <td>The number of times you interacted with the Berdly statue with Noelle with you. She has unique comments up to 8 on how obsessed you are with it. <br></td>
    </tr>
    <tr>
      <td>349</td>
      <td>FROZEN_CHICKEN - Froze the chicken -</td>
      <td>bool</td>
      <td>Whether there is a large ice crystal you cannot see into blocking the way. <br></td>
    </tr>
    <tr>
      <td>350</td>
      <td>FEDORA_PLUGBOY_WEREWIRED - Werewired Fedora Plugboy -</td>
      <td>bool</td>
      <td>Whether you walked far enough away for the fedora'd Plugboy to get Werewired offscreen. <br></td>
    </tr>
    <tr>
      <td>351</td>
      <td>UNUSED_CYBER_MAZE_HINT - Queen screen maze hint -</td>
      <td>bool</td>
      <td>Unused flag for a hint popup in room_dw_cyber_maze_queenscreen. <br></td>
    </tr>
    <tr>
      <td>352</td>
      <td>SOLVED_VIROVIROKUN_DODGE - Solved Viro Dodge -</td>
      <td>bool</td>
      <td>Whether you got the key in room_dw_cyber_viro_ring. <br></td>
    </tr>
    <tr>
      <td>353</td>
      <td>SEAM_TWO_CRYSTALS_DIALOGUE_PROGRESS - Talk Two Crystals -</td>
      <td>map</td>
      <td>How much you've talked to Seam since obtaining both Shadow Crystals. <br>0 = Default state<br>1 = Gave both<br>2 = Talked about mantle<br></td>
    </tr>
    <tr>
      <td>354</td>
      <td>CD_BAGELS_PURCHASED - CD Bagels -</td>
      <td>number</td>
      <td>The number of CD Bagels you purchased from K_K. He stops selling them at six, in case somebody orders 400. <br></td>
    </tr>
    <tr>
      <td>356</td>
      <td>LANCER_CARED_FOR - Cared for Lancer -</td>
      <td>bool</td>
      <td>Whether statue-Lancer has been pushed to the table and given his adorable bib. <br></td>
    </tr>
    <tr>
      <td>357</td>
      <td>RECRUITED_HACKER - Recruited -</td>
      <td>bool</td>
      <td>Whether you talked to Hacker after collecting all three Blue Checksmarks. <br></td>
    </tr>
    <tr>
      <td>358</td>
      <td>ENTERED_BASEMENT_COUNT - Basement entries -</td>
      <td>number</td>
      <td>Tracks how many times you entered the basement alone. Does not go past 1 until you've seen Susie stealing Ralsei's glasses, after which it gets set to 2. <br></td>
    </tr>
    <tr>
      <td>359</td>
      <td>MET_HACKER - Met Hacker -</td>
      <td>map</td>
      <td>Whether you talked to Hacker. Note that the 2 state isn't directly used; see flag 357. <br>0 = Default state<br>1 = Talked<br>2 = Recruited<br></td>
    </tr>
    <tr>
      <td>360</td>
      <td>APPROACHED_CHEESE_MAZE - Approached Cheese Maze -</td>
      <td>bool</td>
      <td>Whether you've approached the cheese maze, destroying the lone cheese or triggering Noelle dialogue if it's already destroyed. <br></td>
    </tr>
    <tr>
      <td>361</td>
      <td>DID_RIGHT_CHEESE_FIGHT - Did Right Cheese Fight -</td>
      <td>bool</td>
      <td>Unused right-cheese encounter flag. <br></td>
    </tr>
    <tr>
      <td>362</td>
      <td>MAUSWHEEL_DEFEATED - Defeated Mauswheel -</td>
      <td>bool</td>
      <td>Whether you defeated Mauswheel on the normal route, freeing the Swatchlings. <br></td>
    </tr>
    <tr>
      <td>366</td>
      <td>TASQUE_RELEASED - Released Tasque -</td>
      <td>bool</td>
      <td>Makes one particular Tasque persist after leaving the wall screen in Field. <br></td>
    </tr>
    <tr>
      <td>367</td>
      <td>OBTAINED_CHESTMARK - Got Chestmark 1 -</td>
      <td>bool</td>
      <td>Whether you got the Blue Checksmark from a treasure chest. <br></td>
    </tr>
    <tr>
      <td>368</td>
      <td>SOLVED_MICE_2 - Solved Mice 2 -</td>
      <td>map</td>
      <td>Progress on solving the second mice puzzle. <br>0 = Default state<br>1 = Forcefield down<br>0.5 = Mice in hole<br></td>
    </tr>
    <tr>
      <td>369</td>
      <td>NOELLE_SAW_RALSEI_AND_SUSIE - Had Noelle see Ralsei and Susie -</td>
      <td>bool</td>
      <td>Whether Noelle gave her one-time dialogue about seeing Ralsei and Susie having fun. <br></td>
    </tr>
    <tr>
      <td>370</td>
      <td>SOLVED_MANSION_TRAFFIC - Solved Mansion Traffic -</td>
      <td>bool</td>
      <td>Whether the traffic challenge at the end of floor 1F was completed, opening the room with the backdoor switch. <br></td>
    </tr>
    <tr>
      <td>371</td>
      <td>FOUGHT_TASQUE_MANAGER - Fought Tasque Manager -</td>
      <td>bool</td>
      <td>Whether you fought Tasque Manager. <br></td>
    </tr>
    <tr>
      <td>373</td>
      <td>UNLOCKED_EAST_BASEMENT - Unlocked East Basement -</td>
      <td>bool</td>
      <td>Whether you disabled the forcefield in the basement with the final boss. Yeah, the teacups. <br></td>
    </tr>
    <tr>
      <td>374</td>
      <td>MICE_RECEIVED_20_DOLLARS - Gave the mice $20 -</td>
      <td>bool</td>
      <td>Whether the mice got $20. Alters Mousemillian's dialogue. <br></td>
    </tr>
    <tr>
      <td>375</td>
      <td>MICE_RECEIVED_1_DOLLAR - Gave the mice $1 -</td>
      <td>bool</td>
      <td>Whether the mice got $1. Alters Mousemillian's dialogue. <br></td>
    </tr>
    <tr>
      <td>376</td>
      <td>SWATCHLING_VASE_ROOM_PROGRESS - Vase room -</td>
      <td>map</td>
      <td>Progress in the room with the Swatchling and the bridges and the unavoidable vase. <br>0 = Default state<br>1 = Swatchling freed<br>2 = Vase spawned<br></td>
    </tr>
    <tr>
      <td>377</td>
      <td>MOUSE_LOTTERY_RESULT_1 - Mouselottery Solved -</td>
      <td>bool</td>
      <td>Whether the mice have triggered the blue house. <br></td>
    </tr>
    <tr>
      <td>378</td>
      <td>MOUSE_LOTTERY_RESULT_2 - Mouselottery Solved 2 -</td>
      <td>bool</td>
      <td>Whether the mice have triggered the red house. <br></td>
    </tr>
    <tr>
      <td>379</td>
      <td>NOELLE_BEAT_FEAR - Helped Noelle overcome her fear -</td>
      <td>bool</td>
      <td>Whether Noelle stopped being afraid of mice. <br></td>
    </tr>
    <tr>
      <td>380</td>
      <td>CALLED_MOM_AFTER_LAB - Called Mom After Lab -</td>
      <td>bool</td>
      <td>Whether you called Toriel after leaving the computer lab. Prevents her from repeating her dialogue. <br></td>
    </tr>
    <tr>
      <td>381</td>
      <td>DOG_OPENED_DOOR - Had the dog open the door -</td>
      <td>bool</td>
      <td>Whether the dog, ah, forced open the double door in the bajillion platters room in the mansion. <br></td>
    </tr>
    <tr>
      <td>382</td>
      <td>DINING_HALL_COMPLETE - Completed the dining hall -</td>
      <td>bool</td>
      <td>Whether you finished the ultimate dining hall puzzle. <br></td>
    </tr>
    <tr>
      <td>383</td>
      <td>SOLVED_FORCEFIELD_1 - Solved Forcefield 1 -</td>
      <td>bool</td>
      <td>Whether you successfully activated both switches in the first forcefield puzzle, disabling it forever. <br></td>
    </tr>
    <tr>
      <td>384</td>
      <td>FOUGHT_CHEESE_MAZE - Fought Cheese Maze -</td>
      <td>bool</td>
      <td>Whether you touched the cheese maze, triggering an encounter and destroying it. <br></td>
    </tr>
    <tr>
      <td>385</td>
      <td>VASE_BALANCING_OUTCOME - Balance Pot Status -</td>
      <td>map</td>
      <td>What happened in the vase-balancing minigame. <br>0 = Default state<br>1 = Dropped pot<br>2 = Success<br></td>
    </tr>
    <tr>
      <td>386</td>
      <td>VISITED_SPAMTON - Visited Spamton -</td>
      <td>map</td>
      <td>Prevents you from getting repeat dialogue every single time you visit Spamton's shop. <br>0 = Default state<br>1 = First time in shop<br>2 = Exited<br></td>
    </tr>
    <tr>
      <td>387</td>
      <td>RETURNED_CASTLE_TOWN - Saw Queen introduce herself to Castle Town -</td>
      <td>bool</td>
      <td>Whether you've seen Queen introduce herself to Castle Town. <br></td>
    </tr>
    <tr>
      <td>388</td>
      <td>OBTAINED_NO_RECRUITS - Sealed the Fountain with no recruits -</td>
      <td>bool</td>
      <td>Whether you sealed the Fountain with no recruits at all, on the normal route anyway. <br></td>
    </tr>
    <tr>
      <td>389</td>
      <td>FOUGHT_BRIDGE_WEREWIRE - Fought Bridge Werewire -</td>
      <td>bool</td>
      <td>Whether you fought the Werewire in the acid lake bridge room, unlocking the Revive Dust chest. <br></td>
    </tr>
    <tr>
      <td>390</td>
      <td>SOLVED_APPLE_PUZZLE - Solved Apple Puzzle -</td>
      <td>bool</td>
      <td>Whether you unlocked the way to NUBERT'S TREASURE. <br></td>
    </tr>
    <tr>
      <td>391</td>
      <td>ENCOUNTERED_FIRST_VIROVIROKUN - Fought First Viro -</td>
      <td>bool</td>
      <td>Tracks whether you've encountered the first Virovirokun. When set, it will fly around in a circle instead of staying still. <br></td>
    </tr>
    <tr>
      <td>392</td>
      <td>MANSION_THIRD_FLOOR_SHORTCUT_UNLOCKED - 3F bookcase shortcut (Snowgrave) -</td>
      <td>bool</td>
      <td>Unlocks a mansion shortcut early on the Snowgrave Route. <br></td>
    </tr>
    <tr>
      <td>393</td>
      <td>STOLE_SUSIE_STATUE - Stole Susie statue -</td>
      <td>bool</td>
      <td>Whether you stole the Susie statue from Noelle's room. <br></td>
    </tr>
    <tr>
      <td>394</td>
      <td>STOLE_ICE_E_STATUE - Stole Ice-E statue -</td>
      <td>bool</td>
      <td>Whether you stole the Ice-E statue from Noelle's room. <br></td>
    </tr>
    <tr>
      <td>395</td>
      <td>OPENED_SIDE_A_PAINTING - Opened Side A painting -</td>
      <td>bool</td>
      <td>Whether a painting opened a passageway. <br></td>
    </tr>
    <tr>
      <td>396</td>
      <td>OPENED_SIDE_PAINTING_B - Opened Side B painting -</td>
      <td>bool</td>
      <td>Whether a painting opened a passageway. <br></td>
    </tr>
    <tr>
      <td>397</td>
      <td>ACTIVATED_QUEEN_PAINTINGS - Activated Queen's paintings -</td>
      <td>bool</td>
      <td>Whether Queen warned you not to take your eyes off her paintings, and activated the painting fireballs. <br></td>
    </tr>
    <tr>
      <td>398</td>
      <td>ACTIVATED_MINT_PAINTING - Activated mint painting -</td>
      <td>bool</td>
      <td>Whether you activated the Revive Mint painting with a different painting. <br></td>
    </tr>
    <tr>
      <td>399</td>
      <td>ACTIVATED_PAINTING_EXIT - Activated the painting exit -</td>
      <td>bool</td>
      <td>Whether you disabled a fire painting blocking the exit by interacting with a different painting. <br></td>
    </tr>
    <tr>
      <td>400</td>
      <td>MANSION_VASE_TUTORIAL_PROGRESS - Vase Intro Status -</td>
      <td>map</td>
      <td>Your progress in learning the basics of Queen's Mansion. <br>0 = Default state<br>1 = Learned rules<br>2 = Broke vase<br></td>
    </tr>
    <tr>
      <td>407</td>
      <td>OBTAINED_CHESTMARK_2 - Got Chestmark 2 -</td>
      <td>bool</td>
      <td>Whether you got the second Chest-Checksmark. <br></td>
    </tr>
    <tr>
      <td>408</td>
      <td>SAW_SWEET_CAPN_CAKES_FLYBY - Saw Sweet Cap'n Cakes fly by -</td>
      <td>bool</td>
      <td>Whether you saw Sweet Cap'n Cakes fly by after fighting them. <br></td>
    </tr>
    <tr>
      <td>409</td>
      <td>INSPECTED_KRIS_BED - Inspected Kris's bed -</td>
      <td>bool</td>
      <td>Whether you inspected your own bed. Necessary to retain your Bed Inspector title. <br></td>
    </tr>
    <tr>
      <td>410</td>
      <td>INSPECTED_SUSIE_BED - Inspected Susie's bed -</td>
      <td>bool</td>
      <td>Whether you inspected Susie's bed. Necessary to retain your Bed Inspector title. <br></td>
    </tr>
    <tr>
      <td>411</td>
      <td>INSPECTED_LANCER_BED - Inspected Lancer's bed -</td>
      <td>bool</td>
      <td>Whether you inspected Lancer's bed. Necessary to retain your Bed Inspector title. <br></td>
    </tr>
    <tr>
      <td>412</td>
      <td>INSPECTED_CLOVER_BED - Inspected Clover's bed -</td>
      <td>bool</td>
      <td>Whether you inspected Clover's bed. Necessary to retain your Bed Inspector title. Only obtainable on v1.09+ due to a bug. <br></td>
    </tr>
    <tr>
      <td>413</td>
      <td>INSPECTED_NOELLE_BED - Inspected Noelle's bed -</td>
      <td>bool</td>
      <td>Whether you inspected Noelle's bed. Necessary to retain your Bed Inspector title. <br></td>
    </tr>
    <tr>
      <td>414</td>
      <td>BED_INSPECTOR_CH2 - Earned Bed Inspector -</td>
      <td>bool</td>
      <td>Whether you retained your Bed Inspector title. That is, got slightly different Noelle bed dialogue. Only obtainable on v1.09+ due to a bug. <br></td>
    </tr>
    <tr>
      <td>415</td>
      <td>MICE_ATTACK_REASON - Mice Attack Reason -</td>
      <td>map</td>
      <td>What you told Noelle about the mice attacking her. The question was, "What do I look like, the girl from the Nutcracker?" <br>0 = Default state<br>1 = They like you<br>2 = Unknown<br>3 = You look like her<br></td>
    </tr>
    <tr>
      <td>416</td>
      <td>TRIGGERED_CYBER_FIELD_TEMP_SAVE - Triggered Field Tempsave -</td>
      <td>bool</td>
      <td>Whether you returned to the Cyber Field hub after defeating Sweet Cap'n Cakes and triggered a tempsave. <br></td>
    </tr>
    <tr>
      <td>417</td>
      <td>TRIGGERED_TRASH_ZONE_TEMP_SAVE - Triggered Trash Tempsave -</td>
      <td>bool</td>
      <td>Whether you reached Cyber City by falling into the dump and triggered a tempsave. <br></td>
    </tr>
    <tr>
      <td>418</td>
      <td>OBTAINED_SHOE - Got Shoe -</td>
      <td>bool</td>
      <td>Whether you got a free sample from Cyber Shoes. Alters Lancer's dialogue and prevents a Mansion tempsave from happening (reused flag). <br></td>
    </tr>
    <tr>
      <td>419</td>
      <td>TASQUE_MANAGER_RESPONSE - Tasque Manager Response -</td>
      <td>map</td>
      <td>Whether you got all or most of Tasque Manager's questions correct. She starts with 100% if all, 50% if you miss the last due to her phrasing. <br>0 = Default state<br>1 = All correct<br>2 = Thought alphabetical<br></td>
    </tr>
    <tr>
      <td>420</td>
      <td>SOLVED_GIASFCLFEBREBREBEHR_PUZZLE - Solved the typing puzzle -</td>
      <td>bool</td>
      <td>Whether you solved the Giasfclfebrebrebrebehr typing puzzle, earning the third Blue Checksmark. <br></td>
    </tr>
    <tr>
      <td>421</td>
      <td>NOELLE_RELATIONSHIP_RESPONSE - Noelle Friend -</td>
      <td>map</td>
      <td>Whether you told Noelle you were "something else." Necessary for Snowgrave. <br>0 = Friends<br>1 = Something else<br></td>
    </tr>
    <tr>
      <td>422</td>
      <td>TALKED_TO_METTATON_CH2 - Talked to Mettaton -</td>
      <td>bool</td>
      <td>Whether you talked to Mettaton in Chapter 2. They don't repeat themselves. <br></td>
    </tr>
    <tr>
      <td>423</td>
      <td>STOLEN_BAGELS - Stolen Bagels -</td>
      <td>number</td>
      <td>How many CD Bagels you stole on the Snowgrave Route (0-4). <br></td>
    </tr>
    <tr>
      <td>424</td>
      <td>TALKED_TO_ONION_CH2 - Talked to Onion -</td>
      <td>bool</td>
      <td>Whether you talked to Onionsan in Chapter 2. <br></td>
    </tr>
    <tr>
      <td>425</td>
      <td>ONION_WAS_MISSED - Missed -</td>
      <td>map</td>
      <td>What you told Onion. <br>0 = Default state<br>1 = Missed<br>2 = Did not miss<br></td>
    </tr>
    <tr>
      <td>426</td>
      <td>SWATCHLING_COMBO - Swatchling fight combo -</td>
      <td>map</td>
      <td>Volatile. The current combination of Swatchlings you are fighting. Later ones are harder, generally. <br>0 = ROB<br>1 = BGY<br>2 = ROY<br>3 = BYR<br>4 = RBY<br>5 = BYG<br>6 = RYB<br>7 = BRY<br>8 = YGO<br>-1 = RRB<br></td>
    </tr>
    <tr>
      <td>427</td>
      <td>UNLOCKED_MINT_CHEST - Unlocked the mint chest -</td>
      <td>bool</td>
      <td>Whether Virovirokun triggered the hidden path to the Revive Mint chest. <br></td>
    </tr>
    <tr>
      <td>428</td>
      <td>SAW_SWEET - Saw Sweet -</td>
      <td>bool</td>
      <td>Whether you saw Sweet right after the first teacup ride. Prevents him from appearing multiple times. <br></td>
    </tr>
    <tr>
      <td>429</td>
      <td>STATUE_SINK_PROGRESS - Statue sink -</td>
      <td>number</td>
      <td>The amount by which the statue of Queen has sunk into the acid, in frames, so it persists even if you leave. <br></td>
    </tr>
    <tr>
      <td>430</td>
      <td>TOOK_AZZY_MONEY - Took Asriel's $5 -</td>
      <td>bool</td>
      <td>Whether you took five bucks from Asriel's drawer. <br></td>
    </tr>
    <tr>
      <td>431</td>
      <td>TALKED_TO_JIGSAW_JOE_CH2 - Talked to Jigsaw Joe -</td>
      <td>bool</td>
      <td>Whether you talked to Jigsaw Joe yet in the Party Dojo, which he introduces. <br></td>
    </tr>
    <tr>
      <td>432</td>
      <td>TOLD_TO_EXPLORE - Told To Explore -</td>
      <td>bool</td>
      <td>Whether Ralsei told you and Susie to explore the Castle Town yet. <br></td>
    </tr>
    <tr>
      <td>433</td>
      <td>TOLD_TO_RUN_CH2 - Told to run -</td>
      <td>bool</td>
      <td>Whether Susie reminded you that you can run in this game (if you fail to do so in the chapter). <br></td>
    </tr>
    <tr>
      <td>434</td>
      <td>HEARD_SPAMTON_DEAL_EXPLANATION - Heard Spamton explain the deal -</td>
      <td>bool</td>
      <td>Whether Spamton told you about our deal and the machine in the basement. Prevents him from skipping it if you buy KeyGen first. <br></td>
    </tr>
    <tr>
      <td>435</td>
      <td>HOUSE_GAME_WINNER - House Game Winner -</td>
      <td>map</td>
      <td>Who won Rouxls's house minigame. <br>0 = Default state<br>1 = Rouxls<br>2 = Kris<br>3 = Draw<br></td>
    </tr>
    <tr>
      <td>436</td>
      <td>CALLED_MOM_BUSY - Called home during the ending -</td>
      <td>bool</td>
      <td>Whether you called home during the Chapter 2 end sequence. Unique dialogue the first time, then everyone's too busy to pick it up. <br></td>
    </tr>
    <tr>
      <td>437</td>
      <td>FESTIVAL_COMPANION_RESPONSE - Fave Party Member 2 -</td>
      <td>map</td>
      <td>Who you told Susie you would take to the festival in the Chapter 2 end cutscene. Unaccessed. <br>0 = Default state<br>1 = Noelle<br>2 = Ralsei<br>3 = Susie<br>4 = ...<br></td>
    </tr>
    <tr>
      <td>438</td>
      <td>TUTORIAL_VIROVIROKUN_LOCATION - Tutor Viro Location -</td>
      <td>map</td>
      <td>Where you fought the tutorial Virovirokun. Persists its ice statue in Snowgrave. <br>0 = Default state<br>1 = Progressed<br>2 = Backtracked<br></td>
    </tr>
    <tr>
      <td>439</td>
      <td>DEPOSITED_EGG_CH2 - Deposited the egg -</td>
      <td>bool</td>
      <td>Whether you put the egg in the egg basket in Sans's store. <br></td>
    </tr>
    <tr>
      <td>440</td>
      <td>INTERACTED_WITH_FERRIS_POSTER - Checked the Ferris wheel poster -</td>
      <td>bool</td>
      <td>Whether you interacted with the Ferris wheel poster with Noelle. One-time event. <br></td>
    </tr>
    <tr>
      <td>441</td>
      <td>TALKED_TO_DATING_SHOES_ADDISON - Talked to the Dating Shoes Addison -</td>
      <td>bool</td>
      <td>Whether you talked to the Addison selling Dating Shoes. One-time event. See also flag 421. <br></td>
    </tr>
    <tr>
      <td>442</td>
      <td>LEARNED_TEACUPS - Learned the teacup controls -</td>
      <td>bool</td>
      <td>Whether you've taken your first teacup ride and possibly gotten a tutorial on operating it. <br></td>
    </tr>
    <tr>
      <td>443</td>
      <td>TOLD_SAVE_TOWN - Heard Ralsei explain saving -</td>
      <td>bool</td>
      <td>Whether Ralsei told you to feel free to SAVE and take a break in Castle Town. <br></td>
    </tr>
    <tr>
      <td>444</td>
      <td>TOLD_VISIT_TOWN - Heard Susie suggest Castle Town -</td>
      <td>bool</td>
      <td>Whether Susie told you to go back and check out Castle Town, if you went down south first. <br></td>
    </tr>
    <tr>
      <td>445</td>
      <td>READ_CLEANING_POSTER - Read the cleaning poster -</td>
      <td>bool</td>
      <td>Whether you interacted with the poster for Queen Cleaning Agent with Noelle behind you. Interesting dialogue exclusive to non-Snowgrave. <br></td>
    </tr>
    <tr>
      <td>446</td>
      <td>WENT_WEIRD_DOOR - Went Weird Door -</td>
      <td>bool</td>
      <td>Whether you brought Noelle all the way back to the gray door. Unique dialogue about its creepiness, but not required for Snowgrave. <br></td>
    </tr>
    <tr>
      <td>447</td>
      <td>BROKE_BALLOON_CHEESE - Broke Balloon Cheese -</td>
      <td>bool</td>
      <td>Whether the balloon cheese, found right before the mice basket puzzle, was dropped. <br></td>
    </tr>
    <tr>
      <td>448</td>
      <td>FINISHED_BIG_FORCEFIELD - Finished Big Forcefield -</td>
      <td>bool</td>
      <td>Whether you finished and disabled the right-side forcefields in that room where Noelle stands on a button forever. <br></td>
    </tr>
    <tr>
      <td>449</td>
      <td>EASTER_EGG_FORCEFIELD - Triggered the forcefield easter egg -</td>
      <td>bool</td>
      <td>Whether you disabled the Easter egg forcefield (with the balloons) by all getting in one teacup. <br></td>
    </tr>
    <tr>
      <td>450</td>
      <td>BALLOON_TEACUP_EASTER_EGG_PROGRESS - Teacup easter egg -</td>
      <td>map</td>
      <td>Progress in the balloon-teacup Easter egg. <br>0 = Default state<br>1 = Read sign<br>2 = Rode teacups<br></td>
    </tr>
    <tr>
      <td>451</td>
      <td>TALKED_TO_SANS_ABOUT_PAPYRUS - Talked to Sans about Papyrus -</td>
      <td>bool</td>
      <td>Whether you talked to Sans about Papyrus in both chapters 1 and 2; talking in Chapter 2 only isn't saved. <br></td>
    </tr>
    <tr>
      <td>452</td>
      <td>TOLD_WRONGWAY - Told Wrongway -</td>
      <td>bool</td>
      <td>Whether Noelle questioned if you were going the right way while backtracking further into the trash zone. <br></td>
    </tr>
    <tr>
      <td>453</td>
      <td>TALKED_TO_SPAMTON_BEHIND_BASEMENT_DOOR - Talked to Spamton behind the basement door -</td>
      <td>bool</td>
      <td>Whether you talked to Spamton through the basement door while he was changing forms. He doesn't repeat himself. <br></td>
    </tr>
    <tr>
      <td>454</td>
      <td>OBTAINED_DEALMAKER - Got Dealmaker -</td>
      <td>bool</td>
      <td>Whether you spared Spamton NEO. <br></td>
    </tr>
    <tr>
      <td>455</td>
      <td>RIDE_WITH_ME - Ride With Me -</td>
      <td>bool</td>
      <td>Whether you said "Noelle will ride with me" on Snowgrave. Unaccessed. <br></td>
    </tr>
    <tr>
      <td>456</td>
      <td>DEFEATED_SNOWGRAVE_NEO - Defeated SnowGrave NEO -</td>
      <td>bool</td>
      <td>Whether you defeated Spamton NEO on Snowgrave. <br></td>
    </tr>
    <tr>
      <td>457</td>
      <td>SPARED_BERDLY_ALL_THREE_TIMES - Spared all three -</td>
      <td>bool</td>
      <td>Whether you spared Berdly all three times, keeping him from breaking his arm. <br></td>
    </tr>
    <tr>
      <td>458</td>
      <td>HOUSES_HIT - Houses hit -</td>
      <td>number</td>
      <td>The number of houses you hit with the swan boat, converted to TP at the start of the Rouxls fight. Maximum 7. <br></td>
    </tr>
    <tr>
      <td>459</td>
      <td>PUT_DISK_MANNEQUIN - Put the disk in the mannequin -</td>
      <td>bool</td>
      <td>Whether you tried to put the LoadedDisk into the Mannequin. It doesn't repeat. <br></td>
    </tr>
    <tr>
      <td>460</td>
      <td>OBTAINED_JEVIL_HOLE - Got the Jevil-hole item -</td>
      <td>bool</td>
      <td>Whether you got the Jevil item from the Castle Town hole. Accessed, but not necessary. <br></td>
    </tr>
    <tr>
      <td>461</td>
      <td>INTERACTED_WITH_SINK_CH2 - Used the sink -</td>
      <td>bool</td>
      <td>Whether you interacted with Rudy's sink in Chapter 2. See also flag 278. <br></td>
    </tr>
    <tr>
      <td>462</td>
      <td>CARS_HIT - Cars hit -</td>
      <td>number</td>
      <td>The number of cars you hit. If less than 3 and you're otherwise pacifistic enough, you get the Castle Town tiny car. <br></td>
    </tr>
    <tr>
      <td>463</td>
      <td>READ_CYBERPEDIA - Read the Cyberpedia -</td>
      <td>bool</td>
      <td>Whether you read Ralsei's editable Cyberpedia entry. <br></td>
    </tr>
    <tr>
      <td>464</td>
      <td>TALKED_TO_SWATCH_ABOUT_TOPCHEF - Talked to Swatch about Topchef -</td>
      <td>bool</td>
      <td>Whether you talked to Swatch in the Castle Town Cafe about removing Topchef. Poor man. <br></td>
    </tr>
    <tr>
      <td>465</td>
      <td>CAR_PART_COMPLETED - Completed the car section -</td>
      <td>bool</td>
      <td>Whether you completed the car sequence. You can't get the tiny car on Snowgrave, even with all recruits, because of this. <br></td>
    </tr>
    <tr>
      <td>466</td>
      <td>JUNKBALL_DROPPED - Dropped the junk ball -</td>
      <td>bool</td>
      <td>Whether you dropped the Ball of Junk at any point. Unaccessed. <br></td>
    </tr>
    <tr>
      <td>467</td>
      <td>CHESTMARK_OPENED - Opened Chestmark -</td>
      <td>bool</td>
      <td>Keeps you from opening the Chestmark chest multiple times. <br></td>
    </tr>
    <tr>
      <td>468</td>
      <td>SPAMTON_NO_ROOM - Spamton No Room -</td>
      <td>map</td>
      <td>Whether you had no room after defeating Spamton NEO. Spawns the chest. <br>0 = Default state<br>1 = No room Pacifist<br>2 = No room Snowgrave<br></td>
    </tr>
    <tr>
      <td>469</td>
      <td>CANT_GO_BACK_TIP - Saw the no-return tip -</td>
      <td>bool</td>
      <td>Whether the save point reminded you that you can't go back to the Cyber World if you overwrite your save in Castle Town. Consider this carefully! <br></td>
    </tr>
    <tr>
      <td>500</td>
      <td>RUDINN_FIGHT_COUNT - First Rudinn fight count -</td>
      <td>number</td>
      <td>The number of times you've fought the first Rudinn. Changes its encounter text. <br></td>
    </tr>
    <tr>
      <td>501</td>
      <td>TRIPLE_HATHY_OUTCOME - Triple Hathy encounter state -</td>
      <td>map</td>
      <td>Tracks an unused room_field2 encounter state and related dialogue. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>502</td>
      <td>PONMAN_FIGHT_COUNT - Ponman fight count -</td>
      <td>number</td>
      <td>The number of times you fought Ponmen. Minor changes to the overworld chasing Ponmen. <br></td>
    </tr>
    <tr>
      <td>503</td>
      <td>SUSIE_COMPLIMENT_COUNT - Susie complimented Rudinn Ranger -</td>
      <td>bool</td>
      <td>Whether Susie has attempted to compliment Rudinn Ranger. Free ham sandwich day does not repeat. <br></td>
    </tr>
    <tr>
      <td>504</td>
      <td>SUSIE_FLIRT_COUNT - Susie flirt attempts on Head Hathy -</td>
      <td>number</td>
      <td>The number of times you used X-Flirt on Head Hathy. She tries the first time, makes Ralsei try the second, and you take over from the third. <br></td>
    </tr>
    <tr>
      <td>505</td>
      <td>FOUGHT_RABBICK - Fought Rabbick -</td>
      <td>bool</td>
      <td>Whether you fought any Rabbicks. If so, they run slower in the forest maze. Also set when you fight Clover. <br></td>
    </tr>
    <tr>
      <td>506</td>
      <td>FOUGHT_BLOXER - Fought Bloxer -</td>
      <td>bool</td>
      <td>Whether you fought Bloxer. If so, they don't chase you as diligently. <br></td>
    </tr>
    <tr>
      <td>507</td>
      <td>FOUGHT_RUDINN_RANGER - Fought Rudinn Ranger -</td>
      <td>bool</td>
      <td>Whether you fought Rudinn Ranger. If so, they don't chase you at all. <br></td>
    </tr>
    <tr>
      <td>508</td>
      <td>FOUGHT_HATHYX - Fought Head Hathy -</td>
      <td>bool</td>
      <td>Whether you fought Head Hathy. If so, they don't chase you at all. <br></td>
    </tr>
    <tr>
      <td>509</td>
      <td>PIPPINS_BRIBE_ACT_COUNT - Pippins Ralsei ACT -</td>
      <td>number</td>
      <td>Number of Bribe ACTs used on Pippins. Unique dialogue first time. <br></td>
    </tr>
    <tr>
      <td>510</td>
      <td>PIPPINS_CHEAT_ACT_COUNT - Pippins Susie ACT -</td>
      <td>number</td>
      <td>Number of Cheat ACTs used on Pippins. <br></td>
    </tr>
    <tr>
      <td>511</td>
      <td>USED_S_ACTION_ON_SHUTTAH - Used Susie's ACT on Shuttah -</td>
      <td>bool</td>
      <td>Whether you've used S-Action during a Shuttah battle. Randomizes flavortext on repeat. <br></td>
    </tr>
    <tr>
      <td>512</td>
      <td>USED_R_ACTION_ON_SHUTTAH - Used Ralsei's ACT on Shuttah -</td>
      <td>bool</td>
      <td>Whether you've used R-Action during a Shuttah battle. Reduces flavortext on repeat. <br></td>
    </tr>
    <tr>
      <td>513</td>
      <td>SHUTTAH_KRIS_PIC - Shuttah Kris photo -</td>
      <td>bool</td>
      <td>Whether you took a photo of Kris during the Shuttah fight. Alters repeat dialogue. <br></td>
    </tr>
    <tr>
      <td>514</td>
      <td>SHUTTAH_SUSIE_PIC - Shuttah Susie photo -</td>
      <td>bool</td>
      <td>Whether you took a photo of Susie during the Shuttah fight. Alters repeat dialogue. <br></td>
    </tr>
    <tr>
      <td>515</td>
      <td>SHUTTAH_RALSEI_PIC - Shuttah Ralsei photo -</td>
      <td>bool</td>
      <td>Whether you took a photo of Ralsei during the Shuttah fight. Alters repeat dialogue. <br></td>
    </tr>
    <tr>
      <td>520</td>
      <td>RUDINN_VIOLENCES - Rudinns beaten up -</td>
      <td>number</td>
      <td>The number of Rudinns you have beat up. Subtracted from flag 40 if you apologize. <br></td>
    </tr>
    <tr>
      <td>521</td>
      <td>HATHY_VIOLENCES - Hathys beaten up -</td>
      <td>number</td>
      <td>The number of Hathys you have beat up. Subtracted from flag 40 if 2 or less and you apologize. <br></td>
    </tr>
    <tr>
      <td>522</td>
      <td>CLOVER_VIOLENCE - Violence -</td>
      <td>bool</td>
      <td>Whether you beat up Clover the first time. You can't apologize. <br></td>
    </tr>
    <tr>
      <td>523</td>
      <td>RUDINN_HIT_BY_SUSIE_COUNT - Susie Rudinn whacks -</td>
      <td>number</td>
      <td>Intended for Susie beating up Rudinns, but unset. See flag 43. <br></td>
    </tr>
    <tr>
      <td>524</td>
      <td>HATHY_HIT_BY_SUSIE_COUNT - Susie Hathy whacks -</td>
      <td>number</td>
      <td>Intended for Susie beating up Hathys, but unset. See flag 43. <br></td>
    </tr>
    <tr>
      <td>525</td>
      <td>FIRST_WEREWIRE_ENCOUNTER_OUTCOME - Werewire -</td>
      <td>map</td>
      <td>Tracks the state of the first random Werewire encounter. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>526</td>
      <td>FIRST_TASQUE_ENCOUNTER_OUTCOME - Tasque -</td>
      <td>map</td>
      <td>Tracks the state of the first random Tasque encounter, the one that jumps out at you. Then it's reused for like Giga Queen deaths or something, which is a little broken. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>527</td>
      <td>FIRST_VIROVIROKUN_ENCOUNTER_OUTCOME - Virovirokun -</td>
      <td>map</td>
      <td>Tracks the state of the first Virovirokun encounter, the one en route to AGREE2ALL. Also reused for Giga Queen stuff, doing Round 1 hitless causes this to be set to 1. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>528</td>
      <td>SECOND_SMORGASBORD_ENCOUNTER_OUTCOME - Smorgasbord -</td>
      <td>map</td>
      <td>Tracks the state of the Smorgasboard 2 encounter. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>529</td>
      <td>BERDLY_1_ENCOUNTER_OUTCOME - First fight -</td>
      <td>map</td>
      <td>Tracks the state of the first Berdly battle. Used to determine if he breaks his arm. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>530</td>
      <td>FIRST_POPPUP_ENCOUNTER_OUTCOME - Poppup -</td>
      <td>map</td>
      <td>Tracks the state of the first Poppup encounter, before you meet Noelle. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>531</td>
      <td>TUTORIAL_VIROVIROKUN_ENCOUNTER_OUTCOME - Virovirokun -</td>
      <td>map</td>
      <td>Tracks the state of the Virovirokun that tells Noelle how to battle. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>532</td>
      <td>AMBYU_LANCE_ENCOUNTER_OUTCOME - Ambyu-Lance -</td>
      <td>map</td>
      <td>Tracks the state of the first Ambyu-Lance encounter. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>533</td>
      <td>ANTIVIRUS_VIROVIROKUN_ENCOUNTER_OUTCOME - Ambyu-Lance + Virovirokun -</td>
      <td>map</td>
      <td>Tracks the state of the Ambyu-Lance + Virovirokun encounter. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>534</td>
      <td>DOUBLE_WEREWIRE_ENCOUNTER_OUTCOME - 2 Werewires -</td>
      <td>map</td>
      <td>Tracks the state of the double Werewire encounter toward the middle of Cyber City. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>535</td>
      <td>ERASER_VIROVIROKUN_ENCOUNTER_OUTCOME - 2 Virovirokuns -</td>
      <td>map</td>
      <td>Tracks the state of the double Virovirokun encounter blocking the way to the Bounce Blade. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>536</td>
      <td>SINGLE_MAUS_ENCOUNTER_OUTCOME - Maus -</td>
      <td>map</td>
      <td>Tracks the state of the single Maus encounter when rubbing the cheese. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>537</td>
      <td>CHEESE_MAUS_ENCOUNTER_OUTCOME - Maus -</td>
      <td>map</td>
      <td>Tracks the state of Maus encounters when bumping into cheese. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>538</td>
      <td>POPPUP_MAUS_ENCOUNTER_OUTCOME - Poppup + Maus -</td>
      <td>map</td>
      <td>Tracks the state of the Poppup and Maus encounter after the last mouse puzzle. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>539</td>
      <td>GLOW_WRIST_TASQUE_ENCOUNTER_OUTCOME - Tasque -</td>
      <td>map</td>
      <td>Tracks the state of the second random Tasque encounter, in the room with the Glow Wrist and checksmark. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>540</td>
      <td>FIRST_SWATCHLING_ENCOUNTER_OUTCOME - Swatchling -</td>
      <td>map</td>
      <td>Tracks the state of the first Swatchling encounter when disrespecting the pottery. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>541</td>
      <td>MULTIPLE_SWATCHLINGS_ENCOUNTER_OUTCOME - Swatchlings -</td>
      <td>map</td>
      <td>Tracks the state of the second Swatchling encounter, in the room full of vases. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>542</td>
      <td>TASQUE_MANAGER_ENCOUNTER_OUTCOME - Tasque Manager -</td>
      <td>map</td>
      <td>Tracks the state of the Tasque Manager battle. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>543</td>
      <td>MAUSWHEEL_ENCOUNTER_OUTCOME - Mauswheel -</td>
      <td>map</td>
      <td>Tracks the state of the Mauswheel battle. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>544</td>
      <td>RUNNING_SWATCHLINGS_ENCOUNTER_OUTCOME - Swatchlings -</td>
      <td>map</td>
      <td>Tracks the state of the Swatchlings running after/from vases on 2F. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>545</td>
      <td>ACID_WEREWIRE_ENCOUNTER_OUTCOME - Werewires -</td>
      <td>map</td>
      <td>Tracks the state of the Werewires on the acid lake. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>546</td>
      <td>ROUXLS_ENCOUNTER_OUTCOME - Rouxls -</td>
      <td>map</td>
      <td>Tracks the state of the Rouxls/Thrash Machine battle. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>547</td>
      <td>WEREWEREWIRE_ENCOUNTER_OUTCOME - Werewerewire -</td>
      <td>map</td>
      <td>Tracks the state of the Werewerewire encounter. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>548</td>
      <td>QUEEN_ENCOUNTER_OUTCOME - Queen -</td>
      <td>map</td>
      <td>Tracks the state of the normal Queen battle. Used to determine if Berdly breaks his arm. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>549</td>
      <td>SPAMTON_ENCOUNTER_OUTCOME - Spamton -</td>
      <td>map</td>
      <td>Tracks the state of the normal Spamton battle. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>550</td>
      <td>BERDLY_2_ENCOUNTER_OUTCOME - Second fight -</td>
      <td>map</td>
      <td>Tracks the state of the second Berdly battle. Used to determine if he breaks his arm. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>551</td>
      <td>GIGA_QUEEN_ENCOUNTER_OUTCOME - GIGA Queen -</td>
      <td>map</td>
      <td>Tracks the state saved for the GIGA Queen battle. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>552</td>
      <td>SCRIPTED_ENCOUNTER_OUTCOME - Scripted battles -</td>
      <td>map</td>
      <td>Tracks the state of various scripted encounters that are non-repeatable anyway (first Werewires and Sweet Cap'n Cakes). <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>553</td>
      <td>TRIPLE_AMBYU_LANCE_ENCOUNTER_OUTCOME - 3 Ambyu-Lances -</td>
      <td>map</td>
      <td>Tracks the state of the triple Ambyu-Lance encounter on Snowgrave in the big car room. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>554</td>
      <td>TASQUE_VIROVIROKUN_ENCOUNTER_OUTCOME - Tasque + 2 Virovirokuns -</td>
      <td>map</td>
      <td>Tracks the state of the double Virovirokun single Tasque encounter on Snowgrave. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>555</td>
      <td>SNOWGRAVE_MAICE_1_ENCOUNTER_OUTCOME - Maice -</td>
      <td>map</td>
      <td>Tracks the state of the first Maice encounter on Snowgrave (no cheese is involved). <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>556</td>
      <td>FLEEING_TASQUE_ENCOUNTER_OUTCOME - Tasques -</td>
      <td>map</td>
      <td>Tracks the state of the Snowgrave Tasques that run away from you. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>557</td>
      <td>DINING_HALL_PIPIS_ENCOUNTER_OUTCOME - Pipis encounter -</td>
      <td>map</td>
      <td>Tracks the state of the last Pipis encounter you had in the dining hall. Well, it would. Pipis don't chase you. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>558</td>
      <td>RETURNING_TASQUE_ENCOUNTER_OUTCOME - Tasques + Swatchlings -</td>
      <td>map</td>
      <td>Tracks the state of the Tasques and Swatchlings found when backtracking to Tasque Manager's room. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>559</td>
      <td>TRASH_ZONE_POPPUP_ENCOUNTER_OUTCOME - Poppups -</td>
      <td>map</td>
      <td>Tracks the state of the Poppups found when backtracking to the Trash Zone with Noelle. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>560</td>
      <td>TRASH_ZONE_VIROVIROKUN_ENCOUNTER_OUTCOME - Virovirokun -</td>
      <td>map</td>
      <td>Tracks the state of the Virovirokun found when backtracking to the Trash Zone on Snowgrave. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>561</td>
      <td>TRASH_ZONE_WEREWIRE_ENCOUNTER_OUTCOME - Werewire -</td>
      <td>map</td>
      <td>Tracks the state of the Werewire found when backtracking to the Trash Zone on Snowgrave. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>562</td>
      <td>ROAD_AMBYU_LANCE_ENCOUNTER_OUTCOME - Ambyu-Lance -</td>
      <td>map</td>
      <td>Tracks the state of the Ambyu-Lance found in the middle of the road on Snowgrave. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>563</td>
      <td>ROAD_TASQUE_ENCOUNTER_OUTCOME - Tasque -</td>
      <td>map</td>
      <td>Tracks the state of the Tasque found in the middle of the road on Snowgrave. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>564</td>
      <td>ROAD_VIROVIROKUN_ENCOUNTER_OUTCOME - Virovirokun -</td>
      <td>map</td>
      <td>Tracks the state of the Virovirokun found in the middle of the road on Snowgrave. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>565</td>
      <td>ROAD_WEREWIRE_ENCOUNTER_OUTCOME - Werewire -</td>
      <td>map</td>
      <td>Tracks the state of the Werewire found in the middle of the road on Snowgrave. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>566</td>
      <td>SNOWGRAVE_MAICE_2_ENCOUNTER_OUTCOME - Maice -</td>
      <td>map</td>
      <td>Tracks the state of the second Maice encounter on Snowgrave. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>567</td>
      <td>SNOWGRAVE_DOUBLE_POPPUP_ENCOUNTER_OUTCOME - 2 Poppups -</td>
      <td>map</td>
      <td>Tracks the state of the double Poppup encounter that hides under a cone on Snowgrave. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>569</td>
      <td>SNOWGRAVE_WEREWEREWIRE_ENCOUNTER_OUTCOME - Werewerewire -</td>
      <td>map</td>
      <td>That's gotta be the most abbreviated one yet! Tracks the state of Werewerewire on Snowgrave, since it's found elsewhere. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>570</td>
      <td>ULTIMATE_HEAL_AMBYU_LANCE_ENCOUNTER_OUTCOME - Ambyu-Lance -</td>
      <td>map</td>
      <td>Tracks the state of the Ambyu-Lance encounter where Susie demonstrates UltimateHeal. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>571</td>
      <td>SPAMTON_NEO_ENCOUNTER_OUTCOME - Spamton NEO -</td>
      <td>map</td>
      <td>For some reason doesn't use "encounterflag" but tracks the state of Spamton NEO in case that's ever needed later. There are already like 2 flags for him anyway. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>572</td>
      <td>VASE_POPPUP_ENCOUNTER_OUTCOME - Poppup -</td>
      <td>map</td>
      <td>Tracks the state of the Poppup under the vase near where Susie and Ralsei leave you. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>580</td>
      <td>BOARD_1_OASIS_SHADOWGUY_ENCOUNTER_OUTCOME - 2 Shadowguys -</td>
      <td>map</td>
      <td>Tracks the state of the Shadowguy encounter in the room on the left of the oasis in Board 1. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>581</td>
      <td>BOARD_1_BLOCK_ROOM_SHADOWGUY_ENCOUNTER_OUTCOME - 3 Shadowguys -</td>
      <td>map</td>
      <td>Tracks the state of the Shadowguy encounter in the block-pushing room in Board 1. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>582</td>
      <td>BOARD_2_SHRINE_PIPPINS_ENCOUNTER_OUTCOME - 2 Pippins -</td>
      <td>map</td>
      <td>Tracks the state of the Pippins encounter in the room on the left of the Kodakoda shrine in Board 2. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>583</td>
      <td>BOARD_2_CONTROLLER_PIPPINS_ENCOUNTER_OUTCOME - 3 Pippins -</td>
      <td>map</td>
      <td>Tracks the state of the Pippins encounter that Susie runs into using Kris's controller in Board 2. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>584</td>
      <td>BOARD_2_SHUTTAH_ENCOUNTER_OUTCOME - Shuttah -</td>
      <td>map</td>
      <td>Tracks the state of the Shuttah boss battle in Board 2. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>585</td>
      <td>ROUXLS_WEATHER_ENCOUNTER_OUTCOME - Rouxls + Weather Duo -</td>
      <td>map</td>
      <td>Tracks the state of the Rouxls Kaard throuple battle. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>586</td>
      <td>ZAPPER_SHUTTAH_ENCOUNTER_OUTCOME - Zapper + Shuttah -</td>
      <td>map</td>
      <td>Tracks the state of the Zapper + Shuttah encounter later in TV world. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>587</td>
      <td>FIRST_WATERCOOLER_ENCOUNTER_OUTCOME - Watercooler -</td>
      <td>map</td>
      <td>Tracks the state of the Watercooler in the C-rank room. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>588</td>
      <td>UNUSED_WATERCOOLER_ENCOUNTER_OUTCOME - Watercooler encounter -</td>
      <td>map</td>
      <td>Never set, would have tracked the state of a Watercooler encounter in the unused room_dw_b3bs_watercooler. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>589</td>
      <td>FIRST_ZAPPER_ENCOUNTER_OUTCOME - Zapper -</td>
      <td>map</td>
      <td>Tracks the state of the Zapper in front of the suspicious door. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>590</td>
      <td>FIRST_SHADOWGUY_ENCOUNTER_OUTCOME - Shadowguy + Shuttah -</td>
      <td>map</td>
      <td>Tracks the state of the first Shadow Guy + Shuttah encounter in TV World. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>591</td>
      <td>FIRST_RIBBICK_ENCOUNTER_OUTCOME - Ribbick -</td>
      <td>map</td>
      <td>Tracks the state of the first Ribbick encounter in TV World. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>592</td>
      <td>SECOND_WATERCOOLER_ENCOUNTER_OUTCOME - Watercooler + Shadowguys -</td>
      <td>map</td>
      <td>Tracks the state of the Watercooler encounter in TV World, along with the Shadowguys that drop down in the Susiezilla room. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>593</td>
      <td>SECOND_RIBBICK_ENCOUNTER_OUTCOME - Ribbick -</td>
      <td>map</td>
      <td>Tracks the state of the second Ribbick encounter in TV World. Can turn into disguised rabbicks. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>605</td>
      <td>RECRUITED_RUDINN - Recruited Rudinn -</td>
      <td>bool</td>
      <td>Set at the start of Chapter 2. You NEED at least one recruit. <br></td>
    </tr>
    <tr>
      <td>606</td>
      <td>RECRUITED_HATHY - Recruited Hathy -</td>
      <td>bool</td>
      <td>Set at the start of Chapter 2. <br></td>
    </tr>
    <tr>
      <td>611</td>
      <td>RECRUITED_PONMAN - Recruited Ponman -</td>
      <td>bool</td>
      <td>Set at the start of Chapter 2. <br></td>
    </tr>
    <tr>
      <td>613</td>
      <td>RECRUITED_RABBICK - Recruited Rabbick -</td>
      <td>bool</td>
      <td>Set at the start of Chapter 2. <br></td>
    </tr>
    <tr>
      <td>614</td>
      <td>RECRUITED_BLOXER - Recruited Bloxer -</td>
      <td>bool</td>
      <td>Set at the start of Chapter 2. <br></td>
    </tr>
    <tr>
      <td>615</td>
      <td>RECRUITED_JIGSAW - Recruited Jigsawry -</td>
      <td>bool</td>
      <td>Set at the start of Chapter 2. <br></td>
    </tr>
    <tr>
      <td>620</td>
      <td>RECRUITED_JEVIL - Recruited JEVIL -</td>
      <td>bool</td>
      <td>JEVIL recruit flag with recruit info. <br></td>
    </tr>
    <tr>
      <td>622</td>
      <td>RECRUITED_RUDINN_RANGER - Recruited Rudinn Ranger -</td>
      <td>bool</td>
      <td>Set at the start of Chapter 2. <br></td>
    </tr>
    <tr>
      <td>623</td>
      <td>RECRUITED_HEAD_HATHY - Recruited Head Hathy -</td>
      <td>bool</td>
      <td>Set at the start of Chapter 2. <br></td>
    </tr>
    <tr>
      <td>630</td>
      <td>RECRUITED_AMBYU_LANCE - Recruited Ambyu-Lance -</td>
      <td>bool</td>
      <td>Whether you recruited Ambyu-Lance. <br></td>
    </tr>
    <tr>
      <td>631</td>
      <td>RECRUITED_POPPUP - Recruited Poppup -</td>
      <td>bool</td>
      <td>Whether you recruited Poppup. <br></td>
    </tr>
    <tr>
      <td>632</td>
      <td>RECRUITED_TASQUE - Recruited Tasque -</td>
      <td>bool</td>
      <td>Whether you recruited Tasque. <br></td>
    </tr>
    <tr>
      <td>633</td>
      <td>RECRUITED_WEREWIRE - Recruited Werewire -</td>
      <td>bool</td>
      <td>Whether you recruited Plugboy, by which I mean Werewire. <br></td>
    </tr>
    <tr>
      <td>634</td>
      <td>RECRUITED_MAUS - Recruited Maus -</td>
      <td>bool</td>
      <td>Whether you recruited Maus. <br></td>
    </tr>
    <tr>
      <td>635</td>
      <td>RECRUITED_VIROVIROKUN - Recruited Virovirokun -</td>
      <td>bool</td>
      <td>Whether you recruited Virovirokun. <br></td>
    </tr>
    <tr>
      <td>636</td>
      <td>RECRUITED_SWATCHLING - Recruited Swatchling -</td>
      <td>bool</td>
      <td>Whether you recruited Swatchling. <br></td>
    </tr>
    <tr>
      <td>640</td>
      <td>RECRUITED_WEREWEREWIRE - Recruited Werewerewire -</td>
      <td>bool</td>
      <td>Whether you recruited Werewerewire. It doesn't appear for the powers combined scene. <br></td>
    </tr>
    <tr>
      <td>642</td>
      <td>RECRUITED_TASQUE_MANAGER - Recruited Tasque Manager -</td>
      <td>bool</td>
      <td>Whether you recruited Tasque Manager. <br></td>
    </tr>
    <tr>
      <td>644</td>
      <td>RECRUITED_MAUSWHEEL - Recruited Mauswheel -</td>
      <td>bool</td>
      <td>Whether you recruited Mauswheel. <br></td>
    </tr>
    <tr>
      <td>654</td>
      <td>RECRUITED_SHADOWGUY - Recruited Shadowguy -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>655</td>
      <td>RECRUITED_SHUTTAH - Recruited Shuttah -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>656</td>
      <td>RECRUITED_ZAPPER - Recruited Zapper -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>657</td>
      <td>RECRUITED_RIBBICK - Recruited Ribbick -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>658</td>
      <td>RECRUITED_COOLER - Recruited Watercooler -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>659</td>
      <td>RECRUITED_PIPPINS - Recruited Pippins -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>660</td>
      <td>RECRUITED_ELNINA - Recruited Elnina -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>661</td>
      <td>RECRUITED_LANINO - Recruited Lanino -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>662</td>
      <td>RECRUITED_GUEI - Recruited Guei -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>663</td>
      <td>RECRUITED_BALTHIZARD - Recruited Balthizard -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>664</td>
      <td>RECRUITED_BIBLIOX - Recruited Bibliox -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>665</td>
      <td>RECRUITED_MIZZLE - Recruited Mizzle -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>666</td>
      <td>RECRUITED_WICABEL - Recruited Wicabel -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>667</td>
      <td>RECRUITED_WINGLADE - Recruited Winglade -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>668</td>
      <td>RECRUITED_ORGANIKK - Recruited Organikk -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>669</td>
      <td>RECRUITED_MISS_MIZZLE - Recruited Ms. Mizzle -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>670</td>
      <td>RECRUITED_FLORADINN - Recruited Floradinn -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>671</td>
      <td>RECRUITED_LEAFLING - Recruited Leafling -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>672</td>
      <td>RECRUITED_SHI - Recruited Shi -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>673</td>
      <td>RECRUITED_SHINOBEETLE - Recruited Shinobeetle -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>674</td>
      <td>RECRUITED_KAWKAW - Recruited KawKaw -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>675</td>
      <td>RECRUITED_SHEARY - Recruited Sheary -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>676</td>
      <td>RECRUITED_NETSKIE - Recruited Netskie -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>677</td>
      <td>RECRUITED_TERAKOTA - Recruited Terakota -</td>
      <td>bool</td>
      <td>Recruit progress. <br></td>
    </tr>
    <tr>
      <td>700</td>
      <td>COMPLETED_CHURCH_STICKER_FIGHT - Completed the church sticker fight -</td>
      <td>bool</td>
      <td>Viewed the cutscene of Kris and Susie placing stickers on each other at the church. Unaccessed as of chapter 4. <br></td>
    </tr>
    <tr>
      <td>701</td>
      <td>COMPLETED_DINER_SCENE_WITH_SUSIE - Completed the diner scene with Susie -</td>
      <td>bool</td>
      <td>Finished the cutscene of the diner with Susie. <br></td>
    </tr>
    <tr>
      <td>702</td>
      <td>DREW_SUSIE_AT_DINER - Drew Susie at the diner -</td>
      <td>bool</td>
      <td>Drew Susie during the diner cutscene. <br></td>
    </tr>
    <tr>
      <td>703</td>
      <td>WROTE_IN_DINER_CORNER - Wrote in the diner window -</td>
      <td>bool</td>
      <td>Wrote something in the corner during the diner cutscene. Unaccessed as of chapter 4. <br></td>
    </tr>
    <tr>
      <td>704</td>
      <td>ACTIVATED_UNUSED_DARKROOM_WALL_SWITCH - Activated the darkroom wall switch -</td>
      <td>bool</td>
      <td>Activated the switch in the unused room_dw_church_darkroom1_old. <br></td>
    </tr>
    <tr>
      <td>705</td>
      <td>LIT_ALL_UNUSED_CANDLES - Lit all candles -</td>
      <td>bool</td>
      <td>Whether all the candles were lit in an unused candle lighting room. <br></td>
    </tr>
    <tr>
      <td>706</td>
      <td>COMPLETED_CASTLE_TOWN_RETURN_SCENE_CH4 - Completed the Castle Town return scene -</td>
      <td>bool</td>
      <td>Finished the cutscene of returning to Castle Town and greeting Ralsei at the start of chapter 4. <br></td>
    </tr>
    <tr>
      <td>707</td>
      <td>NOELLE_SLAPPED_KRIS_WEIRD_ROUTE - Had Noelle slap Kris -</td>
      <td>bool</td>
      <td>Aborted the Weird Route late enough for Noelle to yell and slap you for your "prank". <br></td>
    </tr>
    <tr>
      <td>708</td>
      <td>KEPT_NOELLE_WATCH_AFTER_CH2 - Took Noelle's watch -</td>
      <td>bool</td>
      <td>Kept Noelle's watch in your equipment or inventory at the end of chapter 2. <br></td>
    </tr>
    <tr>
      <td>709</td>
      <td>HOLIDAY_GATE_STATE - Gate -</td>
      <td>bool</td>
      <td>Opened the gate of the Holiday residence. There is a bug where it is set to -1 if you kill a Titan Spawn because the game thinks it's recruitable. <br></td>
    </tr>
    <tr>
      <td>710</td>
      <td>SAW_EMPTY_RALSEI_ROOM - Ralsei's room -</td>
      <td>map</td>
      <td>Whether you saw the emptiness of Ralsei's room in Castle Town. <br>0 = Default state<br>1 = Susie ran off, followed by Ralsei<br>2 = Finished the Ralsei room cutscene<br></td>
    </tr>
    <tr>
      <td>711</td>
      <td>HEARD_RALSEI_PLUSH_DIALOGUE - Heard Ralsei's plush dialogue -</td>
      <td>bool</td>
      <td>Listened to Ralsei after interacting with his Ralsei plush (obtained in chapter 2) in his room. <br></td>
    </tr>
    <tr>
      <td>712</td>
      <td>LAKE_SITTING_SCENE_PROGRESS - Lake sitting -</td>
      <td>map</td>
      <td>Progress in cutscene after sitting down by the lake at the end of chapter 4. Interrupted by getting up. <br>0 = Default state<br>1 = Susie asks if you can hear a song<br>2 = Kris looks at Susie<br>3 = Susie asks if she got something on her face<br>4 = Given the option to say what's on your mind<br>5 = Susie gets up and says they should go<br></td>
    </tr>
    <tr>
      <td>713</td>
      <td>LAKE_CONVERSATION_RESPONSE - Beach festival reply -</td>
      <td>map</td>
      <td>Which option you picked when asked to say what's on your mind or nothing at the lake. Unaccessed as of chapter 4. <br>0 = Default state<br>1 = Say what's on your mind<br>2 = Say nothing<br></td>
    </tr>
    <tr>
      <td>714</td>
      <td>BERDLY_PHONE_CALL_PROGRESS - Berdly call -</td>
      <td>map</td>
      <td>Progress in the Berdly phone call at Noelle's house. <br>0 = Default state<br>1 = Picked up Noelle's phone<br>2 = Go with Berdly<br>3 = Sing the wrong number song<br></td>
    </tr>
    <tr>
      <td>715</td>
      <td>ASKED_ALVIN_ABOUT_SHELTER - Asked Alvin about the shelter -</td>
      <td>bool</td>
      <td>Talked to Alvin and picked "Enter the shelter" after his sermon. <br></td>
    </tr>
    <tr>
      <td>716</td>
      <td>PRAISED_ALVINS_SERMON - Praised Alvin's sermon -</td>
      <td>bool</td>
      <td>Talked to Alvin and picked the best option after his sermon. <br></td>
    </tr>
    <tr>
      <td>717</td>
      <td>ASKED_ALVIN_ABOUT_ASGORE - Asked Alvin about Asgore -</td>
      <td>bool</td>
      <td>Talked to Alvin and picked "Asgore" after his sermon. <br></td>
    </tr>
    <tr>
      <td>718</td>
      <td>MONSTER_KID_CHURCH_RESPONSE - Monster Kid response -</td>
      <td>map</td>
      <td>What you said to Monster Kid after Alvin's sermon. <br>0 = Default state<br>1 = Shelter<br>2 = Susie will not be tamed<br></td>
    </tr>
    <tr>
      <td>719</td>
      <td>MADE_ALPHYS_JUICE - Made Alphys's juice -</td>
      <td>bool</td>
      <td>Successfully created Alphys' juice combo at church. <br></td>
    </tr>
    <tr>
      <td>720</td>
      <td>ALPHYS_JUICE_OUTCOME - Alphys response -</td>
      <td>map</td>
      <td>Whether you gave Alphys her juice combo… or not. <br>0 = Default state<br>1 = Offer juice<br>2 = Drink juice in front of her<br></td>
    </tr>
    <tr>
      <td>722</td>
      <td>ALPHYS_SHELTER_REASON - Shelter reason -</td>
      <td>map</td>
      <td>The reason you gave to Alphys for asking about the shelter. <br>0 = Default state<br>1 = Architectural history research<br>2 = Put hay inside new house for Susie<br></td>
    </tr>
    <tr>
      <td>723</td>
      <td>ALPHYS_UNDYNE_CHURCH_RESPONSE - Undyne response -</td>
      <td>map</td>
      <td>Talked to Alphys about Undyne at church. An extra value is available if we gave her Undyne's chocolate in chapter 2. <br>0 = Default state<br>1 = Undyne / She gave you chocolates though<br>2 = It's because of me<br></td>
    </tr>
    <tr>
      <td>726</td>
      <td>HEARD_NOELLE_SANTA_EXPLANATION - Heard Noelle explain the Santas -</td>
      <td>bool</td>
      <td>Whether Noelle has explained the Santas. <br></td>
    </tr>
    <tr>
      <td>727</td>
      <td>HEARD_NOELLE_DEAD_SANTA_COMMENT - Heard Noelle's dead-Santa comment -</td>
      <td>bool</td>
      <td>Whether Noelle commented on Kris trying to "starve" the Santas. <br></td>
    </tr>
    <tr>
      <td>728</td>
      <td>SAW_UNUSED_TREAT_LAUNCHER_SCENE - Saw the treat-launcher scene -</td>
      <td>bool</td>
      <td>Viewed the cutscene of Noelle showing off the unused holiday treat launcher. <br></td>
    </tr>
    <tr>
      <td>730</td>
      <td>HEARD_NOELLE_CACTUS_COMMENT - Heard Noelle's cactus comment -</td>
      <td>bool</td>
      <td>Whether Noelle commented on the cactus being called Tsuntsun by Berdly. <br></td>
    </tr>
    <tr>
      <td>731</td>
      <td>CHECKED_NOELLE_BROWSING_HISTORY - Checked Noelle's browsing history -</td>
      <td>bool</td>
      <td>Checked Noelle's browsing history with Susie. <br></td>
    </tr>
    <tr>
      <td>732</td>
      <td>FOUND_CAT_PETTERZ_4 - Found Cat Petterz 4 -</td>
      <td>bool</td>
      <td>Noticed Cat Petterz 4 on Noelle's computer. <br></td>
    </tr>
    <tr>
      <td>733</td>
      <td>TOOK_NOELLE_DESK_PENCIL - Took Noelle's desk pencil -</td>
      <td>bool</td>
      <td>Took the pencil from Noelle's homework desk. <br></td>
    </tr>
    <tr>
      <td>734</td>
      <td>COMPLETED_RALSEI_SUSIE_FESTIVAL_TALK - Completed Ralsei and Susie's festival talk -</td>
      <td>bool</td>
      <td>Whether you completed the talk between Susie and Ralsei prior to Tenna's introduction in Chapter 3. <br></td>
    </tr>
    <tr>
      <td>736</td>
      <td>NOELLE_KITCHEN_PHONE_LINE - Phone line -</td>
      <td>map</td>
      <td>Tracks the current line in the spooky phone call to Kris in Noelle's kitchen. <br>0 = ... dark... fountain... next...<br>1 = ... Susie... must not get... guitar...<br>2 = ... need... soul...<br>3 = Without... soul... Kris... will...<br>4 = ... Susie... guitar... code... stop...<br>5 = ... police... sacrifice... next week...<br>6 = ... church... tonight...<br>7 = ... Kris... dark world... no soul... can't...<br>8 = ...... ...... ......<br></td>
    </tr>
    <tr>
      <td>737</td>
      <td>NOELLE_KITCHEN_SOUL_CAPTURE_PROGRESS - Soul capture -</td>
      <td>map</td>
      <td>Tracks the progress in the cutscene of Kris catching the Soul in Noelle's kitchen. <br>0 = Default state<br>1 = Kris caught Soul in kitchen<br>2 = Kris put back Soul in closet<br></td>
    </tr>
    <tr>
      <td>738</td>
      <td>NOELLE_KITCHEN_PIANO_SONG - Piano song -</td>
      <td>map</td>
      <td>Tracks the current piano song being played by Kris in Noelle's kitchen. <br>0 = Default state<br>1 = kris_piano_sevenfour<br>2 = kris_piano_quiz<br>3 = kris_piano_lancer_waltz<br>4 = kris_piano_rouxls<br>5 = kris_piano_waitingroom<br>6 = kris_piano_shop<br>7 = kris_piano_last_prophecy<br>8 = kris_piano_prophecy<br>9 = Kris played all songs (unused?)<br></td>
    </tr>
    <tr>
      <td>739</td>
      <td>NOELLE_PRESENT_1_X - Present 1 X position -</td>
      <td>number</td>
      <td>X coordinate of the first present in Noelle's present room. <br></td>
    </tr>
    <tr>
      <td>740</td>
      <td>NOELLE_PRESENT_2_X - Present 2 X position -</td>
      <td>number</td>
      <td>X coordinate of the second present in Noelle's present room. <br></td>
    </tr>
    <tr>
      <td>741</td>
      <td>NOELLE_PRESENT_3_X - Present 3 X position -</td>
      <td>number</td>
      <td>X coordinate of the third present in Noelle's present room. <br></td>
    </tr>
    <tr>
      <td>742</td>
      <td>NOELLE_BATHROOM_ASGORE_LINE - Mirror -</td>
      <td>map</td>
      <td>Tracks the current line in the Asgore cutscene in Noelle's bathroom. <br>0 = Default state<br>1 = Dum dee dum...<br>2 = Phew! Cleaning up sure works up an appetite.<br>3 = ... I wonder if the kitchen has any treats for me...<br>4 = ... No. Not now. I can't afford to take a break.<br>5 = Now, more than ever... I need to concentrate.<br>6 = ... to settle this once and for all.<br>7 = ... I've got to go look again.<br></td>
    </tr>
    <tr>
      <td>744</td>
      <td>SHOWED_FAMILY_PHOTO_TO_SUSIE - Showed the family photo to Susie -</td>
      <td>bool</td>
      <td>Showed to Susie the old family photo on your fridge. <br></td>
    </tr>
    <tr>
      <td>745</td>
      <td>SHOWED_ASRIEL_PHOTO_TO_SUSIE - Showed Asriel's photo to Susie -</td>
      <td>bool</td>
      <td>Showed to Susie the Asriel photo on your fridge. <br></td>
    </tr>
    <tr>
      <td>746</td>
      <td>OPENED_DRAGON_BOOK_DRAWER_FOR_SUSIE - Opened the dragon-book drawer for Susie -</td>
      <td>bool</td>
      <td>Opened the drawer containing How To Draw Dragons in front of Susie. <br></td>
    </tr>
    <tr>
      <td>748</td>
      <td>CLEANED_KRIS_ROOM_STAIN - Cleaned Kris's room stain -</td>
      <td>bool</td>
      <td>Cleaned up the stain with Susie in Kris's room. <br></td>
    </tr>
    <tr>
      <td>750</td>
      <td>TALKED_TO_BERDLY_AT_LIBRARBY - Talked to Berdly at the Librarby -</td>
      <td>bool</td>
      <td>Talked to Berdly at the Librarby. <br></td>
    </tr>
    <tr>
      <td>751</td>
      <td>DISCUSSED_PLANS_WITH_BERDLY_AT_LIBRARBY - Discussed study plans -</td>
      <td>bool</td>
      <td>Discussed plans with Berdly at the Librarby. <br></td>
    </tr>
    <tr>
      <td>752</td>
      <td>INTRODUCED_SUSIE_TO_RUDY_AFTER_CHURCH - Introduced Susie -</td>
      <td>bool</td>
      <td>Brought Susie to see Rudy at the hospital after church, if we didn't see him at the end of chapter 2 (flag 316). <br></td>
    </tr>
    <tr>
      <td>753</td>
      <td>BROUGHT_SUSIE_TO_RUDY_AFTER_CHURCH - Brought Susie to Rudy after church -</td>
      <td>bool</td>
      <td>Brought Susie to see Rudy at the hospital after church, if we did see him at the end of chapter 2 (flag 316). <br></td>
    </tr>
    <tr>
      <td>754</td>
      <td>USED_RUDY_SINK_CH4 - Used Rudy's sink -</td>
      <td>bool</td>
      <td>Interacted with Rudy's sink in chapter 4, after also doing it in chapter 1 (flag 278) and 2 (flag 461). <br></td>
    </tr>
    <tr>
      <td>755</td>
      <td>VISITED_BERDLY_IN_HOSPITAL_CH4 - Visited Berdly in the hospital -</td>
      <td>bool</td>
      <td>Visited Berdly's room at the hospital after church if his arm was injured in chapter 2. <br></td>
    </tr>
    <tr>
      <td>756</td>
      <td>CHANGED_BERDLY_HOSPITAL_WATER_BOTTLE - Changed Berdly's hospital water bottle -</td>
      <td>bool</td>
      <td>Changed Berdly's water bottle at the hospital during the Weird Route. <br></td>
    </tr>
    <tr>
      <td>757</td>
      <td>TURNED_UP_BERDLY_HOSPITAL_HEATER - Turned up Berdly's hospital heater -</td>
      <td>bool</td>
      <td>Turned up the space heater in Berdly's room at the hospital during the Weird Route. <br></td>
    </tr>
    <tr>
      <td>758</td>
      <td>SAW_SUSIE_POST_BERDLY_VISIT_SCENE - Saw Susie's post-Berdly hallway scene -</td>
      <td>bool</td>
      <td>Viewed the cutscene of Susie talking to Kris after exiting Berdly's hospital room if his arm was injured in chapter 2. <br></td>
    </tr>
    <tr>
      <td>759</td>
      <td>SUSIE_BERDLY_HOSPITAL_WEIRD_ROUTE_PROGRESS - Hallway visit state -</td>
      <td>map</td>
      <td>Tracks Susie talking before and after we enter Berdly's hospital room in the Weird Route. <br>0 = Default state<br>1 = Susie asked if Kris wants to go alone<br>2 = Susie talked to Kris after they come out<br></td>
    </tr>
    <tr>
      <td>760</td>
      <td>TALKED_TO_CATTY_IN_ALLEY - Talked to Catty in alley -</td>
      <td>bool</td>
      <td>Talked to Catty in the alley. <br></td>
    </tr>
    <tr>
      <td>761</td>
      <td>EAVESDROPPED_BLUE_BUNNY - Eavesdropped on bunny -</td>
      <td>bool</td>
      <td>Eavesdropped on Blue Bunny at the diner. <br></td>
    </tr>
    <tr>
      <td>762</td>
      <td>TALKED_TO_BRATTY_ABOUT_CATTY - Talked to Bratty about Catty -</td>
      <td>bool</td>
      <td>Talked to Bratty about Catty at the diner. <br></td>
    </tr>
    <tr>
      <td>763</td>
      <td>TALKED_TO_ALPHYS_CH4 - Talked to Alphys about milk -</td>
      <td>bool</td>
      <td>Talked to Alphys in Hometown in chapter 4, if we already talked to her in chapter 1 (flag 269). <br></td>
    </tr>
    <tr>
      <td>764</td>
      <td>ASKED_ALPHYS_TO_EXPLAIN_CH4 - Asked Alphys to explain -</td>
      <td>bool</td>
      <td>Talked to Alphys in Hometown in chapter 4 and asked her to explain herself, if we didn't talk to her in chapter 1 (flag 269). <br></td>
    </tr>
    <tr>
      <td>765</td>
      <td>SAW_SUSIE_SCARE_DOOR_KID_SCENE - Saw Susie scare the door kid -</td>
      <td>bool</td>
      <td>Viewed the cutscene of Susie scaring the kid behind one of the knockable doors. <br></td>
    </tr>
    <tr>
      <td>767</td>
      <td>TALKED_TO_CATTI_ABOUT_SUSIE_IN_HOMETOWN - Talked to Catti about Susie in Hometown -</td>
      <td>bool</td>
      <td>Talked to Catti about Susie in Hometown. <br></td>
    </tr>
    <tr>
      <td>768</td>
      <td>CHECKED_GERSON_GRAVE_WITH_SUSIE - Checked Gerson's grave with Susie -</td>
      <td>bool</td>
      <td>Interacted with Gerson's grave with Susie at the end of chapter 4. <br></td>
    </tr>
    <tr>
      <td>769</td>
      <td>CHECKED_SHELTER_WITH_SUSIE - Checked the shelter with Susie -</td>
      <td>bool</td>
      <td>Interacted with the Shelter with Susie at the end of chapter 4. <br></td>
    </tr>
    <tr>
      <td>770</td>
      <td>TRIED_TO_ENTER_SCHOOL_END_CH4 - Alphys's classroom -</td>
      <td>bool</td>
      <td>Tried to enter the school at the end of chapter 4. <br></td>
    </tr>
    <tr>
      <td>771</td>
      <td>LAKE_CUTSCENE_PROGRESS_CH4 - Beach scene -</td>
      <td>map</td>
      <td>Tracks the progress of the lake cutscene with Susie in chapter 4. <br>0 = Default state<br>1 = Susie remarks our weird friend is busy today<br>2 = Normal NPC when coming back<br>3 = Viewed the skipping stones cutscene<br></td>
    </tr>
    <tr>
      <td>773</td>
      <td>CHECKED_LAKE_TABLE_BEFORE_RAIN - Checked the lake table before the rain -</td>
      <td>bool</td>
      <td>Interacted with the table near the lake with Susie, before it started raining. <br></td>
    </tr>
    <tr>
      <td>774</td>
      <td>CHECKED_LAKE_TABLE_AFTER_RAIN - Checked the lake table after the rain -</td>
      <td>bool</td>
      <td>Interacted with the table near the lake with Susie, after it started raining. <br></td>
    </tr>
    <tr>
      <td>775</td>
      <td>CHECKED_BERDLY_DESK_WITH_EGGS - Checked Berdly's desk with the eggs -</td>
      <td>bool</td>
      <td>Interacted with Berdly's desk with the egg(s) on it in Alphys' class. <br></td>
    </tr>
    <tr>
      <td>776</td>
      <td>ASKED_BURGERPANTS_TO_CONTINUE - Asked burgerpants to continue -</td>
      <td>bool</td>
      <td>Picked 'Hear more' when talking to Burgerpants. <br></td>
    </tr>
    <tr>
      <td>777</td>
      <td>BURGERPANTS_DATE_PROGRESS - Date progress -</td>
      <td>map</td>
      <td>Tracks the progress of the Burgerpants date cutscene. <br>0 = Default state<br>1 = Burgerpants got cookies and left<br>2 = Talked to Nice Cream Guy<br></td>
    </tr>
    <tr>
      <td>778</td>
      <td>TORIEL_BLUSHING - Face draw cutscene -</td>
      <td>bool</td>
      <td>Whether Toriel is blushing. Used for the end of chapter 4. <br></td>
    </tr>
    <tr>
      <td>779</td>
      <td>TENNA_METTATON_GIFT_PROGRESS - Mettaton response -</td>
      <td>map</td>
      <td>Tracks the progress of giving Tenna to Mettaton. <br>0 = Default state<br>1 = Offered to give our TV<br>2 = Gave our TV<br></td>
    </tr>
    <tr>
      <td>780</td>
      <td>BROUGHT_TENNA_TO_SCHOOL - Brought Tenna to school -</td>
      <td>bool</td>
      <td>Brought Tenna to school. <br></td>
    </tr>
    <tr>
      <td>782</td>
      <td>USED_TREAT_CATCHER_WITH_SUSIE_AND_NOELLE - Used the Treat Catcher with Susie and Noelle -</td>
      <td>bool</td>
      <td>Interacted with the holiday treat catcher with Susie and Noelle at Noelle's house. <br></td>
    </tr>
    <tr>
      <td>783</td>
      <td>ORNAMENT_FINISHED_ROLLING - Ornament done -</td>
      <td>bool</td>
      <td>Whether the unused ornament in Noelle's house has finished rolling after falling. <br></td>
    </tr>
    <tr>
      <td>784</td>
      <td>NOELLE_FAN_ROTATING - Fan running -</td>
      <td>bool</td>
      <td>Whether the unused rotating fan in Noelle's house is rotating. <br></td>
    </tr>
    <tr>
      <td>785</td>
      <td>NOELLE_FAN_FRAME - Fan frame -</td>
      <td>number</td>
      <td>The current frame of the unused rotating fan in Noelle's house. <br></td>
    </tr>
    <tr>
      <td>786</td>
      <td>TALKED_TO_SANS_AT_GRILL - Talked to Sans at the grill -</td>
      <td>bool</td>
      <td>Talked to Sans in front of his grill in Hometown. <br></td>
    </tr>
    <tr>
      <td>787</td>
      <td>NOELLE_KITCHEN_PIANO_APPROACH_PROGRESS - Piano approach -</td>
      <td>map</td>
      <td>Tracks the progress of the cutscene of Kris walking to the piano in Noelle's kitchen. <br>0 = Default state<br>1 = Entered kitchen again after getting caught<br>2 = Kris walks to the left<br>3 = Kris walks down<br>4 = Kris walks to the right<br></td>
    </tr>
    <tr>
      <td>788</td>
      <td>SAW_LANCER_ROOM_RENOVATION_SCENE - Saw Lancer's renovated room -</td>
      <td>bool</td>
      <td>Viewed the cutscene about Lancer's room being renovated. <br></td>
    </tr>
    <tr>
      <td>789</td>
      <td>TALKED_TO_KING_ABOUT_KNIGHT - Talked to King about the Knight -</td>
      <td>bool</td>
      <td>Talked to King about the Knight. <br></td>
    </tr>
    <tr>
      <td>790</td>
      <td>SAW_TENNA_ENTERTAIN_KING_SCENE - Saw Tenna entertain King -</td>
      <td>bool</td>
      <td>Viewed the cutscene of Tenna entertaining King. <br></td>
    </tr>
    <tr>
      <td>791</td>
      <td>SAW_QUEEN_DRINKING_SCENE - Saw Queen drinking -</td>
      <td>bool</td>
      <td>Viewed the cutscene of Queen drinking in front of the giant speakers. <br></td>
    </tr>
    <tr>
      <td>792</td>
      <td>CASTLE_TOWN_ADDISON_LINEUP - Addison lineup -</td>
      <td>map</td>
      <td>Current lineup of the Addison booth in Castle Town. <br>0 = Lineup 1<br>1 = Lineup 2<br>2 = Lineup 3<br>3 = Lineup 4<br></td>
    </tr>
    <tr>
      <td>793</td>
      <td>SUSIE_CARRIED_LANCER - Had Susie carry Lancer -</td>
      <td>bool</td>
      <td>Whether Susie carried Lancer on her back in Castle Town. <br></td>
    </tr>
    <tr>
      <td>794</td>
      <td>RAIN_STATE - Rain effect state -</td>
      <td>map</td>
      <td>Activated when it's raining (mainly to control music and effects). <br>0 = Default state<br>1 = Chapter 4 ending (becomes state 2 after setting some parameters)<br>2 = Rain initialized (overrides other states)<br>3 = Used for certain room transitions (set back to 2 immediately if rain exists in the next room)<br></td>
    </tr>
    <tr>
      <td>795</td>
      <td>UNUSED_STAIRS_PROPHECY_COUNT - Legender prophecy seen -</td>
      <td>map</td>
      <td>How many of the two prophecies were seen in the two unused room_dw_church_stairs_topleft and room_dw_church_stairs_topright. <br>0 = Default state<br>1 = Saw one prophecy<br>2 = Saw both prophecies<br></td>
    </tr>
    <tr>
      <td>797</td>
      <td>CHECKED_SHELTER_PANEL - Checked the shelter panel -</td>
      <td>bool</td>
      <td>Checked the Shelter's panel. <br></td>
    </tr>
    <tr>
      <td>798</td>
      <td>SANS_SIGN_PROGRESS - Egg sign -</td>
      <td>map</td>
      <td>Tracks the progress of the Sans sign shenanigans. <br>0 = Default state<br>1 = Talked to Sans before checking the sign<br>2 = Checked Open sign<br>3 = Talked to Sans when sign says Open<br>4 = Went away and came back<br>5 = Talked to Sans when sign says Clopen<br>6 = Went away and came back<br>7 = Talked to Sans when sign is Sans<br></td>
    </tr>
    <tr>
      <td>799</td>
      <td>SAW_EGG_MAN_IN_DINER - Saw the Egg Man in the diner -</td>
      <td>bool</td>
      <td>Saw the Man in the diner, if you got the Egg in chapter 3. <br></td>
    </tr>
    <tr>
      <td>800</td>
      <td>CAFE_TOP_LEFT_RECRUIT - Top-left seat recruit -</td>
      <td>map</td>
      <td>The recruit seated in the top-left of the Cafe. Defaults to Jigsawry. <br>1 = Invalid (1)<br>5 = Rudinn<br>6 = Hathy<br>11 = Ponman<br>13 = Rabbick<br>14 = Bloxer<br>15 = Jigsawry<br>20 = JEVIL<br>22 = Rudinn Ranger<br>23 = Head Hathy<br>30 = Ambyu-Lance<br>31 = Poppup<br>32 = Tasque<br>33 = Werewire<br>34 = Maus<br>35 = Virovirokun<br>36 = Swatchling<br>40 = Werewerewire<br>42 = Tasque Manager<br>44 = Mauswheel<br>54 = Shadowguy<br>55 = Shuttah<br>56 = Zapper<br>57 = Ribbick<br>58 = Watercooler<br>59 = Pippins<br>60 = Elnina<br>61 = Lanino<br>62 = Guei<br>63 = Balthizard<br>64 = Bibliox<br>65 = Mizzle<br>66 = Wicabel<br>67 = Winglade<br>68 = Organikk<br>69 = Ms. Mizzle<br>70 = Floradinn<br>71 = Leafling<br>72 = Shi<br>73 = Shinobeetle<br>74 = KawKaw<br>75 = Sheary<br>76 = Netskie<br>77 = Terakota<br></td>
    </tr>
    <tr>
      <td>801</td>
      <td>CAFE_TOP_RIGHT_RECRUIT - Top-right seat recruit -</td>
      <td>map</td>
      <td>The recruit seated in the top-right of the Cafe. Defaults to Rudinn. <br>1 = Invalid (1)<br>5 = Rudinn<br>6 = Hathy<br>11 = Ponman<br>13 = Rabbick<br>14 = Bloxer<br>15 = Jigsawry<br>20 = JEVIL<br>22 = Rudinn Ranger<br>23 = Head Hathy<br>30 = Ambyu-Lance<br>31 = Poppup<br>32 = Tasque<br>33 = Werewire<br>34 = Maus<br>35 = Virovirokun<br>36 = Swatchling<br>40 = Werewerewire<br>42 = Tasque Manager<br>44 = Mauswheel<br>54 = Shadowguy<br>55 = Shuttah<br>56 = Zapper<br>57 = Ribbick<br>58 = Watercooler<br>59 = Pippins<br>60 = Elnina<br>61 = Lanino<br>62 = Guei<br>63 = Balthizard<br>64 = Bibliox<br>65 = Mizzle<br>66 = Wicabel<br>67 = Winglade<br>68 = Organikk<br>69 = Ms. Mizzle<br>70 = Floradinn<br>71 = Leafling<br>72 = Shi<br>73 = Shinobeetle<br>74 = KawKaw<br>75 = Sheary<br>76 = Netskie<br>77 = Terakota<br></td>
    </tr>
    <tr>
      <td>802</td>
      <td>CAFE_BOTTOM_LEFT_RECRUIT - Bottom-left seat recruit -</td>
      <td>map</td>
      <td>The recruit seated in the bottom-left of the Cafe. Defaults to Hathy. <br>1 = Invalid (1)<br>5 = Rudinn<br>6 = Hathy<br>11 = Ponman<br>13 = Rabbick<br>14 = Bloxer<br>15 = Jigsawry<br>20 = JEVIL<br>22 = Rudinn Ranger<br>23 = Head Hathy<br>30 = Ambyu-Lance<br>31 = Poppup<br>32 = Tasque<br>33 = Werewire<br>34 = Maus<br>35 = Virovirokun<br>36 = Swatchling<br>40 = Werewerewire<br>42 = Tasque Manager<br>44 = Mauswheel<br>54 = Shadowguy<br>55 = Shuttah<br>56 = Zapper<br>57 = Ribbick<br>58 = Watercooler<br>59 = Pippins<br>60 = Elnina<br>61 = Lanino<br>62 = Guei<br>63 = Balthizard<br>64 = Bibliox<br>65 = Mizzle<br>66 = Wicabel<br>67 = Winglade<br>68 = Organikk<br>69 = Ms. Mizzle<br>70 = Floradinn<br>71 = Leafling<br>72 = Shi<br>73 = Shinobeetle<br>74 = KawKaw<br>75 = Sheary<br>76 = Netskie<br>77 = Terakota<br></td>
    </tr>
    <tr>
      <td>803</td>
      <td>CAFE_BOTTOM_RIGHT_RECRUIT - Bottom-right seat recruit -</td>
      <td>map</td>
      <td>The recruit seated in the bottom-right of the Cafe. Defaults to Rudinn. <br>1 = Invalid (1)<br>5 = Rudinn<br>6 = Hathy<br>11 = Ponman<br>13 = Rabbick<br>14 = Bloxer<br>15 = Jigsawry<br>20 = JEVIL<br>22 = Rudinn Ranger<br>23 = Head Hathy<br>30 = Ambyu-Lance<br>31 = Poppup<br>32 = Tasque<br>33 = Werewire<br>34 = Maus<br>35 = Virovirokun<br>36 = Swatchling<br>40 = Werewerewire<br>42 = Tasque Manager<br>44 = Mauswheel<br>54 = Shadowguy<br>55 = Shuttah<br>56 = Zapper<br>57 = Ribbick<br>58 = Watercooler<br>59 = Pippins<br>60 = Elnina<br>61 = Lanino<br>62 = Guei<br>63 = Balthizard<br>64 = Bibliox<br>65 = Mizzle<br>66 = Wicabel<br>67 = Winglade<br>68 = Organikk<br>69 = Ms. Mizzle<br>70 = Floradinn<br>71 = Leafling<br>72 = Shi<br>73 = Shinobeetle<br>74 = KawKaw<br>75 = Sheary<br>76 = Netskie<br>77 = Terakota<br></td>
    </tr>
    <tr>
      <td>810</td>
      <td>COMPLETED_GRAZING - Completed the grazing challenge -</td>
      <td>bool</td>
      <td>Whether you beat the grazing challenge in the Party Dojo. <br></td>
    </tr>
    <tr>
      <td>811</td>
      <td>COMPLETED_DOJO_CLOVER - Completed the Clover dojo battle -</td>
      <td>bool</td>
      <td>Whether you beat Clover's rematch in the Party Dojo. <br></td>
    </tr>
    <tr>
      <td>812</td>
      <td>COMPLETED_TASQUE_MANAGER_SAYS - Completed Tasque Manager Says -</td>
      <td>bool</td>
      <td>Whether you beat the "Tasque Manager Says" challenge in the Party Dojo. <br></td>
    </tr>
    <tr>
      <td>813</td>
      <td>COMPLETED_ALLSTARS - Completed All Stars -</td>
      <td>bool</td>
      <td>Whether you beat the Ch2 All Stars challenge in the Party Dojo. <br></td>
    </tr>
    <tr>
      <td>814</td>
      <td>COMPLETED_JOE - Completed Joe's dojo battle -</td>
      <td>bool</td>
      <td>Whether you defeated Jigsaw Joe in the Party Dojo and took his life savings. <br></td>
    </tr>
    <tr>
      <td>815</td>
      <td>WEATHER_DUO_DOJO_OUTCOME - Lanino and Elnina -</td>
      <td>map</td>
      <td>Whether you defeated Lanino & Elnina in the chapter 4 Party/Love Dojo. <br>0 = Default state<br>2 = Won<br></td>
    </tr>
    <tr>
      <td>831</td>
      <td>HEARD_TORIEL_POST_CHURCH_INVITATION - Heard Toriel's post-church invitation -</td>
      <td>bool</td>
      <td>Viewed the cutscene of Toriel telling us to come by the church if we need anything. <br></td>
    </tr>
    <tr>
      <td>832</td>
      <td>TOOK_ASRIEL_DRAWER_MONEY_CH4 - Took Asriel's money -</td>
      <td>bool</td>
      <td>Whether you took five bucks from Asriel's drawer in chapter 4. <br></td>
    </tr>
    <tr>
      <td>833</td>
      <td>DINER_PAYMENT_REFUSED - Payment refused -</td>
      <td>bool</td>
      <td>Tried to get diner while not having the money for it. <br></td>
    </tr>
    <tr>
      <td>834</td>
      <td>SPLATTED_NEXT_TO_RALSEI - Splatted next to Ralsei -</td>
      <td>bool</td>
      <td>Showed compassion to Ralsei by splatting next to him in the church Dark World. <br></td>
    </tr>
    <tr>
      <td>835</td>
      <td>CHECKED_FIRST_SANCTUARY_PROPHECY_SAVE_POINT - Checked the First Sanctuary prophecy save point -</td>
      <td>bool</td>
      <td>Interacted with the save point under the prophecy panel at the start of the First Sanctuary. <br></td>
    </tr>
    <tr>
      <td>836</td>
      <td>TALKED_TO_GERSON_IN_STUDY - Talked to Gerson in his study -</td>
      <td>bool</td>
      <td>Talked to Gerson once he's installed in his study. <br></td>
    </tr>
    <tr>
      <td>837</td>
      <td>ASKED_GERSON_ABOUT_HIS_WORK_BEFORE_JACKENSTEIN - Asked Gerson about his work before Jackenstein -</td>
      <td>bool</td>
      <td>Asked Gerson in his study what he's doing, before healing Jackenstein. <br></td>
    </tr>
    <tr>
      <td>838</td>
      <td>ASKED_GERSON_ABOUT_KNIGHT_BEFORE_JACKENSTEIN - Asked Gerson about the Knight before Jackenstein -</td>
      <td>bool</td>
      <td>Asked Gerson in his study about the Knight, before healing Jackenstein. <br></td>
    </tr>
    <tr>
      <td>841</td>
      <td>UNUSED_HIDE_STUDY_ELIXIR - Study elixir state -</td>
      <td>map</td>
      <td>If activated, hides the elixir on the table of Gerson's study. Never set. <br>0 = Default state<br>2 = Hide elixir<br></td>
    </tr>
    <tr>
      <td>844</td>
      <td>SUSIE_COPIED_WALL_NOTES - Wall notes -</td>
      <td>bool</td>
      <td>Viewed the cutscene of Susie talking to Gerson and writing down the music notes on the wall. <br></td>
    </tr>
    <tr>
      <td>845</td>
      <td>THOUGHT_ABOUT_KNIGHT - Knight daydream rest -</td>
      <td>bool</td>
      <td>Viewed the cutscene of Kris thinking about the Knight. Unaccessed as of chapter 4. <br></td>
    </tr>
    <tr>
      <td>846</td>
      <td>THOUGHT_ABOUT_NOELLE_WEIRD_ROUTE - Drip vision rest -</td>
      <td>bool</td>
      <td>Viewed the cutscene of Kris thinking about Noelle in the Weird Route. Unaccessed as of chapter 4. <br></td>
    </tr>
    <tr>
      <td>847</td>
      <td>STUDY_SHEET_MUSIC_PROGRESS - Sheet music -</td>
      <td>map</td>
      <td>Tracks the progress of the cutscene of Kris playing the organ/piano and opening the central door in Gerson's study. <br>0 = Default state<br>1 = Used sheet music<br>2 = Kris played piano<br>3 = Unused (relies on unused flag 848)<br></td>
    </tr>
    <tr>
      <td>848</td>
      <td>UNUSED_ORGAN_FLAG - Organ shadow puzzle -</td>
      <td>number</td>
      <td>Set by unreachable code, might be related to a cut player-only solve. <br></td>
    </tr>
    <tr>
      <td>849</td>
      <td>SAW_JACKENSTEIN_TRUE_FACE - Saw Jackenstein's True face -</td>
      <td>bool</td>
      <td>Saw Jackenstein's True face after defeating him. Unaccessed as of chapter 4. <br></td>
    </tr>
    <tr>
      <td>850</td>
      <td>JACKENSTEIN_CUTSCENE_PROGRESS - Sheet music hunt -</td>
      <td>map</td>
      <td>Tracks the progress of the Jackenstein cutscenes. <br>0 = Default state<br>1 = Found both sets of four tones<br>2 = Solved piano puzzle<br>3 = Fell into THE DARK ZONE<br>4 = Jackenstein hit chandelier<br>5 = Susie healed Jackenstein<br>6 = Susie offered Kris to heal again<br>0.5 = Found one set of four tones<br></td>
    </tr>
    <tr>
      <td>851</td>
      <td>GERSON_CUTSCENE_PROGRESS - Tall bookcase -</td>
      <td>map</td>
      <td>Tracks the progress of the Gerson cutscenes. <br>0 = Default state<br>1 = Solved secret piano puzzle<br>2 = Fought Gerson<br>3 = Viewed post-battle cutscene<br></td>
    </tr>
    <tr>
      <td>852</td>
      <td>DEFEATED_HAMMER_OF_JUSTICE - Defeated -</td>
      <td>bool</td>
      <td>Whether you defeated the Hammer of Justice. <br></td>
    </tr>
    <tr>
      <td>853</td>
      <td>HAMMER_OF_JUSTICE_ATTEMPT_COUNT - Attempts -</td>
      <td>number</td>
      <td>Number of times you fought the Hammer of Justice. <br></td>
    </tr>
    <tr>
      <td>854</td>
      <td>RALSEI_DESIRES_RESPONSE - Ralsei room apology -</td>
      <td>map</td>
      <td>What you answered to Ralsei asking you if a Darkner should be starting to develop his own desires. Unaccessed as of chapter 4. <br>0 = Default state<br>1 = Please be yourself<br>2 = Of course not<br></td>
    </tr>
    <tr>
      <td>855</td>
      <td>TALKED_TO_SEAM_ABOUT_ADDISONS - Talked to Seam about the Addisons -</td>
      <td>bool</td>
      <td>Talked to Seam about taking everything from the Addisons to scare them. <br></td>
    </tr>
    <tr>
      <td>856</td>
      <td>GAVE_KNIGHT_SHADOW_CRYSTAL_TO_SEAM - Shadow Crystal -</td>
      <td>bool</td>
      <td>Whether you gave Seam the Knight's Shadow Crystal. <br></td>
    </tr>
    <tr>
      <td>862</td>
      <td>TALKED_TO_RUDY_ABOUT_ASGORE - Talked to Rudy about Asgore -</td>
      <td>bool</td>
      <td>Talked to Rudy about Asgore at church. <br></td>
    </tr>
    <tr>
      <td>863</td>
      <td>OBTAINED_SIDE_CLIMB_POWER_BAND - Got Power Band -</td>
      <td>bool</td>
      <td>Got the Power Band from the chest in the room with the Mizzle on top. <br></td>
    </tr>
    <tr>
      <td>864</td>
      <td>STOLE_LADDER_FOR_RALSEI - Stole the ladder for Ralsei -</td>
      <td>bool</td>
      <td>Stole the ladder in the bookshelf puzzle room to decorate Ralsei's room. <br></td>
    </tr>
    <tr>
      <td>865</td>
      <td>STOLE_PILLOW_FOR_RALSEI - Stole the cushion for Ralsei -</td>
      <td>bool</td>
      <td>Stole the pillow in the right piano piece room to decorate Ralsei's room. <br></td>
    </tr>
    <tr>
      <td>866</td>
      <td>TOLD_RALSEI_TO_SIT - Told Ralsei to sit -</td>
      <td>bool</td>
      <td>Told Ralsei to park his butt. <br></td>
    </tr>
    <tr>
      <td>867</td>
      <td>TALKED_TO_FIRE_EXTINGUISHER - Talked to the fire extinguisher -</td>
      <td>bool</td>
      <td>Talked to the most important Darkner. <br></td>
    </tr>
    <tr>
      <td>868</td>
      <td>GERSON_RECRUITED_GUEIS - Had Gerson recruit the Gueis -</td>
      <td>bool</td>
      <td>Whether Gerson recruited the Gueis. <br></td>
    </tr>
    <tr>
      <td>869</td>
      <td>SOLVED_INTRO_PIANO_PUZZLE - Solved the introductory piano puzzle -</td>
      <td>bool</td>
      <td>Solved the first piano puzzle. <br></td>
    </tr>
    <tr>
      <td>871</td>
      <td>OPENED_DARK_MAZE_CHEST - Opened the dark-maze chest -</td>
      <td>bool</td>
      <td>Opened the empty chest in the dark maze room. <br></td>
    </tr>
    <tr>
      <td>872</td>
      <td>DARKER_CANDY_BOWL_STATE - Darker Candy bowl -</td>
      <td>map</td>
      <td>Tracks what you did with the Darker Candy bowl. <br>0 = Default state<br>1 = Took one candy<br>3 = Spilled the bowl<br></td>
    </tr>
    <tr>
      <td>873</td>
      <td>CHECKED_LOCKED_CHURCH_DOOR - Locked door -</td>
      <td>bool</td>
      <td>Interacted with the locked church door before Susie got an idea. <br></td>
    </tr>
    <tr>
      <td>874</td>
      <td>TRIGGERED_GERSON_SILHOUETTE - Triggered Gerson's silhouette -</td>
      <td>bool</td>
      <td>Triggered the silhouette of Gerson walking away in the intro dark maze room. <br></td>
    </tr>
    <tr>
      <td>875</td>
      <td>RALSEI_SMILE_RESPONSE - Ralsei response -</td>
      <td>map</td>
      <td>What you told Ralsei after he told you he was smiling. <br>0 = Default state<br>1 = It's okay not to smile<br>2 = Good. Keep smiling<br></td>
    </tr>
    <tr>
      <td>876</td>
      <td>BOOKSHELF_PUZZLE_SHELF_1_X - Blue shelf X -</td>
      <td>number</td>
      <td>X coordinate of the first shelf in the bookshelf puzzle room. <br></td>
    </tr>
    <tr>
      <td>877</td>
      <td>BOOKSHELF_PUZZLE_SHELF_1_Y - Blue shelf Y -</td>
      <td>number</td>
      <td>Y coordinate of the first shelf in the bookshelf puzzle room. <br></td>
    </tr>
    <tr>
      <td>878</td>
      <td>BOOKSHELF_PUZZLE_SHELF_2_X - Red shelf X -</td>
      <td>number</td>
      <td>X coordinate of the second shelf in the bookshelf puzzle room. <br></td>
    </tr>
    <tr>
      <td>879</td>
      <td>BOOKSHELF_PUZZLE_SHELF_2_Y - Red shelf Y -</td>
      <td>number</td>
      <td>Y coordinate of the second shelf in the bookshelf puzzle room. <br></td>
    </tr>
    <tr>
      <td>880</td>
      <td>BOOKSHELF_PUZZLE_SHELF_3_X - Green shelf X -</td>
      <td>number</td>
      <td>X coordinate of the third shelf in the bookshelf puzzle room. <br></td>
    </tr>
    <tr>
      <td>881</td>
      <td>BOOKSHELF_PUZZLE_SHELF_3_Y - Green shelf Y -</td>
      <td>number</td>
      <td>Y coordinate of the third shelf in the bookshelf puzzle room. <br></td>
    </tr>
    <tr>
      <td>882</td>
      <td>RIGHT_PIANO_PIECE_SHELF_1_X - Shelf 1 X -</td>
      <td>number</td>
      <td>X coordinate of the first shelf in the right piano piece room. <br></td>
    </tr>
    <tr>
      <td>883</td>
      <td>RIGHT_PIANO_PIECE_SHELF_1_Y - Shelf 1 Y -</td>
      <td>number</td>
      <td>Y coordinate of the first shelf in the right piano piece room. <br></td>
    </tr>
    <tr>
      <td>884</td>
      <td>RIGHT_PIANO_PIECE_SHELF_2_X - Shelf 2 X -</td>
      <td>number</td>
      <td>X coordinate of the second shelf in the right piano piece room. <br></td>
    </tr>
    <tr>
      <td>885</td>
      <td>RIGHT_PIANO_PIECE_SHELF_2_Y - Shelf 2 Y -</td>
      <td>number</td>
      <td>Y coordinate of the second shelf in the right piano piece room. <br></td>
    </tr>
    <tr>
      <td>886</td>
      <td>PIANO_PUZZLE_RIGHT_HINT_STATE - Right melody -</td>
      <td>map</td>
      <td>Revealed the right piano hint for the piano puzzle. <br>0 = Default state<br>1 = Revealed hint<br>-1 = Solved piano puzzle<br></td>
    </tr>
    <tr>
      <td>887</td>
      <td>INTRO_PIANO_LEFT_HINT_REVEALED - Left hint -</td>
      <td>bool</td>
      <td>Revealed the left piano hint in the intro piano room. <br></td>
    </tr>
    <tr>
      <td>888</td>
      <td>INTRO_PIANO_RIGHT_HINT_REVEALED - Right hint -</td>
      <td>bool</td>
      <td>Revealed the right piano hint in the intro piano room. <br></td>
    </tr>
    <tr>
      <td>889</td>
      <td>DARK_MAZE_BOTTOM_HINT_REVEALED - Bottom hint -</td>
      <td>bool</td>
      <td>Revealed the bottom piano hint in the dark maze room. <br></td>
    </tr>
    <tr>
      <td>890</td>
      <td>DARK_MAZE_TOP_HINT_REVEALED - Top hint -</td>
      <td>bool</td>
      <td>Revealed the top piano hint in the dark maze room. <br></td>
    </tr>
    <tr>
      <td>891</td>
      <td>PIANO_PUZZLE_LEFT_HINT_STATE - Left melody -</td>
      <td>map</td>
      <td>Revealed the left piano hint for the piano puzzle. <br>0 = Default state<br>1 = Revealed hint<br>-1 = Solved piano puzzle<br></td>
    </tr>
    <tr>
      <td>892</td>
      <td>SOLVED_PIANO_PUZZLE - Solved -</td>
      <td>bool</td>
      <td>Solved the piano puzzle before Jackenstein. <br></td>
    </tr>
    <tr>
      <td>893</td>
      <td>PIANO_PUZZLE_WITHOUT_HINT_ATTEMPTS - No-hint attempts -</td>
      <td>map</td>
      <td>Tried to solve the piano puzzle without hint. <br>0 = Default state<br>1 = Interacted with piano once<br>1.1 = Interacted with piano more than once<br></td>
    </tr>
    <tr>
      <td>894</td>
      <td>OPENED_LEFT_PIANO_PIECE_CHEST - Opened the left piano-piece chest -</td>
      <td>bool</td>
      <td>Got the Scarlixir from the chest in the left piano piece room. <br></td>
    </tr>
    <tr>
      <td>895</td>
      <td>SUSIE_BASEMENT_DIALOGUE_LINE - Susie conversation -</td>
      <td>map</td>
      <td>Tracks the current line of Susie's dialogue alone in Noelle's basement during the Weird Route. <br>0 = Default state<br>1 = ... Damn, I've moved everything but I can't find anything...<br>2 = ... wonder how Kris's search is going.<br>3 = ... nothing to do but keep looking, I guess.<br></td>
    </tr>
    <tr>
      <td>897</td>
      <td>UNUSED_PIANO_HINT_PREVENTION_FLAG - Incomplete music dialogue -</td>
      <td>bool</td>
      <td>Flag never set, but would have prevented use of the piano after getting one of the two hints. <br></td>
    </tr>
    <tr>
      <td>898</td>
      <td>MONEY_FOUNTAIN_DONATION - Donation -</td>
      <td>number</td>
      <td>The amount of money you donated to the money fountain. <br></td>
    </tr>
    <tr>
      <td>899</td>
      <td>HOLY_WATERCOOLER_ENCOUNTER_OUTCOME - Holy Watercooler -</td>
      <td>map</td>
      <td>Tracks the state of the Holywatercooler encounter. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>900</td>
      <td>VESSEL_HEAD - Head -</td>
      <td>map</td>
      <td>The head of your vessel. <br>0 = Bald<br>1 = Kris-like<br>2 = Left lock<br>3 = Middle part<br>4 = Thick hair<br>5 = Loose<br>6 = Balding line<br>7 = Refined<br></td>
    </tr>
    <tr>
      <td>901</td>
      <td>VESSEL_BODY - Body -</td>
      <td>map</td>
      <td>The body of your vessel. <br>0 = Long sleeves<br>1 = Short sleeves<br>2 = Baggy sleeves<br>3 = Baggier sleeves<br>4 = Zipper<br>5 = Buttons<br></td>
    </tr>
    <tr>
      <td>902</td>
      <td>VESSEL_LEGS - Legs -</td>
      <td>map</td>
      <td>The legs of your vessel. <br>0 = Wider on right<br>1 = Wider on right<br>2 = Wider on right<br>3 = Wider on right<br>4 = Wider on left<br></td>
    </tr>
    <tr>
      <td>903</td>
      <td>VESSEL_FOOD - What is its favorite food? -</td>
      <td>map</td>
      <td>Your vessel's favorite food. <br>0 = Sweet<br>1 = Soft<br>2 = Sour<br>3 = Salty<br>4 = Pain<br>5 = Cold<br></td>
    </tr>
    <tr>
      <td>904</td>
      <td>VESSEL_BLOOD - Your favorite blood type? -</td>
      <td>map</td>
      <td>Your favorite blood type. <br>0 = A<br>1 = AB<br>2 = B<br>3 = C<br>4 = D<br></td>
    </tr>
    <tr>
      <td>905</td>
      <td>VESSEL_COLOR - What color does it like most? -</td>
      <td>map</td>
      <td>Your vessel's favorite color. <br>0 = Red<br>1 = Blue<br>2 = Green<br>3 = Cyan<br></td>
    </tr>
    <tr>
      <td>906</td>
      <td>VESSEL_FEELING - How do you feel about your creation? (It will not hear.) -</td>
      <td>map</td>
      <td>How you feel about your vessel. <br>0 = Love<br>1 = Hope<br>2 = Disgust<br>3 = Fear<br></td>
    </tr>
    <tr>
      <td>907</td>
      <td>VESSEL_HONEST - Have you answered honestly? -</td>
      <td>bool</td>
      <td>Were you honest about your vessel choices? <br></td>
    </tr>
    <tr>
      <td>908</td>
      <td>VESSEL_SEIZURE - You acknowledge the possibility of pain and seizure. -</td>
      <td>bool</td>
      <td>Do you acknowledge the possibility of pain and seizure? <br></td>
    </tr>
    <tr>
      <td>909</td>
      <td>VESSEL_GIFT - Please give it a gift -</td>
      <td>map</td>
      <td>The gift you give your vessel. Stored in reverse order. <br>0 = Mind<br>1 = Kindness<br>-3 = Voice<br>-2 = Bravery<br>-1 = Ambition<br></td>
    </tr>
    <tr>
      <td>910</td>
      <td>EGG_ROOM_PROGRESS_CH1 - Room progress -</td>
      <td>map</td>
      <td>Your progress to finding... him. <br>0 = Default state<br>1 = Entered room<br>2 = Interacted with man<br></td>
    </tr>
    <tr>
      <td>911</td>
      <td>OBTAINED_EGG_CH1 - Got the egg -</td>
      <td>bool</td>
      <td>Set when entering Chapter 2 if you had or deposited the Chapter 1 egg, but not if you dropped it. Maybe. It checks the key item. <br></td>
    </tr>
    <tr>
      <td>912</td>
      <td>LANGUAGE_NAME - Language -</td>
      <td>map</td>
      <td>Language your name was entered in, used to display the correct font even if you change the game language later. <br>0 = English<br>1 = Japanese<br></td>
    </tr>
    <tr>
      <td>913</td>
      <td>INTERACTED_WITH_MAN_CAR - Saw man in car -</td>
      <td>bool</td>
      <td>Whether you saw the man wave at you from his car, if flag 910 up there was 2 (even if you refused the offer). <br></td>
    </tr>
    <tr>
      <td>914</td>
      <td>STARTING_CHAPTER - Starting chapter -</td>
      <td>number</td>
      <td>The chapter you started your current save file on, is 0 if the file was created on the current chapter. <br></td>
    </tr>
    <tr>
      <td>915</td>
      <td>SNOWGRAVE_ROUTE_PROGRESS - Progress -</td>
      <td>map</td>
      <td>Your progress on the Snowgrave Route. This is a big one. <br>0 = Default state<br>1 = Froze tutor Virovirokun<br>2 = Ready for Freeze Ring<br>3 = Got Freeze Ring<br>4 = Passed forcefield<br>5 = Froze mouse puzzle<br>6 = SnowGrave.<br>7 = Entered mansion<br>8 = Rouxls's condition explained<br>9 = Did not see Suselle scene<br>19 = Seen Noelle with Rudy<br>20 = Creeped Noelle out<br>1.5 = Froze Trash Zone enemies<br>1.75 = Froze roadway enemies<br></td>
    </tr>
    <tr>
      <td>916</td>
      <td>SNOWGRAVE_FAIL - Failed -</td>
      <td>bool</td>
      <td>Whether you failed the Snowgrave Route at any point, by any action. Reverts practically every effect of the route. <br></td>
    </tr>
    <tr>
      <td>917</td>
      <td>EGG_ROOM_PROGRESS_CH2 - Room progress -</td>
      <td>map</td>
      <td>Your progress to finding him. Again. <br>0 = Default state<br>1 = Killed by dog<br>2 = Entered egg room<br>3 = Interacted with man<br></td>
    </tr>
    <tr>
      <td>918</td>
      <td>OBTAINED_EGG_CH2 - Got the egg -</td>
      <td>bool</td>
      <td>Whether you got the Chapter 2 egg, for Temmie's collection. <br></td>
    </tr>
    <tr>
      <td>919</td>
      <td>NOELLE_LEVEL_UP_COUNT - Times Noelle Leveled -</td>
      <td>number</td>
      <td>Like flag 65 but for Noelle in particular. Unaccessed. <br></td>
    </tr>
    <tr>
      <td>920</td>
      <td>OBTAINED_MOSS_CH2 - Got the moss -</td>
      <td>bool</td>
      <td>Whether you got the Moss in Chapter 2 and the Moss Finder title. <br></td>
    </tr>
    <tr>
      <td>921</td>
      <td>ATE_MOSS_WITH_NOELLE - Ate moss with Noelle -</td>
      <td>bool</td>
      <td>Whether Noelle was with you when you found the Moss, earning the Moss Neutral title. <br></td>
    </tr>
    <tr>
      <td>922</td>
      <td>ATE_MOSS_WITH_SUSIE - Ate moss with Susie -</td>
      <td>bool</td>
      <td>Whether Susie was with you when you found the Moss, earning the Moss Enjoyer title. <br></td>
    </tr>
    <tr>
      <td>923</td>
      <td>FAILED_SNOWGRAVE_WITHOUT_THORN_RING - Forgot Ring -</td>
      <td>bool</td>
      <td>Whether you failed the Snowgrave route because of not having the Thorn Ring at Berdly. Unaccessed. <br></td>
    </tr>
    <tr>
      <td>924</td>
      <td>SNOWGRAVE_KILL_COMMAND_COUNT - Snowgrave Attempts -</td>
      <td>number</td>
      <td>The number of times you told Noelle to KILL HIM, KILL HIM NOW. (0-4) <br></td>
    </tr>
    <tr>
      <td>925</td>
      <td>ICESHOCKS - IceShock uses -</td>
      <td>number</td>
      <td>The number of IceShocks Noelle has used, finishing or not. Each increases her Coldness by 7. <br></td>
    </tr>
    <tr>
      <td>926</td>
      <td>ICESHOCKED_ENCOUNTERS - Iceshocked Encounters -</td>
      <td>number</td>
      <td>The number of encounters defeated with IceShock. Unaccessed. <br></td>
    </tr>
    <tr>
      <td>928</td>
      <td>CREEPY_STEPS - Creepy Steps -</td>
      <td>number</td>
      <td>The number of steps you take toward Noelle (0-3) after the hospital scene on Snowgrave. Yeah, that's a thing. <br></td>
    </tr>
    <tr>
      <td>930</td>
      <td>OBTAINED_EGG_CH3 - Got the egg -</td>
      <td>bool</td>
      <td>Whether you got the Chapter 3 egg. <br></td>
    </tr>
    <tr>
      <td>931</td>
      <td>OBTAINED_EGG_CH4 - Got the egg -</td>
      <td>bool</td>
      <td>Whether you got the Chapter 4 egg. <br></td>
    </tr>
    <tr>
      <td>932</td>
      <td>DAMAGE_TAKEN_COUNT_CH1 - Damage taken -</td>
      <td>number</td>
      <td>Number of times hit in Chapter 1, used for trophies. <br></td>
    </tr>
    <tr>
      <td>933</td>
      <td>ICE_E_PAIN_SCALE_VIEW_COUNT_CH1 - Ice-E pain-scale views -</td>
      <td>number</td>
      <td>Number of times you looked at the ICE-E pain scale in Chapter 1, used for trophies. <br></td>
    </tr>
    <tr>
      <td>934</td>
      <td>DAMAGE_TAKEN_COUNT_CH2 - Damage taken -</td>
      <td>number</td>
      <td>Number of times hit in Chapter 2, used for trophies. <br></td>
    </tr>
    <tr>
      <td>935</td>
      <td>ICE_E_PAIN_SCALE_VIEW_COUNT_CH2 - Ice-E pain-scale views -</td>
      <td>number</td>
      <td>Number of times you looked at the ICE-E pain scale in Chapter 2, used for trophies. <br></td>
    </tr>
    <tr>
      <td>936</td>
      <td>DAMAGE_TAKEN_COUNT_CH3 - Damage taken -</td>
      <td>number</td>
      <td>Number of times hit in Chapter 3, used for trophies. <br></td>
    </tr>
    <tr>
      <td>937</td>
      <td>DAMAGE_TAKEN_COUNT_CH4 - Damage taken -</td>
      <td>number</td>
      <td>Number of times hit in Chapter 4, used for trophies. <br></td>
    </tr>
    <tr>
      <td>938</td>
      <td>ICE_E_PAIN_SCALE_VIEW_COUNT_CH4 - Ice-E pain-scale views -</td>
      <td>number</td>
      <td>Number of times you looked at the ICE-E pain scale in Chapter 4, used for trophies. <br></td>
    </tr>
    <tr>
      <td>939</td>
      <td>TREASURE_CHEST_COUNT - Amount Treasure -</td>
      <td>number</td>
      <td>Number of chests opened, used for trophies. <br></td>
    </tr>
    <tr>
      <td>950</td>
      <td>SHADOW_FAILED_CH2 - Shadow failed -</td>
      <td>bool</td>
      <td>Whether you used the Shadow Crystal in Chapter 2 and saw nothing. 952 is more interesting. <br></td>
    </tr>
    <tr>
      <td>951</td>
      <td>GLASS_FAILED_CH2 - Glass failed -</td>
      <td>bool</td>
      <td>Whether you used the Glass in Chapter 2 and saw nothing. 953 and 281 are more interesting. <br></td>
    </tr>
    <tr>
      <td>952</td>
      <td>SHADOW_LAB - Shadow Lab -</td>
      <td>bool</td>
      <td>Whether you saw the computer lab using the Shadow Crystal. <br></td>
    </tr>
    <tr>
      <td>953</td>
      <td>GLASS_SUSIE_GLARE - Glass Susie Glare -</td>
      <td>bool</td>
      <td>Whether you saw Susie glare at you using the Glass. <br></td>
    </tr>
    <tr>
      <td>954</td>
      <td>GAVE_JEVIL_CRYSTAL - Jevil Crystal -</td>
      <td>bool</td>
      <td>Whether you gave Seam JEVIL's Shadow Crystal. <br></td>
    </tr>
    <tr>
      <td>961</td>
      <td>FAILED_SPAM_CRYSTAL - Failed Spam Crystal -</td>
      <td>bool</td>
      <td>Whether you got JEVIL's Shadow Crystal but failed to find Spamton's, and told Seam. They seem quite dejected... <br></td>
    </tr>
    <tr>
      <td>1001</td>
      <td>TINY_PYRAMID_STATE - Tiny pyramid puzzle -</td>
      <td>map</td>
      <td>Progress finding the even tinier pyramid in Desert Board. Resets to 0 if you enter Rouxls's shop. <br>0 = Default state<br>1 = Tiny pyramid mentioned<br>2 = Rouxls evicted<br>3 = Locked out<br></td>
    </tr>
    <tr>
      <td>1002</td>
      <td>FOUGHT_SHADOWMANTLE - Started the Shadow Mantle fight -</td>
      <td>bool</td>
      <td>Whether you've started the Shadow Mantle fight. Speeds up repeat fights, as your death isn't a real Game Over and doesn't reload a save. <br></td>
    </tr>
    <tr>
      <td>1003</td>
      <td>BOARD_LOSSES - Tenna show game overs -</td>
      <td>number</td>
      <td>Number of Game Overs attained in Tenna's show. <br></td>
    </tr>
    <tr>
      <td>1004</td>
      <td>OBTAINED_CROWD_TREASURE - Got the maze-crowd treasure -</td>
      <td>bool</td>
      <td>Whether you opened the chest in the lower-left corner of that maze with Zapper+Shuttah fights. <br></td>
    </tr>
    <tr>
      <td>1005</td>
      <td>FOUND_MAZE_CROWD - Found the maze crowd -</td>
      <td>bool</td>
      <td>Whether you triggered the cheering crowd in the upper-right corner of that maze with Zapper+Shuttah fights. <br></td>
    </tr>
    <tr>
      <td>1006</td>
      <td>FOREST_CUT_PROGRESS - Forest cut room count -</td>
      <td>number</td>
      <td>Number of repeating forest rooms passed through looking for the Ice Key. <br></td>
    </tr>
    <tr>
      <td>1007</td>
      <td>SWORDROUTE_EVICT - Kicked from original game -</td>
      <td>bool</td>
      <td>Whether you've (recently) done something to get yourself kicked out of the original game. Like dying. <br></td>
    </tr>
    <tr>
      <td>1008</td>
      <td>FOUND_SHADOWTEASE - Found shadow teaser message -</td>
      <td>bool</td>
      <td>Whether you found the "See you soon" hidden message in the Sword Route. <br></td>
    </tr>
    <tr>
      <td>1009</td>
      <td>SHADOWTEASE_EYES - Shadow teaser eyes -</td>
      <td>bool</td>
      <td>Whether you saw the teaser eyes on the side of the pyramid in Sword Board 1. <br></td>
    </tr>
    <tr>
      <td>1010</td>
      <td>SHADOWTEASE_GRIN - Shadow teaser grin -</td>
      <td>bool</td>
      <td>Whether you saw the teaser grin on the side of the pyramid in Sword Board 1. <br></td>
    </tr>
    <tr>
      <td>1011</td>
      <td>GAMESHOW_BATTLES - Gameshow battles entered -</td>
      <td>number</td>
      <td>Number of battles entered on Tenna's show? Unaccessed, but there's an empty code block here. <br></td>
    </tr>
    <tr>
      <td>1012</td>
      <td>GAMESHOW_NAME_1 - Letter 1 -</td>
      <td>map</td>
      <td>First letter selected for Kris's name on the game show. <br>Every number corresponds to a lettter. <br> 0 = A,<br> 1 = B,<br> 2 = C, etc.</td>
    </tr>
    <tr>
      <td>1013</td>
      <td>GAMESHOW_NAME_2 - Letter 2 -</td>
      <td>map</td>
      <td>Second letter selected for Kris's name on the game show. <br>Every number corresponds to a lettter. <br> 0 = A,<br> 1 = B,<br> 2 = C, etc.</td>
    </tr>
    <tr>
      <td>1014</td>
      <td>GAMESHOW_NAME_3 - Letter 3 -</td>
      <td>map</td>
      <td>Third letter selected for Kris's name on the game show. <br>Every number corresponds to a lettter. <br> 0 = A,<br> 1 = B,<br> 2 = C, etc.</td>
    </tr>
    <tr>
      <td>1017</td>
      <td>FAVORITE_WEATHER_ATTACK - Favorite weather attack -</td>
      <td>map</td>
      <td>Whose attack you liked better, causing the Weather to not Stick Together. <br>0 = Elnina<br>1 = Lanino<br></td>
    </tr>
    <tr>
      <td>1018</td>
      <td>SAW_NOWHERE_PREREQUISITE_BOARD - Saw the Nowhere prerequisite board -</td>
      <td>bool</td>
      <td>Whether you saw the board that's a prerequisite for solving Nowhere. Unaccessed. <br></td>
    </tr>
    <tr>
      <td>1019</td>
      <td>QUIZ_RIGHT_ANSWERS - Quiz correct answers -</td>
      <td>number</td>
      <td>Number of correct answers (totalled on all characters) in the most recent of Tenna's quizzes. Slightly alters the Tenna-sphinx dialogue. <br></td>
    </tr>
    <tr>
      <td>1020</td>
      <td>OBTAINED_POWER_CROISSANT - Got the Power Croissant for Susie -</td>
      <td>bool</td>
      <td>Whether Susie has obtained the Power Croissant, allowing her to pick up boxes, pots, weeds, and Ralsei. <br></td>
    </tr>
    <tr>
      <td>1021</td>
      <td>COUCH_WALKAWAY_CH3 - Walked away -</td>
      <td>bool</td>
      <td>Whether the couch has begun walking away (if you go right then go back to it) at the start of Chapter 3. <br></td>
    </tr>
    <tr>
      <td>1022</td>
      <td>TENNA_BOARD_ABSENT - Tenna left board -</td>
      <td>bool</td>
      <td>Whether Tenna has left the current board, allowing for additional board interactions. <br></td>
    </tr>
    <tr>
      <td>1023</td>
      <td>CANT_GRAB_RALSEI - Cannot grab Ralsei -</td>
      <td>bool</td>
      <td>Prevents Susie from picking up Ralsei in Tenna's minigames. <br></td>
    </tr>
    <tr>
      <td>1024</td>
      <td>BOARD_TRANSITION_FREEZE - Board transition freeze -</td>
      <td>bool</td>
      <td>Volatile value used to freeze characters on Chapter 3 minigame transitions. <br></td>
    </tr>
    <tr>
      <td>1025</td>
      <td>UNUSED_BOARD_KEY_COUNT - Board key tracker -</td>
      <td>number</td>
      <td>Board 1 key count. Unaccessed. See flag 1122 instead. Also incremented if you buy the useless board 2 key. <br></td>
    </tr>
    <tr>
      <td>1027</td>
      <td>DROPPED_S_RANK_ROOM_STAR - S-rank star fallen -</td>
      <td>bool</td>
      <td>Whether you interacted with the stars in the S-Rank room, causing one of them to fall on the floor. <br></td>
    </tr>
    <tr>
      <td>1028</td>
      <td>OBTAINED_RAMB_BOARD_REWARD_1 - Ramb reward -</td>
      <td>map</td>
      <td>Whether you got the first board reward from Ramb (if available based on rank). <br>0 = Default state<br>1 = Got prize<br>2 = Got nothing (Z-Rank)<br></td>
    </tr>
    <tr>
      <td>1029</td>
      <td>RAMB_BACKSTAGE_DIALOGUE_PROGRESS - Ramb backstage talk -</td>
      <td>map</td>
      <td>How much you've talked with Ramb backstage. <br>0 = Default state<br>1 = Ramb moved away from the door the first time<br>2 =&nbsp;&nbsp;"I'm glad you"re having REAL fun, Kris. (moves for the second time)" <br>3 = Talked round 3 (unused?)<br></td>
    </tr>
    <tr>
      <td>1030</td>
      <td>OBTAINED_RAMB_BOARD_REWARD_2 - Ramb reward -</td>
      <td>map</td>
      <td>Whether you got the second board reward from Ramb (if available based on rank). <br>0 = Default state<br>1 = Got prize<br>2 = Got nothing (Z-Rank)<br></td>
    </tr>
    <tr>
      <td>1031</td>
      <td>ENTERED_CHANGING_ROOM - Entered rank room -</td>
      <td>bool</td>
      <td>Whether you've interacted to enter the S- or Z-Rank room. Stops Susie's and Ralsei's dialogue on repeat. <br></td>
    </tr>
    <tr>
      <td>1032</td>
      <td>TALKED_TO_RAMB - Talked to Ramb first -</td>
      <td>bool</td>
      <td>Whether you've talked to Ramb at least once in the Green Room. Alters repeat interaction. <br></td>
    </tr>
    <tr>
      <td>1033</td>
      <td>TRIED_RACING - Tried racing game -</td>
      <td>bool</td>
      <td>Whether you've interacted with the TV with the racing game at least once. Alters repeat interaction. <br></td>
    </tr>
    <tr>
      <td>1034</td>
      <td>PLAYED_RACING_COUNT - Racing game plays -</td>
      <td>number</td>
      <td>Number of times you played the unseeable racing game. <br></td>
    </tr>
    <tr>
      <td>1035</td>
      <td>WON_RACING - Won racing game -</td>
      <td>bool</td>
      <td>Whether you won the racing game. Susie refuses to play any more afterward. <br></td>
    </tr>
    <tr>
      <td>1037</td>
      <td>RAL_CHEER_EQUIP_COUNT - Ralsei cheer equips -</td>
      <td>number</td>
      <td>Number of times you've equipped the Blue Ribbon to Ralsei, giving progress of a cheer chant. <br></td>
    </tr>
    <tr>
      <td>1038</td>
      <td>PIPIS_SOUNDS - Pipis inventory sounds -</td>
      <td>map</td>
      <td>Status of the Pipis in your inventory. Increases over time. <br>0 = Default state<br>1 = Chirping<br>2 = Clucking<br></td>
    </tr>
    <tr>
      <td>1039</td>
      <td>TENNA_PIPIS_STATE - Tenna Pipis bonus state -</td>
      <td>map</td>
      <td>State of Tenna's Pipis in the Bonus Zone (without Spamton). <br>0 = Default state<br>1 = Tenna panicked<br>2 = Got Pipis<br></td>
    </tr>
    <tr>
      <td>1040</td>
      <td>OBTAINED_HERO_PHOTO - Got the hero photo -</td>
      <td>bool</td>
      <td>Whether you've photographed the three heroes for Shuttah. The same flag is reused in some scrapped content. <br></td>
    </tr>
    <tr>
      <td>1041</td>
      <td>OBTAINED_HALF_FLOWER - Got the half-flower photo -</td>
      <td>bool</td>
      <td>Whether you've photographed the half flower in Board 2. <br></td>
    </tr>
    <tr>
      <td>1042</td>
      <td>OBTAINED_SPRING_PHOTO - Got the spring photo -</td>
      <td>bool</td>
      <td>Whether you've photographed the healing green spring in Board 2. <br></td>
    </tr>
    <tr>
      <td>1043</td>
      <td>OBTAINED_CACTUS_PHOTO - Got the cactus photo -</td>
      <td>bool</td>
      <td>Whether you've photographed the only cactus in Board 2. <br></td>
    </tr>
    <tr>
      <td>1044</td>
      <td>POINTS_CH3 - Points -</td>
      <td>number</td>
      <td>Your point total in Chapter 3. <br></td>
    </tr>
    <tr>
      <td>1045</td>
      <td>SUSIE_HEAL_PRACTICE_COUNT - Healing practice -</td>
      <td>number</td>
      <td>The number of times you have used UltraHeal/OKHeal/BetterHeal. Improves the spell. Caps at 5 in Chapter 3, 15 in Chapter 4. <br></td>
    </tr>
    <tr>
      <td>1047</td>
      <td>KNIGHT_BATTLE_OUTCOME_CH3 - Outcome -</td>
      <td>map</td>
      <td>Whether you beat the Knight... down to 80% of its health. Also saved to ini. <br>0 = Default state<br>1 = Won<br>2 = Lost<br></td>
    </tr>
    <tr>
      <td>1048</td>
      <td>LANCER_COST - Lancer purchase cost -</td>
      <td>map</td>
      <td>Amount spent on Lancer in Board 2. Decreases if he is photographed before purchase. <br>0 = Uninitialized<br>9 = 9 points<br>99 = 99 points<br>999 = 999 points<br></td>
    </tr>
    <tr>
      <td>1049</td>
      <td>BOARD_1_BATTLES - Board 1 Battles Count -</td>
      <td>number</td>
      <td>Number of battles engaged in on Board 1. <br></td>
    </tr>
    <tr>
      <td>1050</td>
      <td>DEFEATED_MANTLE - Defeated -</td>
      <td>bool</td>
      <td>Whether the Shadow Mantle boss was defeated. <br></td>
    </tr>
    <tr>
      <td>1051</td>
      <td>ADMITTED_CHEAT_COUNT - Cheater admits count -</td>
      <td>number</td>
      <td>Number of times you admitted to Zappers that you're a cheater, usually triggering a battle. <br></td>
    </tr>
    <tr>
      <td>1052</td>
      <td>TENNA_DELETED_GRASS - Tenna deleted grass -</td>
      <td>bool</td>
      <td>Whether Tenna deleted the grass to keep Susie from wasting time on it in the unused Board 3. <br></td>
    </tr>
    <tr>
      <td>1054</td>
      <td>TENNA_VOICE_PITCH - Tenna voice pitch -</td>
      <td>map</td>
      <td>Appears to be a volatile factor applied to Tenna's voice bite. Only used for his flashback. <br>0 = Uninitialized<br>1 = Full pitch<br>0.8 = 80% pitch<br></td>
    </tr>
    <tr>
      <td>1055</td>
      <td>SWORD_ROUTE_PROGRESS - Progress -</td>
      <td>map</td>
      <td>Progress on the Sword Route, the Chapter 3 side quest for the Shadow Mantle. <br>0 = Not started<br>1 = Got Ice Key<br>2 = She was used up.<br>3 = Got Shelter Key<br>4 = Entered red dungeon<br>5 = Entered shelter<br>6 = Defeated boss<br>1.5 = Entered Ice Palace<br></td>
    </tr>
    <tr>
      <td>1056</td>
      <td>KRIS_TENNA_CHAT - Kris talked with Tenna -</td>
      <td>bool</td>
      <td>Whether Tenna tried to justify himself to Kris between rounds. <br></td>
    </tr>
    <tr>
      <td>1057</td>
      <td>UNUSED_BACKSTAGE_SEQUENCE - Backstage sequence -</td>
      <td>number</td>
      <td>Unused tracker for a scrapped backstage sequence in Chapter 3. <br></td>
    </tr>
    <tr>
      <td>1058</td>
      <td>FOUND_ISLAND_TENNA - Found Tropic Tenna -</td>
      <td>bool</td>
      <td>Whether you found Tenna at the Tropic of Love on the original game, and heard his musings. <br></td>
    </tr>
    <tr>
      <td>1059</td>
      <td>ROUXLS_RULES_CARD_ENCOUNTER_OUTCOME - Rouxls battle -</td>
      <td>map</td>
      <td>Battle status of the Rouxls Kaard Rules Card battle. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1060</td>
      <td>OBTAINED_UNUSED_ELNINA_CONTROLLER - Got the Elnina controller -</td>
      <td>bool</td>
      <td>Whether you got the Elnina Controller for an unused game. The item ID got repurposed as the Odd Controller. <br></td>
    </tr>
    <tr>
      <td>1061</td>
      <td>SHADOWGUNNER_PHOTOS - Shadowmen photo count -</td>
      <td>number</td>
      <td>Number of photos taken of the Shadowmen shooting at you from trees. They have bunny ears after 5. <br></td>
    </tr>
    <tr>
      <td>1062</td>
      <td>OBTAINED_CURTAIN_SABER10 - Got the Curtain Saber -</td>
      <td>bool</td>
      <td>Whether you got the Saber10 from the quiet person behind the S-Rank curtain. <br></td>
    </tr>
    <tr>
      <td>1066</td>
      <td>HEARD_RAMB_FOUNTAIN_EXPLANATION - Heard Ramb explain the fountain -</td>
      <td>bool</td>
      <td>Whether Ramb explained (after Board 3) that he saw Kris make the fountain. <br></td>
    </tr>
    <tr>
      <td>1067</td>
      <td>OBTAINED_SHADOWMANTLE - Got Shadow Mantle -</td>
      <td>bool</td>
      <td>Whether you've opened the chest containing the Shadow Mantle. <br></td>
    </tr>
    <tr>
      <td>1068</td>
      <td>TALKED_TO_LANCER_IN_GREEN_ROOM - Talked to Lancer in the Green Room -</td>
      <td>bool</td>
      <td>Whether you've talked to Lancer in the Green Room (and he phased through the door). <br></td>
    </tr>
    <tr>
      <td>1071</td>
      <td>COUCH_SKIP_CH3 - Skipped intro -</td>
      <td>bool</td>
      <td>Whether you used the couch to skip to Board 1 in Chapter 3. <br></td>
    </tr>
    <tr>
      <td>1073</td>
      <td>LANCER_TV_NAME - Lancer Quiz Name -</td>
      <td>map</td>
      <td>What you (and Ralsei) named Lancer in Tenna's quiz. <br>0 = Lancer<br>1 = Dancer<br>2 = Prancer<br>3 = Mr. Generosity<br></td>
    </tr>
    <tr>
      <td>1074</td>
      <td>OBTAINED_IN_S_RANK_1 - Got first S-Rank access -</td>
      <td>bool</td>
      <td>Whether you've talked to the Zapper guarding the S-Rank room and gotten in for board 1. <br></td>
    </tr>
    <tr>
      <td>1075</td>
      <td>OBTAINED_IN_S_RANK_2 - Got second S-Rank access -</td>
      <td>bool</td>
      <td>Whether you've talked to the Zapper guarding the S-Rank room and gotten in for board 2. <br></td>
    </tr>
    <tr>
      <td>1076</td>
      <td>COUNTERFEIT_S_1 - Counterfeit Rank 1 -</td>
      <td>map</td>
      <td>Buying the counterfeit S-Rank for Board 1. <br>0 = Default state<br>1 = Have counterfeit<br>2 = Reset<br></td>
    </tr>
    <tr>
      <td>1077</td>
      <td>COUNTERFEIT_S_2 - Counterfeit Rank 2 -</td>
      <td>map</td>
      <td>Buying the counterfeit S-Rank for Board 2. <br>0 = Default state<br>1 = Have counterfeit<br>2 = Reset<br></td>
    </tr>
    <tr>
      <td>1078</td>
      <td>OBTAINED_MOSS_CH3 - Got moss -</td>
      <td>bool</td>
      <td>Whether you got the Moss in Chapter 3 and the Moss Mystery title. <br></td>
    </tr>
    <tr>
      <td>1079</td>
      <td>DRANK_OASIS - Drank the oasis dry -</td>
      <td>bool</td>
      <td>Whether you chose to deplete the oasis by drinking it. Dries up all the trees. <br></td>
    </tr>
    <tr>
      <td>1080</td>
      <td>SUSIEZILLA_LOSS_COUNT - Susiezilla losses -</td>
      <td>number</td>
      <td>Times lost at Suziezilla, up to 8. <br></td>
    </tr>
    <tr>
      <td>1081</td>
      <td>SUSIEZILLA_RESULT - Susiezilla result -</td>
      <td>map</td>
      <td>Exactly how much you won at Suziezilla. <br>0 = Default state<br>1 = Destroyed by Spamton's big shot without ever hitting him<br>2 = Declared win by Tenna<br>3 = Defeated final wave<br></td>
    </tr>
    <tr>
      <td>1083</td>
      <td>OBTAINED_LANCER_NAME_Q - Saw the Lancer-name question -</td>
      <td>bool</td>
      <td>Whether you've faced the question of Tenna forgetting Lancer's name. Unaccessed. <br></td>
    </tr>
    <tr>
      <td>1084</td>
      <td>RAMB_GAME_OPINION - Ramb game response -</td>
      <td>map</td>
      <td>Your choice to Ramb of whether you're enjoying Tenna's game. <br>0 = Default state<br>1 = Super fun<br>2 = Eh<br></td>
    </tr>
    <tr>
      <td>1085</td>
      <td>UNUSED_BOARD_PUZZLE_STARTED - Puzzle Started -</td>
      <td>bool</td>
      <td>Set when you enter an unused Chapter 3 room with a board puzzle. <br></td>
    </tr>
    <tr>
      <td>1086</td>
      <td>DEFEATED_DOOM_SHADOWMAN - Beat Doom Shadowman -</td>
      <td>bool</td>
      <td>Whether you've defeated the Shadowman on the Doom Board, to prompt the Zapper encounter instead. <br></td>
    </tr>
    <tr>
      <td>1087</td>
      <td>ENTERED_ICE_PALACE - Entered Ice Palace -</td>
      <td>bool</td>
      <td>Set upon entering the Ice Palace on Sword Board 2 as a checkpoint. <br></td>
    </tr>
    <tr>
      <td>1088</td>
      <td>CHEATED_DICE_VAL - Cheated dice value -</td>
      <td>map</td>
      <td>Number on the die in the unused room where a Pippins challenges you to roll even. <br>0 = Uninitialized<br>1 = 1<br>2 = 2<br>3 = 3<br>4 = 4<br>5 = 5<br>6 = 6<br></td>
    </tr>
    <tr>
      <td>1089</td>
      <td>COOKING_LOSSES_COUNT - Cooking losses -</td>
      <td>number</td>
      <td>Times lost at the cooking game. <br></td>
    </tr>
    <tr>
      <td>1090</td>
      <td>PARENT_LOCK_1_SCENE - Parent Lock 1 Intro -</td>
      <td>bool</td>
      <td>Whether you've completed specifically the introductory scene activating the puzzle for Parental Lock 1. <br></td>
    </tr>
    <tr>
      <td>1091</td>
      <td>SUSIE_NOTICE_SWORD - Susie noticed sword -</td>
      <td>map</td>
      <td>Status of Susie noticing Kris has a sword in the minigame if the OddController was obtained. <br>0 = Default state<br>1 = Sword used<br>2 = Susie commented<br></td>
    </tr>
    <tr>
      <td>1092</td>
      <td>BIBLIOX_QUEST_PROGRESS_CH3 - Bibliox quest -</td>
      <td>map</td>
      <td>Progress obtaining the TripTicket to Nowhere from the Bibliox. <br>0 = Default state<br>1 = Wardrobe mentioned<br>2 = Wardrobe appeared<br>3 = Wardrobe checked<br>4 = Got TripTicket<br>5 = Got post-Mantle hint<br>6 = Got alternate TripTicket<br></td>
    </tr>
    <tr>
      <td>1093</td>
      <td>JAILED_CHEATER - Cheater jailed -</td>
      <td>bool</td>
      <td>Whether you confessed to the Zapper that you are cheaters, and went into the highly escapable prison. <br></td>
    </tr>
    <tr>
      <td>1094</td>
      <td>PARENT_LOCK_1 - Parental Lock 1 Solved -</td>
      <td>bool</td>
      <td>Whether you solved the first parental lock in Chapter 3. <br></td>
    </tr>
    <tr>
      <td>1095</td>
      <td>PARENT_LOCK_2 - Parental Lock 2 Solved -</td>
      <td>bool</td>
      <td>Whether you solved the second parental lock in Chapter 3. <br></td>
    </tr>
    <tr>
      <td>1096</td>
      <td>RHYTHM_GAME_LOSSES - Rhythm game failures -</td>
      <td>number</td>
      <td>Total number of losses on the rock band game. <br></td>
    </tr>
    <tr>
      <td>1097</td>
      <td>UNUSED_ID_CARD_PUZZLE_FOUND - ID card puzzle found -</td>
      <td>bool</td>
      <td>Whether you found the water interaction in the unused ID card puzzle. <br></td>
    </tr>
    <tr>
      <td>1098</td>
      <td>CHEATER_PIP_LEFT - Cheater Pippins fled -</td>
      <td>bool</td>
      <td>Whether the unused dice-cheating Pippins have fled from being photographed. <br></td>
    </tr>
    <tr>
      <td>1099</td>
      <td>LANCER_CONTROL_NUM - Lancer controllers -</td>
      <td>number</td>
      <td>Number of Lancer Controllers obtained. <br></td>
    </tr>
    <tr>
      <td>1100</td>
      <td>OBTAINED_COOL_TRASHY_REWARD - Got Cool Trashy's reward -</td>
      <td>bool</td>
      <td>Whether you got Trashy's DeluxeDinner. <br></td>
    </tr>
    <tr>
      <td>1101</td>
      <td>POINT_CHEST_STATE - Found -</td>
      <td>map</td>
      <td>Progress with the 10-point chest in the dust pile at the start of Chapter 3. <br>0 = Default state<br>1 = Found chest<br>2 = Got points<br></td>
    </tr>
    <tr>
      <td>1102</td>
      <td>ZAPPER_SNEEZED - Zapper sneezed -</td>
      <td>bool</td>
      <td>Whether a Zapper left of the Chapter 3 starting area gave itself away by sneezing. <br></td>
    </tr>
    <tr>
      <td>1103</td>
      <td>ICE_KEY_FAIL - Ice key missing -</td>
      <td>bool</td>
      <td>Whether you reached the Ice Palace with no key, thus forgetting something important. <br></td>
    </tr>
    <tr>
      <td>1104</td>
      <td>OBTAINED_CUT_RIBBICK_ITEM - Got the cut Ribbick item -</td>
      <td>bool</td>
      <td>Set for a Ribbick trigger in an unused room. <br></td>
    </tr>
    <tr>
      <td>1105</td>
      <td>CUT_RIBBICK_FIGHTS - Cut Ribbick fights -</td>
      <td>number</td>
      <td>Counts up with a Ribbick trigger in an unused room. <br></td>
    </tr>
    <tr>
      <td>1106</td>
      <td>DID_CUT_WEATHER_PUZ - Cut weather puzzle -</td>
      <td>bool</td>
      <td>Flag for an unused puzzle involving a bridge and the Weather Duo. <br></td>
    </tr>
    <tr>
      <td>1107</td>
      <td>UNUSED_LANINA_PUZZLE_FOUND - Lanina puzzle found -</td>
      <td>bool</td>
      <td>Whether you found the water interaction in the unused Rouxls and Lanina puzzle. <br></td>
    </tr>
    <tr>
      <td>1108</td>
      <td>UNUSED_LANINA_PUZZLE_GRASS_COUNT - Lanina puzzle grass -</td>
      <td>number</td>
      <td>Amount of grass plucked by Susie in the unused Rouxls and Lanina puzzle. Just keeps you from re-plucking. <br></td>
    </tr>
    <tr>
      <td>1109</td>
      <td>PRE_EGG_BLOCK_X - Preegg block X -</td>
      <td>number</td>
      <td>X coordinate of the persistent block needed for the Ch3 egg. <br></td>
    </tr>
    <tr>
      <td>1110</td>
      <td>PRE_EGG_BLOCK_Y - Preegg block Y -</td>
      <td>number</td>
      <td>Y coordinate of the persistent block needed for the Ch3 egg. <br></td>
    </tr>
    <tr>
      <td>1111</td>
      <td>PRE_EGG_BLOCK_STATE - Block state -</td>
      <td>map</td>
      <td>Status of the puzzle with the persistent block needed for the Ch3 egg. <br>0 = Default state<br>1 = Block saved<br>2 = Puzzle solved<br></td>
    </tr>
    <tr>
      <td>1112</td>
      <td>SOLVED_NOWHERE_BLOCK_PUZZLE - Solved the Nowhere block puzzle -</td>
      <td>bool</td>
      <td>Whether you've solved the block puzzle to get to the Chapter 3 Bibliox with the TripTicket. <br></td>
    </tr>
    <tr>
      <td>1113</td>
      <td>GUARD_ZAPPER_BUTTONS - Guard Zapper buttons -</td>
      <td>map</td>
      <td>Progress with the Zapper guarding the cold area. <br>0 = Default state<br>1 = Played chest like bongos<br>2 = Shood off<br></td>
    </tr>
    <tr>
      <td>1114</td>
      <td>GUARD_ZAPPER_FOUGHT - Guard Zapper fought -</td>
      <td>bool</td>
      <td>Attempting to do nothing against the Zapper guarding the cold area. <br></td>
    </tr>
    <tr>
      <td>1115</td>
      <td>TENNA_MAILROOM_PROGRESS - Progress -</td>
      <td>map</td>
      <td>Progress entering Tenna's secret mail room. <br>0 = Default state<br>1 = Discovered<br>2 = Entered<br>3 = Found empty<br></td>
    </tr>
    <tr>
      <td>1116</td>
      <td>POINTS_FROM_BATTLE - Battle points current -</td>
      <td>number</td>
      <td>Number of points earned in battles on the current board. Used for the board score. <br></td>
    </tr>
    <tr>
      <td>1117</td>
      <td>POINTS_SPENT - Points spent -</td>
      <td>number</td>
      <td>Number of points spent on the current board. Used to include them in the board score as well as held points. <br></td>
    </tr>
    <tr>
      <td>1118</td>
      <td>LAST_MINIGAME_POINTS - Last minigame points -</td>
      <td>number</td>
      <td>Number of points earned in the last PHYSICAL CHALLENGE, tracked into the overall round evaluation. <br></td>
    </tr>
    <tr>
      <td>1119</td>
      <td>COOLER_BEG_COUNT - Watercooler beg count -</td>
      <td>number</td>
      <td>Number of times begged for mercy from Watercooler. Alters repeat flavortext. <br></td>
    </tr>
    <tr>
      <td>1122</td>
      <td>BOARD_KEY_COUNT - Count -</td>
      <td>number</td>
      <td>Board 1 key count. Used to award bonuses for extra keys. Also incremented if you buy the useless board 2 key. <br></td>
    </tr>
    <tr>
      <td>1123</td>
      <td>ENTERED_PARENT_0 - Entered parental room -</td>
      <td>bool</td>
      <td>Whether you've entered the room before the first Parental Lock, acknowledged by the party. <br></td>
    </tr>
    <tr>
      <td>1124</td>
      <td>TENNA_FALLING_OBJECT_NAME - Called falling Tenna -</td>
      <td>map</td>
      <td>What Tenna last called the falling objects on Board 1. Alters Board 2 dialogue. <br>0 = Default state<br>1 = Rocks<br>2 = Peaches<br></td>
    </tr>
    <tr>
      <td>1125</td>
      <td>STARTED_COWBOY_GAME - Started the first cowboy game -</td>
      <td>bool</td>
      <td>Whether you reached the first cowboy game in Chapter 3. <br></td>
    </tr>
    <tr>
      <td>1126</td>
      <td>UNUSED_SNEAK_TOP_LEFT_CAPTURE_COUNT - Sneak Caught Topleft -</td>
      <td>number</td>
      <td>Number of times captured in the top-left zone of the unused big sneaking section. <br></td>
    </tr>
    <tr>
      <td>1127</td>
      <td>UNUSED_SNEAK_TOP_RIGHT_CAPTURE_COUNT - Sneak Caught Topright -</td>
      <td>number</td>
      <td>Number of times captured in the top-right zone of the unused big sneaking section. <br></td>
    </tr>
    <tr>
      <td>1128</td>
      <td>UNUSED_SNEAK_BOTTOM_LEFT_CAPTURE_COUNT - Sneak Caught Botleft -</td>
      <td>number</td>
      <td>Number of times captured in the left zone of the unused big sneaking section. <br></td>
    </tr>
    <tr>
      <td>1129</td>
      <td>UNUSED_SNEAK_HARD_ZONE_1_CAPTURE_COUNT - Sneak Caught Hard1 -</td>
      <td>number</td>
      <td>Number of times captured in the first "hard" zone of the unused big sneaking section. <br></td>
    </tr>
    <tr>
      <td>1130</td>
      <td>UNUSED_SNEAK_HARD_ZONE_2_CAPTURE_COUNT - Sneak Caught Hard2 -</td>
      <td>number</td>
      <td>Number of times captured in the second "hard" zone of the unused big sneaking section. <br></td>
    </tr>
    <tr>
      <td>1131</td>
      <td>OVERWORLD_QUIZ_1 - Quiz 1 -</td>
      <td>bool</td>
      <td>Whether you completed the 1st overworld quiz while escaping. <br></td>
    </tr>
    <tr>
      <td>1132</td>
      <td>OVERWORLD_QUIZ_2 - Quiz 2 -</td>
      <td>bool</td>
      <td>Whether you completed the 2nd overworld quiz while escaping. <br></td>
    </tr>
    <tr>
      <td>1133</td>
      <td>PARENT_LOCK_1_START - Parental Lock 1 Started -</td>
      <td>bool</td>
      <td>Whether you got a wrong answer for the first parental lock, activating the screen with the puzzle. <br></td>
    </tr>
    <tr>
      <td>1134</td>
      <td>PARENT_LOCK_2_START - Parental Lock 2 Started -</td>
      <td>bool</td>
      <td>Whether you've activated the second parental lock puzzle by interacting with it. <br></td>
    </tr>
    <tr>
      <td>1135</td>
      <td>UNLOCKED_STEALTH - Unlocked stealth -</td>
      <td>bool</td>
      <td>Whether Susie has suggested the use of stealth. <br></td>
    </tr>
    <tr>
      <td>1136</td>
      <td>UNUSED_PA_ANNOUNCEMENT_FLAG - PA announcement -</td>
      <td>bool</td>
      <td>Never set, would have changed the logic of an incomplete "PA" system. <br></td>
    </tr>
    <tr>
      <td>1137</td>
      <td>FOUND_TRASH_SWITCH - Found the trash switch -</td>
      <td>bool</td>
      <td>Whether you've activated the trash switch at the end of the first stealth section. <br></td>
    </tr>
    <tr>
      <td>1138</td>
      <td>OBTAINED_UNUSED_WATERCOOLER_ITEM - Got the watercooler item -</td>
      <td>bool</td>
      <td>Whether you got an undefined item from an unused watercooler room in Chapter 3. <br></td>
    </tr>
    <tr>
      <td>1139</td>
      <td>OBTAINED_REVIVE_MINT_CH3 - Got Revive Mint -</td>
      <td>bool</td>
      <td>Whether you got the puzzle-locked Revive Mint in Chapter 3. <br></td>
    </tr>
    <tr>
      <td>1140</td>
      <td>OBTAINED_ONE_POINT - Got one point -</td>
      <td>bool</td>
      <td>Whether you got the chest with a singular point in the room with the Zapper who takes you nowhere. <br></td>
    </tr>
    <tr>
      <td>1141</td>
      <td>BIBLIOX_TALK_COUNT_CH3 - Bibliox talk count -</td>
      <td>number</td>
      <td>Number of times talked to the Chapter 3 in-game Bibliox. Dialogue does not reset. <br></td>
    </tr>
    <tr>
      <td>1142</td>
      <td>CAM_REMIND_SOLVE - Camera reminder puzzle -</td>
      <td>map</td>
      <td>Used for the unused camerareminder puzzle in Chapter 3. <br>0 = Default state<br>1 = Solved<br>2 = Solved with Ralsei<br></td>
    </tr>
    <tr>
      <td>1143</td>
      <td>COOLER_AVOID_NUM_COUNT - Watercooler Avoid Count -</td>
      <td>number</td>
      <td>Number of times you entered the room with the second Watercooler fight. They get closer up to 5 times, then block the way. Set to 50 after actually doing the fight. <br></td>
    </tr>
    <tr>
      <td>1144</td>
      <td>COOLER_2_FLIRT - Watercooler 2 Flirted -</td>
      <td>map</td>
      <td>Status flirting with the second Watercooler. Affects curtain flavortext. <br>0 = Default state<br>1 = Flirted<br>2 = Did not flirt<br>3 = Checked curtain after flirting<br></td>
    </tr>
    <tr>
      <td>1146</td>
      <td>INTERACTED_WITH_CURTAIN_COOLER - Interacted with the curtain after Watercooler -</td>
      <td>bool</td>
      <td>Whether you interacted with the curtain after fighting the second Watercooler. <br></td>
    </tr>
    <tr>
      <td>1147</td>
      <td>LAWNMOWER_BEAT_PAPER - Paper destroyed -</td>
      <td>bool</td>
      <td>Whether you used the lawnmower to destroy the Shadowmen's contracts. Earns their gratitude if not previously LOST. <br></td>
    </tr>
    <tr>
      <td>1148</td>
      <td>ROUXLS_SNACKS_CH3 - Rouxls Snacks Status -</td>
      <td>map</td>
      <td>Rouxls's progress when he shows up with the weather duo. <br>0 = Default state<br>1 = Showed up for snacks<br>2 = Took snacks and left<br></td>
    </tr>
    <tr>
      <td>1150</td>
      <td>PARENT_LOCK_3 - Parental Lock 3 Progress -</td>
      <td>map</td>
      <td>Progress with the third parental lock puzzle. <br>0 = Default state<br>1 = Activated<br>2 = Solved block puzzle<br>3 = Solved bridge puzzle<br>4 = Got camera<br>1.5 = Used TV<br></td>
    </tr>
    <tr>
      <td>1151</td>
      <td>SAW_SPAMTENNA_SCENE - Saw the Spamtenna scene -</td>
      <td>bool</td>
      <td>Whether you saw Tenna coat Spamton in foam in self-defense. <br></td>
    </tr>
    <tr>
      <td>1152</td>
      <td>HORSE_RALSEI - Ralsei horse -</td>
      <td>bool</td>
      <td>Whether Ralsei forgot to change out of his horse costume. <br></td>
    </tr>
    <tr>
      <td>1153</td>
      <td>HAY_RESPONSE - Hay Susie Reaction -</td>
      <td>map</td>
      <td>Set based on how Susie reacts to Ralsei considering eating hay. Depends on whether you've previously eaten moss. <br>0 = Default state<br>1 = It's for sleeping (no moss)<br>2 = Eat spinach (ate moss with Susie)<br></td>
    </tr>
    <tr>
      <td>1154</td>
      <td>BONUS_ZONE_TREASURE_1 - Treasure 1 -</td>
      <td>bool</td>
      <td>Whether you got the 1st treasure chest (of points) in Tenna's bonus zone. <br></td>
    </tr>
    <tr>
      <td>1155</td>
      <td>BONUS_ZONE_TREASURE_2 - Treasure 2 -</td>
      <td>bool</td>
      <td>Whether you got the 2nd treasure chest (of points) in Tenna's bonus zone. <br></td>
    </tr>
    <tr>
      <td>1156</td>
      <td>BONUS_ZONE_TREASURE_3 - Treasure 3 -</td>
      <td>bool</td>
      <td>Whether you got the 3rd treasure chest (of points) in Tenna's bonus zone. <br></td>
    </tr>
    <tr>
      <td>1157</td>
      <td>BONUS_ZONE_POINTS_1 - Points 1 -</td>
      <td>bool</td>
      <td>Whether you got the 1st coin in Tenna's bonus zone. <br></td>
    </tr>
    <tr>
      <td>1158</td>
      <td>BONUS_ZONE_POINTS_2 - Points 2 -</td>
      <td>bool</td>
      <td>Whether you got the 2nd coin in Tenna's bonus zone. <br></td>
    </tr>
    <tr>
      <td>1159</td>
      <td>BONUS_ZONE_POINTS_3 - Points 3 -</td>
      <td>bool</td>
      <td>Whether you got the 3rd coin in Tenna's bonus zone. <br></td>
    </tr>
    <tr>
      <td>1160</td>
      <td>BONUS_ZONE_POINTS_4 - Points 4 -</td>
      <td>bool</td>
      <td>Whether you got the 4th coin in Tenna's bonus zone. <br></td>
    </tr>
    <tr>
      <td>1161</td>
      <td>TENNA_BONUS_ZONE - Entered -</td>
      <td>bool</td>
      <td>Whether you've entered Tenna's Bonus Zone behind the green panel (prior to Pipis scene). <br></td>
    </tr>
    <tr>
      <td>1162</td>
      <td>BONUS_BIG_CHEST - Bonus Big Chest -</td>
      <td>bool</td>
      <td>Whether you've opened the giant test in Tenna's Bonus Zone (with a Pippins). <br></td>
    </tr>
    <tr>
      <td>1163</td>
      <td>CHECK_RECRUITS_CH3 - Recruits checked -</td>
      <td>bool</td>
      <td>Whether you checked the employee list in Chapter 3 to tell if you had missed any recruits. <br></td>
    </tr>
    <tr>
      <td>1164</td>
      <td>LIGHTMAZE_FOUGHT - Lightmaze Zapper Fought -</td>
      <td>bool</td>
      <td>Whether you fought the Zapper in the lightmaze room so unused, it has no exits. <br></td>
    </tr>
    <tr>
      <td>1165</td>
      <td>OVERWORLD_QUIZ_3 - Quiz 3 -</td>
      <td>bool</td>
      <td>Whether you completed an overworld quiz in the big maze room. <br></td>
    </tr>
    <tr>
      <td>1166</td>
      <td>OVERWORLD_QUIZ_4 - Quiz 4 -</td>
      <td>bool</td>
      <td>Whether you completed an overworld quiz in the big maze room. <br></td>
    </tr>
    <tr>
      <td>1167</td>
      <td>OVERWORLD_QUIZ_5 - Quiz 5 -</td>
      <td>bool</td>
      <td>Whether you completed an overworld quiz in the big maze room. <br></td>
    </tr>
    <tr>
      <td>1168</td>
      <td>OVERWORLD_QUIZ_6 - Quiz 6 -</td>
      <td>bool</td>
      <td>Whether you completed an overworld quiz in the big maze room. <br></td>
    </tr>
    <tr>
      <td>1169</td>
      <td>OBTAINED_UNUSED_LANINA_POINTS - Got Lanina's puzzle points -</td>
      <td>bool</td>
      <td>Whether you got a 100-point chest in the unused Rouxls and Lanina puzzle room. <br></td>
    </tr>
    <tr>
      <td>1171</td>
      <td>BOARD_2_BATTLES - Board 2 Battles Count -</td>
      <td>number</td>
      <td>Number of battles engaged in on Board 2. <br></td>
    </tr>
    <tr>
      <td>1173</td>
      <td>RANK_BOARD_1 - Board rank -</td>
      <td>map</td>
      <td>Your rank on Board 1. <br>-1 = ?<br>0 = Z<br>1 = C<br>2 = B<br>3 = A<br>4 = S<br>5 = T<br></td>
    </tr>
    <tr>
      <td>1174</td>
      <td>RANK_BOARD_2 - Board rank -</td>
      <td>map</td>
      <td>Your rank on Board 2. <br>-1 = ?<br>0 = Z<br>1 = C<br>2 = B<br>3 = A<br>4 = S<br>5 = T<br></td>
    </tr>
    <tr>
      <td>1176</td>
      <td>ODD_CONTROLLER_PROGRESS - Oddcontroller State -</td>
      <td>map</td>
      <td>Progress obtaining the OddController. <br>0 = Default state<br>1 = Tried game<br>2 = Got controller<br></td>
    </tr>
    <tr>
      <td>1177</td>
      <td>OBTAINED_TENNA_TIE - Got Tenna Tie -</td>
      <td>bool</td>
      <td>Whether you got the Tenna Tie from the Ball Machine. <br></td>
    </tr>
    <tr>
      <td>1178</td>
      <td>OBTAINED_EXECBUFFET - Got ExecBuffet -</td>
      <td>bool</td>
      <td>Whether you got the Executive Buffet from the Ball Machine. <br></td>
    </tr>
    <tr>
      <td>1179</td>
      <td>OBTAINED_TENSIONMAX - Got TensionMax -</td>
      <td>bool</td>
      <td>Whether you got the TensionMax from the Ball Machine. <br></td>
    </tr>
    <tr>
      <td>1180</td>
      <td>OBTAINED_REVIVEMINT - Got ReviveMint -</td>
      <td>bool</td>
      <td>Whether you got the Revive Mint from the Ball Machine. <br></td>
    </tr>
    <tr>
      <td>1181</td>
      <td>OBTAINED_BLUE_RIBBON - Got Blue Ribbon -</td>
      <td>bool</td>
      <td>Whether you got the Blue Ribbon from the Ball Machine. <br></td>
    </tr>
    <tr>
      <td>1182</td>
      <td>GACHA_LASTBET - Last bet -</td>
      <td>number</td>
      <td>Amount previously spent on the gumball machine in Chapter 3, used to compute gold prize odds. Resets upon earning a gold prize. <br></td>
    </tr>
    <tr>
      <td>1184</td>
      <td>SNEAKING_FAST - Sneaking Fast -</td>
      <td>bool</td>
      <td>Whether the party has decided to sneak really fast. <br></td>
    </tr>
    <tr>
      <td>1185</td>
      <td>S_RANK_ROOM_ANSWER - S Rank Room Answer -</td>
      <td>map</td>
      <td>What you told Susie you were doing in the S-Rank room. <br>0 = Default state<br>1 = Playing games<br>2 = Nothing<br></td>
    </tr>
    <tr>
      <td>1186</td>
      <td>S_RANK_RETURN_2 - S Rank Return 2 -</td>
      <td>bool</td>
      <td>Whether you've gotten the scene of Ralsei mentioning RPGs after returning from the Sword Island Board. <br></td>
    </tr>
    <tr>
      <td>1187</td>
      <td>Z_RANK_UNLOCK - Z Rank Door Unlock -</td>
      <td>map</td>
      <td>Whether you've talked to unlock the Z-Rank door. Changes for each board. <br>0 = Default state<br>1 = Open Board 1<br>2 = Open Board 2<br></td>
    </tr>
    <tr>
      <td>1188</td>
      <td>C_RANK_WATERCOOLER_ENCOUNTER_OUTCOME - Watercooler -</td>
      <td>map</td>
      <td>Status of the Watercooler encounter in the C-Rank room. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1189</td>
      <td>UNLOCKED_SUSIEZILLA - Unlocked -</td>
      <td>bool</td>
      <td>Whether you've purchased access to the Suziezilla game. <br></td>
    </tr>
    <tr>
      <td>1190</td>
      <td>CONTROL_UNJUMBLE - Controls Unjumbled -</td>
      <td>map</td>
      <td>Whether you chose to... keep your controls? It's reversed, Ralsei playing as Kris (board 2) is actually the 0 value. <br>0 = You can have a turn<br>1 = Let's all go back to normal<br></td>
    </tr>
    <tr>
      <td>1191</td>
      <td>MANHOLE_ACTIVATION_CH3 - Manhole used -</td>
      <td>map</td>
      <td>When you last used the Z-Rank manhole to reach the original game. Used to open the return manhole. <br>0 = Default state<br>1 = Opened after board 1<br>2 = Opened after board 2<br></td>
    </tr>
    <tr>
      <td>1192</td>
      <td>S_RANK_RETURN_3 - S Rank Return 3 -</td>
      <td>bool</td>
      <td>Whether you've gotten the scene of Susie and Ralsei racing after returning with the Shadow Mantle. <br></td>
    </tr>
    <tr>
      <td>1193</td>
      <td>COOKING_BEST_SCORE - Cooking score -</td>
      <td>number</td>
      <td>Highest score at the cooking minigame. <br></td>
    </tr>
    <tr>
      <td>1194</td>
      <td>COOKING_BEST_RANK - Cooking rank -</td>
      <td>map</td>
      <td>The corresponding rank to your cooking minigame high score. <br>-1 = ?<br>0 = Z<br>1 = C<br>2 = B<br>3 = A<br>4 = S<br>5 = T<br></td>
    </tr>
    <tr>
      <td>1195</td>
      <td>RAISE_BAT_HISCORE - High score -</td>
      <td>number</td>
      <td>Highest score on Raise Up Your Bat, Normal Mode <br></td>
    </tr>
    <tr>
      <td>1196</td>
      <td>RAISE_BAT_HIRANK - High rank -</td>
      <td>map</td>
      <td>Highest rank on Raise Up Your Bat, Normal Mode <br>-1 = ?<br>0 = Z<br>1 = C<br>2 = B<br>3 = A<br>4 = S<br>5 = T<br></td>
    </tr>
    <tr>
      <td>1197</td>
      <td>SUSIEZILLA_HIGH_SCORE - High score -</td>
      <td>number</td>
      <td>High score at Susiezilla. <br></td>
    </tr>
    <tr>
      <td>1198</td>
      <td>SUSIEZILLA_HIGH_RANK - High rank -</td>
      <td>map</td>
      <td>The corresponding rank to your Susiezilla high score. <br>-1 = ?<br>0 = Z<br>1 = C<br>2 = B<br>3 = A<br>4 = S<br>5 = T<br></td>
    </tr>
    <tr>
      <td>1199</td>
      <td>SUSIE_TENNA_CHAT_1 - Susie Tenna Chat 1 -</td>
      <td>bool</td>
      <td>Whether you saw Susie compliment Tenna's show between boards. <br></td>
    </tr>
    <tr>
      <td>1200</td>
      <td>RALSEI_FACE_THOUGHTS - Ralsei Face Thoughts -</td>
      <td>map</td>
      <td>Your commentary on Ralsei's face, if not watching Susie. <br>0 = Default state<br>1 = Seen it before<br>2 = It's unique<br>3 = It's cute<br></td>
    </tr>
    <tr>
      <td>1201</td>
      <td>TENNA_OPINION_SUSIE - Tenna Opinion Susie -</td>
      <td>map</td>
      <td>Your opinion on Tenna as given to Susie before Board 2. <br>0 = Default state<br>1 = He's fun<br>2 = He sucks<br></td>
    </tr>
    <tr>
      <td>1202</td>
      <td>OPENED_TRASH_CAN_1_CH3 - Opened trash can 1 -</td>
      <td>bool</td>
      <td>Whether you opened the 1st trash can in Chapter 3, with 10 points inside. <br></td>
    </tr>
    <tr>
      <td>1203</td>
      <td>OPENED_TRASH_CAN_2_CH3 - Opened trash can 2 -</td>
      <td>bool</td>
      <td>Whether you opened the 2nd trash can in Chapter 3, with nothing inside. <br></td>
    </tr>
    <tr>
      <td>1204</td>
      <td>OPENED_TRASH_CAN_3_CH3 - Opened trash can 3 -</td>
      <td>bool</td>
      <td>Whether you opened the 3rd trash can in Chapter 3, with the TVSlop. <br></td>
    </tr>
    <tr>
      <td>1205</td>
      <td>OPENED_TRASH_CAN_4_CH3 - Opened trash can 4 -</td>
      <td>bool</td>
      <td>Whether you opened the 4th trash can in Chapter 3, with nothing inside. <br></td>
    </tr>
    <tr>
      <td>1206</td>
      <td>OPENED_TRASH_CAN_5_CH3 - Opened trash can 5 -</td>
      <td>bool</td>
      <td>Whether you opened the 5th trash can in Chapter 3, with 2 points inside. <br></td>
    </tr>
    <tr>
      <td>1207</td>
      <td>OPENED_TRASH_CAN_6_CH3 - Opened trash can 6 -</td>
      <td>bool</td>
      <td>Whether you opened the 6th trash can in Chapter 3, with 50 points inside. <br></td>
    </tr>
    <tr>
      <td>1208</td>
      <td>SUSIE_TENNA_CHAT_2 - Susie Tenna Chat 2 -</td>
      <td>map</td>
      <td>Progress with Susie questioning Tenna's show between boards. <br>0 = Default state<br>1 = Started scene<br>2 = Finished scene<br></td>
    </tr>
    <tr>
      <td>1209</td>
      <td>OPENED_TRASH_CAN_7_CH3 - Opened trash can 7 -</td>
      <td>bool</td>
      <td>Whether you opened the 7th trash can in Chapter 3, with nothing inside. <br></td>
    </tr>
    <tr>
      <td>1210</td>
      <td>ELNINA_GREEN_ROOM_RESPONSE - Elnina Greenroom Talk -</td>
      <td>map</td>
      <td>What you told Elnina about her relationship in the Green Room. <br>0 = Default state<br>1 = You're strong and independent<br>2 = Your forecast is love<br></td>
    </tr>
    <tr>
      <td>1211</td>
      <td>LANINO_GREEN_ROOM_RESPONSE - Lanino Greenroom Talk -</td>
      <td>map</td>
      <td>What you told Lanino about his relationship in the Green Room. <br>0 = Default state<br>1 = You're strong and independent<br>2 = Your forecast is love<br></td>
    </tr>
    <tr>
      <td>1212</td>
      <td>SUSIEBRIDGE_STATE - Susiebridge State -</td>
      <td>map</td>
      <td>Progress on the unused Susie bridging minigame. <br>0 = Default state<br>1 = ???<br>2 = Complete<br></td>
    </tr>
    <tr>
      <td>1213</td>
      <td>OBTAINED_300_POINTS - Got 300 points -</td>
      <td>bool</td>
      <td>Whether you got the chest of points in the room with a Susie board puzzle. <br></td>
    </tr>
    <tr>
      <td>1214</td>
      <td>PARENTAL_LOCK_CONCERN_TARGET - Who Asked Okay -</td>
      <td>map</td>
      <td>Who you asked whether they were okay in the Chapter 3 parental lock room. <br>0 = Default state<br>1 = Susie<br>2 = Ralsei<br>3 = Neither<br></td>
    </tr>
    <tr>
      <td>1215</td>
      <td>SUSIE_REASSURANCE - Susie Reassurance Response -</td>
      <td>map</td>
      <td>What you said to Susie (if talking to her) in the parental lock room. <br>0 = Default state<br>1 = I'm not a dream (creepy)<br>2 = Your friendships are real (fake-heroic)<br>3 = Sucks to be you (unwittingly ironic)<br></td>
    </tr>
    <tr>
      <td>1216</td>
      <td>RALSEI_REASSURANCE - Ralsei Reassurance Response -</td>
      <td>map</td>
      <td>What you said to Ralsei (if talking to him) in the parental lock room. <br>0 = Default state<br>1 = It's ok to take it easy<br>2 = Stay on task<br></td>
    </tr>
    <tr>
      <td>1217</td>
      <td>ICECREAM_FOR_SUSIE - Icecream For Susie -</td>
      <td>map</td>
      <td>What you said to Ralsei about getting ice cream from him to Susie. <br>0 = Default state<br>1 = I'm not going with her<br>2 = I'm saying it's from me<br>3 = Of course<br></td>
    </tr>
    <tr>
      <td>1218</td>
      <td>FESTIVAL_RAL_WHOELSE - Festival Ralsei Whoelse -</td>
      <td>map</td>
      <td>Who you told Ralsei you're going to the festival with, if not Susie. <br>0 = Default state<br>1 = Noelle<br>2 = Ralsei<br>3 = Berdly (BERDLY!?)<br>4 = Not going<br></td>
    </tr>
    <tr>
      <td>1219</td>
      <td>SAW_SUSIEZILLA_INTRO - Saw the Susiezilla intro -</td>
      <td>bool</td>
      <td>Whether you completed the intro scene for the Susiezilla game. <br></td>
    </tr>
    <tr>
      <td>1220</td>
      <td>COMPLETED_SUSIEZILLA - Beat Susiezilla -</td>
      <td>bool</td>
      <td>Whether you reached the elusive BOARD CLEAR of the Suziezilla game. <br></td>
    </tr>
    <tr>
      <td>1221</td>
      <td>OBTAINED_COOLER_CRATER - Got the Watercooler crater points -</td>
      <td>bool</td>
      <td>Whether you got the 200 points from underneath the C-Rank Watercooler. <br></td>
    </tr>
    <tr>
      <td>1222</td>
      <td>OBTAINED_TENNA_STATUE - Got Golden Tenna -</td>
      <td>bool</td>
      <td>Whether you got the Golden Tenna Statue from the Ball Machine. <br></td>
    </tr>
    <tr>
      <td>1223</td>
      <td>OBTAINED_DOG_DOLLAR - Got Dog Dollar -</td>
      <td>bool</td>
      <td>Whether you got the Dog Dollar from the Ball Machine. <br></td>
    </tr>
    <tr>
      <td>1224</td>
      <td>OPENED_BONUS_ZONE - Opened -</td>
      <td>bool</td>
      <td>Whether you opened Tenna's secret bonus zone behind a green screen. <br></td>
    </tr>
    <tr>
      <td>1225</td>
      <td>OPENED_SAMS_ZONE - Opened -</td>
      <td>bool</td>
      <td>Whether you opened the secret zone where you can choose whether the talking cages love or hate. Behind a green screen. <br></td>
    </tr>
    <tr>
      <td>1226</td>
      <td>OBTAINED_1225_ROOM - Entered -</td>
      <td>bool</td>
      <td>Whether you entered the secret 1225 room in the Ball Machine game. Yes, the flag is so close. <br></td>
    </tr>
    <tr>
      <td>1227</td>
      <td>OBTAINED_ANTLION_PHOTO - Got the red-antlion photo -</td>
      <td>bool</td>
      <td>Whether you photographed the red antlion in Board 2. <br></td>
    </tr>
    <tr>
      <td>1228</td>
      <td>ENTERED_COLDPLACE - Entered Cold Place -</td>
      <td>bool</td>
      <td>Whether you've entered the Cold Place and such has been acknowledged by the party. <br></td>
    </tr>
    <tr>
      <td>1229</td>
      <td>LAST_SNEAK_TIMES_FOUND_COUNT - Times caught -</td>
      <td>number</td>
      <td>Number of times caught by the Zapper who later reveals he does not want to be there either. <br></td>
    </tr>
    <tr>
      <td>1230</td>
      <td>SNEAK_ZAPPER_STATE - Zapper state -</td>
      <td>map</td>
      <td>Progress with the Zapper who does not want to be there either. <br>0 = Default state<br>1 = Zapper joined<br>2 = Passed room<br></td>
    </tr>
    <tr>
      <td>1231</td>
      <td>PARENT_LOCK_3_DONE - Parental Lock 3 Done -</td>
      <td>bool</td>
      <td>Whether you solved the undefined parental lock in Chapter 3, optional on Sword Route. <br></td>
    </tr>
    <tr>
      <td>1232</td>
      <td>STARTED_COWBOY_GAME_2 - Started the second cowboy game -</td>
      <td>bool</td>
      <td>Whether you reached the second cowboy game in Chapter 3. <br></td>
    </tr>
    <tr>
      <td>1233</td>
      <td>PARENT_LOCK_3_USED - Parental Lock 3 Used -</td>
      <td>bool</td>
      <td>Whether you went through the door after the undefined parental lock in Chapter 3. <br></td>
    </tr>
    <tr>
      <td>1234</td>
      <td>SUSIEZILLA_BEST_TIME - Susiezilla Best Time -</td>
      <td>number</td>
      <td>The duration of your best Suziezilla run. <br></td>
    </tr>
    <tr>
      <td>1235</td>
      <td>TENNA_MAD_AT_STAFF - Tenna Mad At Staff -</td>
      <td>bool</td>
      <td>Whether you've seen the scene where Tenna gets mad the Darkners haven't found the Lightners yet. <br></td>
    </tr>
    <tr>
      <td>1236</td>
      <td>SAW_RAMB_QUIT_SCENE - Saw Ramb quit -</td>
      <td>bool</td>
      <td>Whether you've seen the scene where Tenna gets mad Ramb is quitting on him. <br></td>
    </tr>
    <tr>
      <td>1237</td>
      <td>OBTAINED_ROUXLS_BLOCK - Bought Rouxls's block -</td>
      <td>bool</td>
      <td>Whether you purchased Rouxls's block for 1 point. <br></td>
    </tr>
    <tr>
      <td>1238</td>
      <td>MOVED_RAMB_TO_FINAL_GAME - Moved Ramb to the final game -</td>
      <td>bool</td>
      <td>Whether you've moved Ramb to play the final game. <br></td>
    </tr>
    <tr>
      <td>1239</td>
      <td>RAMB_PETRIFICATION_LORE_PROGRESS - Ramb Petrify Story -</td>
      <td>map</td>
      <td>Your progress in learning about why Ramb petrified. <br>0 = Default state<br>1 = Spawned Pippins<br>2 = "No one will shed a tear for him."<br></td>
    </tr>
    <tr>
      <td>1240</td>
      <td>TALKED_TO_STARWALKER_CH3 - Talked to original &ensp;*Starwalker* -</td>
      <td>bool</td>
      <td>Whether you've talked to Starwalker in the first room after escaping Tenna. <br></td>
    </tr>
    <tr>
      <td>1241</td>
      <td>RAL_SUSPECT_ZAPPER - Ralsei Suspect Zapper -</td>
      <td>bool</td>
      <td>Whether you've interacted with the Zapper guarding the parental locks, preventing Ralsei's dialogue from repeating. <br></td>
    </tr>
    <tr>
      <td>1242</td>
      <td>BEST_FOOD_STACK - Best Food Stack -</td>
      <td>number</td>
      <td>Number of food items successfully served in a single simultaneous stack in the cooking minigame. Used to track the record on replay. <br></td>
    </tr>
    <tr>
      <td>1243</td>
      <td>ZAPPER_JAIL_2 - Zapper Jail 2 State -</td>
      <td>map</td>
      <td>Progress on the second highly ineffective jail you are placed in by a Zapper while sneaking. <br>0 = Default state<br>1 = Imprisoned<br>2 = Escaped<br></td>
    </tr>
    <tr>
      <td>1244</td>
      <td>OBTAINED_PARENTAL_LOCK_CAMERA - Got the Parental Lock camera -</td>
      <td>bool</td>
      <td>Whether you got the camera in the Parental Lock 3 puzzle. <br></td>
    </tr>
    <tr>
      <td>1245</td>
      <td>NUM_PARENT_PHOTOS - Parental Photos Num -</td>
      <td>number</td>
      <td>Number of photos taken in the Parental Lock 3 puzzle. The in-game console crashes after 8. <br></td>
    </tr>
    <tr>
      <td>1246</td>
      <td>OBTAINED_100_DIG - Dug up the 100-point hole -</td>
      <td>bool</td>
      <td>Whether you dug up the rare 100-point hole in the room with the many Lancers. <br></td>
    </tr>
    <tr>
      <td>1248</td>
      <td>LEVEL_UP_COUNT_CH3 - Level-ups -</td>
      <td>number</td>
      <td>The number of times you have leveled up by violently defeating an encounter. Used for certain increases that only occur every 2, 4, or 10 encounters. <br></td>
    </tr>
    <tr>
      <td>1249</td>
      <td>AT_MAGIC_GAIN_COUNT_CH3 - AT/Magic gains -</td>
      <td>number</td>
      <td>The number of times your AT and Magic have increased due to leveling up (every ten encounters). <br></td>
    </tr>
    <tr>
      <td>1250</td>
      <td>TALKED_TO_JAILED_PIPPINS - Talked to the jailed Pippins -</td>
      <td>bool</td>
      <td>Whether you've talked to the imprisoned Pippins selling TV Dinners. Alters repeat interaction. <br></td>
    </tr>
    <tr>
      <td>1251</td>
      <td>GOULDEN_SON_TALE - Tale -</td>
      <td>map</td>
      <td>Progress telling of Goulden Son. <br>0 = Default state<br>1 = Interacted with 2<br>2 = 2 knew of 1<br>3 = 1 became 3<br>4 = Told of 3<br>1.5 = Told of 2<br></td>
    </tr>
    <tr>
      <td>1252</td>
      <td>GOULDEN_SON_DESTINATION - Destination -</td>
      <td>map</td>
      <td>Used to determine which is Goulden Son and which is Goulden Son 2. The one you interact with first after the lights are gone will be Goulden Son. <br>0 = Default state<br>1 = Right is Goulden Son 2<br>2 = Left is Goulden Son 2<br></td>
    </tr>
    <tr>
      <td>1253</td>
      <td>OPENED_TRASH_CAN_8_CH3 - Opened trash can 8 -</td>
      <td>bool</td>
      <td>Whether you opened the 8th trash can in Chapter 3, with 120 points inside. <br></td>
    </tr>
    <tr>
      <td>1254</td>
      <td>STONE_LANCER_CH3 - Stone Lancer Seen -</td>
      <td>bool</td>
      <td>Whether you saw Lancer petrified in Chapter 3 (in the room where you get his controllers). <br></td>
    </tr>
    <tr>
      <td>1255</td>
      <td>SWORD_ROUTE_KILLS - Kills -</td>
      <td>number</td>
      <td>Number of enemies killed using your sword in the Chapter 3 minigames. Appears in Kris's stats. <br></td>
    </tr>
    <tr>
      <td>1256</td>
      <td>PLUCKED_GRASS_COUNT - Grass plucked -</td>
      <td>number</td>
      <td>The number of times Susie plucks grass in the Chapter 3 minigames. Appears in Susie's stats (up to 99). <br></td>
    </tr>
    <tr>
      <td>1257</td>
      <td>CARRIED_RALSEI_COUNT - Ralsei carried -</td>
      <td>number</td>
      <td>The number of times Ralsei was carried in the Chapter 3 minigames. Appears in Ralsei's stats (up to 99). <br></td>
    </tr>
    <tr>
      <td>1258</td>
      <td>RUN_REMINDER_CH3 - Run reminder -</td>
      <td>bool</td>
      <td>Whether Susie reminded you you can run at the start of Chapter 3. <br></td>
    </tr>
    <tr>
      <td>1259</td>
      <td>SECOND_RUN_REMINDER_CH3 - Run reminder 2 -</td>
      <td>bool</td>
      <td>Whether Ralsei reminded you you can run in Chapter 3. <br></td>
    </tr>
    <tr>
      <td>1260</td>
      <td>TALKED_TO_RALSEI_AT_EYE_PUZZLE - Talked to Ralsei at the eye puzzle -</td>
      <td>bool</td>
      <td>Whether you've talked to Ralsei at the Chapter 3 starting eye puzzle. Alters repeat dialogue. <br></td>
    </tr>
    <tr>
      <td>1261</td>
      <td>TALKED_TO_SUSIE_AT_EYE_PUZZLE - Talked to Susie at the eye puzzle -</td>
      <td>bool</td>
      <td>Whether you've talked to Susie at the Chapter 3 starting eye puzzle. Alters repeat dialogue. <br></td>
    </tr>
    <tr>
      <td>1262</td>
      <td>PARENT_LOCK_1_CLOSE_COUNT - Parental Lock 1 Close -</td>
      <td>number</td>
      <td>Number of times you got the first parental lock numbers, but in the wrong order. Ralsei has special dialogue for the first couple tries. <br></td>
    </tr>
    <tr>
      <td>1263</td>
      <td>ALMOST_BEAT_KNIGHT - Almost-beaten dialogue -</td>
      <td>bool</td>
      <td>Whether you've gotten the one-off pep talk from Gaster for reaching the damage threshold then dying. <br></td>
    </tr>
    <tr>
      <td>1264</td>
      <td>KNIGHT_DEATHS_COUNT - Deaths -</td>
      <td>number</td>
      <td>Number of times you died to the Knight -- it doesn't reset your save when you retry. <br></td>
    </tr>
    <tr>
      <td>1265</td>
      <td>PHASER_CANNONS - Phaser Cannons -</td>
      <td>bool</td>
      <td>Whether you performed the Phaser Cannons Easter Egg in the cooking minigame. <br></td>
    </tr>
    <tr>
      <td>1266</td>
      <td>MOVED_RAMB_AFTER_ROUND_2 - Moved Ramb after round 2 -</td>
      <td>bool</td>
      <td>Whether you've talked to Ramb after round 2 for him to move away from the door. <br></td>
    </tr>
    <tr>
      <td>1267</td>
      <td>LAWNMOWER_SCORE - Lawnmower score -</td>
      <td>number</td>
      <td>Score in Tenna's lawnmower minigame, minimum 1. Reused for a TVDinner chest. <br></td>
    </tr>
    <tr>
      <td>1268</td>
      <td>MINI_ATTACK_SUSIE - Mini Attack Susie -</td>
      <td>bool</td>
      <td>Whether the mini-Kris tried to attack Susie, causing her to offer to let Kris gnaw her hair. <br></td>
    </tr>
    <tr>
      <td>1269</td>
      <td>SHADOW_HOME - Shadow Home Seen -</td>
      <td>bool</td>
      <td>Whether you saw the smashed TV using the Shadow Crystal. <br></td>
    </tr>
    <tr>
      <td>1270</td>
      <td>SHADOW_FAILED_CH3 - Shadow failed -</td>
      <td>bool</td>
      <td>Whether you used the Shadow Crystal in Chapter 3 and saw nothing. 1269 is more interesting. <br></td>
    </tr>
    <tr>
      <td>1271</td>
      <td>GLASS_UNDYNE_FROZE - Glass Undyne Froze -</td>
      <td>bool</td>
      <td>Whether you used the Glass in Chapter 3 and saw Undyne frozen in ice. Unused; you cannot visit the Light World in Chapter 3. <br></td>
    </tr>
    <tr>
      <td>1272</td>
      <td>GLASS_FAILED_CH3 - Glass failed -</td>
      <td>bool</td>
      <td>Whether you used the Glass in Chapter 3 and saw nothing. 1271 is more interesting. <br></td>
    </tr>
    <tr>
      <td>1273</td>
      <td>GAMESHOW_NAME_JA - Japanese mode -</td>
      <td>bool</td>
      <td>Whether the start of Chapter 3 (naming Kris on the show) was played in Japanese. <br></td>
    </tr>
    <tr>
      <td>1274</td>
      <td>GAMESHOW_NAME_1_BACKUP - Backup letter 1 -</td>
      <td>map</td>
      <td>Secondary tracker for the first letter of Kris's name (used for safety with translation). <br>Every number corresponds to a lettter. <br> 0 = A,<br> 1 = B,<br> 2 = C, etc.</td>
    </tr>
    <tr>
      <td>1275</td>
      <td>GAMESHOW_NAME_2_BACKUP - Backup letter 2 -</td>
      <td>map</td>
      <td>Secondary tracker for the second letter of Kris's name (used for safety with translation). <br>Every number corresponds to a lettter. <br> 0 = A,<br> 1 = B,<br> 2 = C, etc.</td>
    </tr>
    <tr>
      <td>1276</td>
      <td>GAMESHOW_NAME_3_BACKUP - Backup letter 3 -</td>
      <td>map</td>
      <td>Secondary tracker for the third letter of Kris's name (used for safety with translation). <br>Every number corresponds to a lettter. <br> 0 = A,<br> 1 = B,<br> 2 = C, etc.</td>
    </tr>
    <tr>
      <td>1277</td>
      <td>PIPPINS_BONUS_STOLE - Pippins chests -</td>
      <td>number</td>
      <td>Appears? to be the number of chests looted by Pippinses in Tenna's bonus zone. <br></td>
    </tr>
    <tr>
      <td>1278</td>
      <td>SWORDROUTE_SODA - Soda -</td>
      <td>map</td>
      <td>Status of the soda left by Susie after obtaining the Shadow Mantle. <br>0 = Default state<br>1 = Soda placed<br>2 = Soda collected<br></td>
    </tr>
    <tr>
      <td>1279</td>
      <td>RAISE_BAT_HARD_HISCORE - Hard score -</td>
      <td>number</td>
      <td>High score on Raise Up Your Bat, Hard Mode. (Unused in Chapter 3) <br></td>
    </tr>
    <tr>
      <td>1280</td>
      <td>RAISE_BAT_HARD_HIRANK - Hard rank -</td>
      <td>map</td>
      <td>Highest rank on Raise Up Your Bat, Hard Mode. (Unused in Chapter 3) <br>-1 = ?<br>0 = Z<br>1 = C<br>2 = B<br>3 = A<br>4 = S<br>5 = T<br></td>
    </tr>
    <tr>
      <td>1312</td>
      <td>PINK_COINS - Pink Coins -</td>
      <td>number</td>
      <td>Your amount of Pink Coins. <br></td>
    </tr>
    <tr>
      <td>1365</td>
      <td>SCISSORS_PUZZLE_FLAGS - Scissors puzzle flags -</td>
      <td>number</td>
      <td>Raw bitfield state for Chapter 5 scissors puzzle progress. <br></td>
    </tr>
    <tr>
      <td>1391</td>
      <td>VOICE_CLIPS_ENABLED - Voice Clips -</td>
      <td>bool</td>
      <td>Voice Clips toggle in settings. <br></td>
    </tr>
    <tr>
      <td>1399</td>
      <td>HOPSCHEF_PROGRESS_FLAG - Hop Chef progress -</td>
      <td>number</td>
      <td>Raw progress state for the Hop Chef challenge. <br></td>
    </tr>
    <tr>
      <td>1404</td>
      <td>RIBBON_CHEST_STATE - Ribbon chest state -</td>
      <td>map</td>
      <td>Tracks the Chapter 5 RedRibbon chest and first ribbon equip scenes. <br>0 = Default state<br>1 = Opened chest; Susie can equip ribbons<br>2 = First equipped ribbon on Kris<br>3 = First equipped ribbon on Susie<br>4 = First equipped ribbon on Ralsei<br></td>
    </tr>
    <tr>
      <td>1411</td>
      <td>FLOWERY_DOLLARS - Flowery Dollars -</td>
      <td>number</td>
      <td>Your amount of Flowery Dollars. <br></td>
    </tr>
    <tr>
      <td>1421</td>
      <td>THRASH_FIT_HAIR - Hair -</td>
      <td>map</td>
      <td>Thrash Fit hair variant. <br>0 = Normal<br>1 = Ponytail<br>2 = Royal Bob<br>3 = Duck Tiara<br>4 = Fresh Swish<br>5 = Princey<br></td>
    </tr>
    <tr>
      <td>1422</td>
      <td>THRASH_FIT_SHIRT - Shirt -</td>
      <td>map</td>
      <td>Thrash Fit shirt variant. <br>0 = Dark Jacket<br>1 = Rip Jacket<br>2 = Similar Hood<br>3 = Duck<br>4 = Lancer Shirt<br>5 = Royal Dress<br>6 = Swag Jacket<br>7 = Tuxusie<br></td>
    </tr>
    <tr>
      <td>1423</td>
      <td>THRASH_FIT_PANTS - Pants -</td>
      <td>map</td>
      <td>Thrash Fit pants variant. <br>0 = Susie Pant<br>1 = Shorter<br>2 = Bagi<br>3 = Duck<br>4 = White Pant<br>5 = Gray Pants<br>6 = Blackpants2<br></td>
    </tr>
    <tr>
      <td>1424</td>
      <td>THRASH_FIT_HAT - Hat -</td>
      <td>map</td>
      <td>Thrash Fit hat variant. <br>0 = No Hat<br>1 = Casual Hat<br>2 = Second Hat<br>3 = Tiara<br>4 = Silk<br></td>
    </tr>
    <tr>
      <td>1425</td>
      <td>THRASH_FIT_SHOES - Shoes -</td>
      <td>map</td>
      <td>Thrash Fit shoes variant. <br>0 = Susie Shoesy<br>1 = Brown Leg<br>2 = Black Flats<br>3 = Duck<br>4 = Glass Shoes<br>5 = Brown Shoe<br>6 = Blackshoes3<br></td>
    </tr>
    <tr>
      <td>1435</td>
      <td>TALKED_TORIEL_TOAST_REQUEST - Toriel toast request -</td>
      <td>map</td>
      <td>Toriel toast request answer. <br>0 = Default state<br>1 = Yes<br>2 = I'm busy<br></td>
    </tr>
    <tr>
      <td>1438</td>
      <td>LOOKED_AT_MICROWAVE - Looked at microwave -</td>
      <td>bool</td>
      <td>Looked at microwave while it was running. <br></td>
    </tr>
    <tr>
      <td>1440</td>
      <td>CASTLE_CLIMB_HISCORE - Castle climb high score -</td>
      <td>number</td>
      <td>Castle Town climbing minigame high score. <br></td>
    </tr>
    <tr>
      <td>1443</td>
      <td>SEEN_HOW_TO_DRAW_DRAGONS - Seen "How To Draw Dragons" -</td>
      <td>bool</td>
      <td>Seen "How To Draw Dragons" inside the drawer. <br></td>
    </tr>
    <tr>
      <td>1500</td>
      <td>MONEYFOUNTAIN_DONATION_OVER_100 - $100 Reward -</td>
      <td>bool</td>
      <td>Donated at least 100 Dark Dollars to the money fountain. <br></td>
    </tr>
    <tr>
      <td>1501</td>
      <td>CANDY_BOWL_PROGRESS - Cutscene -</td>
      <td>map</td>
      <td>Tracks your progress in the candy bowl cutscene. <br>0 = Default state<br>1 = Approached candy bowl<br>2 = Spilled candy bowl<br></td>
    </tr>
    <tr>
      <td>1502</td>
      <td>RIPPLE_WORSHIP_PROGRESS - Ripple progress -</td>
      <td>map</td>
      <td>Tracks your progress in the ripple worship room. <br>0 = Default state<br>1 = Opened the north path<br>2 = Revealed the piano notes<br></td>
    </tr>
    <tr>
      <td>1503</td>
      <td>GERSON_TEA_FINISHED - Organikk at fountain -</td>
      <td>bool</td>
      <td>Finished the tea party with Gerson. <br></td>
    </tr>
    <tr>
      <td>1504</td>
      <td>INTERACTED_WITH_CHURCH_CUPBOARD - Checked the church cupboard -</td>
      <td>bool</td>
      <td>Interacted with the cupboard while looking for the code to the church's locked door. <br></td>
    </tr>
    <tr>
      <td>1505</td>
      <td>INTERACTED_WITH_CHURCH_BOOKS - Checked the church books -</td>
      <td>bool</td>
      <td>Interacted with the books while looking for the code to the church's locked door. <br></td>
    </tr>
    <tr>
      <td>1506</td>
      <td>INTERACTED_WITH_CHURCH_CANDLES - Checked the church candles -</td>
      <td>bool</td>
      <td>Interacted with the candles before going inside. <br></td>
    </tr>
    <tr>
      <td>1507</td>
      <td>WHO_KRIS_PRAYED_FOR - Prayer target -</td>
      <td>map</td>
      <td>Who you decided to pray for in front of the hope candles. <br>0 = Default state<br>1 = Pray for Susie<br>2 = Pray for Noelle<br>3 = Pray for Asriel<br></td>
    </tr>
    <tr>
      <td>1508</td>
      <td>INTERACTED_WITH_CHURCH_BOOKSHELF - Checked the church bookshelf -</td>
      <td>bool</td>
      <td>Interacted with the bookshelf while looking for the code to the church's locked door. <br></td>
    </tr>
    <tr>
      <td>1509</td>
      <td>WHAT_CANDLES_ARE_FOR - Candles answer -</td>
      <td>map</td>
      <td>What you told Susie when she asked if the candles were for birthdays. <br>0 = Default state<br>1 = That's right<br>2 = Prayer<br></td>
    </tr>
    <tr>
      <td>1510</td>
      <td>OPENED_CHURCH_CLOSET - Opened the church closet -</td>
      <td>bool</td>
      <td>Viewed the cutscene of opening the church closet and getting jumpscared by Jackenstein. <br></td>
    </tr>
    <tr>
      <td>1511</td>
      <td>LISTENED_SUSIE_PIANO_STORY - Piano story -</td>
      <td>map</td>
      <td>Viewed the cutscene of Susie telling her story about smashing a piano. <br>0 = Default state<br>1 = Listen (it might be long)<br>2 = Not now<br></td>
    </tr>
    <tr>
      <td>1512</td>
      <td>WILL_KRIS_PLAY_AGAIN - Piano story response -</td>
      <td>map</td>
      <td>What you told Susie after her piano story. Unaccessed as of chapter 4. <br>0 = Default state<br>1 = I'll play again someday<br>2 = If you play too<br>3 = I'll never play again<br></td>
    </tr>
    <tr>
      <td>1513</td>
      <td>TALKED_TO_JACKENSTEIN_IN_STUDY - Talked to Jackenstein in the study -</td>
      <td>bool</td>
      <td>Talked to Jackenstein in Gerson's study. <br></td>
    </tr>
    <tr>
      <td>1514</td>
      <td>WOULD_YOU_LIKE_SUGAR - Sugar -</td>
      <td>map</td>
      <td>What you said to Ralsei asking if you would like sugar during his tea party. <br>0 = Default state<br>1 = No<br>2 = Yes<br>3 = Two lumps please<br></td>
    </tr>
    <tr>
      <td>1515</td>
      <td>WHO_EATS_THE_CAKE - Who eats the cake? -</td>
      <td>map</td>
      <td>What you said to Ralsei after he said he never had cake before during his tea party. Unaccessed as of chapter 4. <br>0 = Default state<br>1 = Ralsei eat the cake<br>2 = That's my cake<br></td>
    </tr>
    <tr>
      <td>1516</td>
      <td>RALSEI_HAS_A_SURPRISE - Surprise -</td>
      <td>bool</td>
      <td>Whether Ralsei told you he had a surprise if we went into our rooms in Castle Town. <br></td>
    </tr>
    <tr>
      <td>1517</td>
      <td>OBTAINED_WORSHIP_CHEST - Got the worship-room chest -</td>
      <td>bool</td>
      <td>Got the Mystic Band / Power Band from the chest in the worship room. <br></td>
    </tr>
    <tr>
      <td>1519</td>
      <td>GERSON_TEA_FANCY_A_DRINK - Secret piano tea answer -</td>
      <td>map</td>
      <td>What you said when Gerson asked if you would fancy a drink. <br>0 = Default state<br>1 = Yes<br>2 = No<br>3 = We already had tea<br></td>
    </tr>
    <tr>
      <td>1521</td>
      <td>GERSON_TEA_DRINK_IT - Waterfall tea answer -</td>
      <td>map</td>
      <td>What you did after getting sugar in your tea with Gerson. <br>0 = Default state<br>1 = Drink it<br>2 = Don't drink it<br></td>
    </tr>
    <tr>
      <td>1523</td>
      <td>GERSON_TEA_ARE_YOU_SURE - Third tearoom answer -</td>
      <td>map</td>
      <td>What you said when Gerson asked you if you were sure you didn't want to have tea now. <br>0 = Default state<br>1 = Not now<br>2 = Actually I will have tea<br></td>
    </tr>
    <tr>
      <td>1524</td>
      <td>CLIMBING_CHALLENGE_FIRST_TIME - First time -</td>
      <td>number</td>
      <td>How fast you did the first climbing challenge. <br></td>
    </tr>
    <tr>
      <td>1525</td>
      <td>CLIMBING_CHALLENGE_SECOND_TIME - Second time -</td>
      <td>number</td>
      <td>How fast you did the second climbing challenge. <br></td>
    </tr>
    <tr>
      <td>1526</td>
      <td>AWAKENED_MIZZLE_PROGRESS - Mizzle progress -</td>
      <td>map</td>
      <td>Tracks the progress of awakening the Mizzle protected by the cups. <br>0 = Default state<br>1 = First cup started charging<br>2 = Mizzle left<br>3 = Started exiting (triggers shortened return path)<br></td>
    </tr>
    <tr>
      <td>1527</td>
      <td>FINISHED_NOELLE_HOUSE_WEIRD - Saw the Noelle-house Weird Route cutscene -</td>
      <td>bool</td>
      <td>Viewed the cutscene after coming out of the Noelle's house during the Weird Route. Unaccessed as of chapter 4. <br></td>
    </tr>
    <tr>
      <td>1528</td>
      <td>HOMETOWN_WEIRD_CUTSCENE_PROGRESS - Hometown cutscene -</td>
      <td>map</td>
      <td>Tracks the progress of the cutscene in the Weird Route when you walk with Susie in the rain. <br>0 = Default state<br>1 = Got dialogue near Sans' store<br>2 = Got dialogue near church<br></td>
    </tr>
    <tr>
      <td>1529</td>
      <td>BROKE_KNIGHT_PROPHECY - Broke the Knight prophecy -</td>
      <td>bool</td>
      <td>Broke the Knight prophecy in the north prophecies room. <br></td>
    </tr>
    <tr>
      <td>1530</td>
      <td>ACTIVATED_TRUE_CLIMB_LEFT_SHORTCUT - Activated the left shortcut -</td>
      <td>bool</td>
      <td>Rung the left bell to activate the left shortcut in the climbing room leading to the grand piano. <br></td>
    </tr>
    <tr>
      <td>1531</td>
      <td>TALKED_TO_NUBERT_CH4 - Talked to Nubert in Castle Town -</td>
      <td>bool</td>
      <td>Talked to Nubert in Castle Town in chapter 4. <br></td>
    </tr>
    <tr>
      <td>1532</td>
      <td>TALKED_TO_RUDINN_CH4 - Talked to Rudinn in Castle Town -</td>
      <td>bool</td>
      <td>Talked to Rudinn in Castle Town in chapter 4. <br></td>
    </tr>
    <tr>
      <td>1533</td>
      <td>SLEPT_THROUGH_SERVICE - Church sermon choice A -</td>
      <td>map</td>
      <td>Whether you chose to sleep through service at church. Unaccessed as of chapter 4. <br>0 = Default state<br>1 = Sleep through service<br>2 = Watch service<br></td>
    </tr>
    <tr>
      <td>1534</td>
      <td>WHAT_YOU_DID_DURING_SERVICE - Church sermon choice B -</td>
      <td>map</td>
      <td>What you chose to do during service at church. Unaccessed as of chapter 4. <br>0 = Default state<br>1 = Let's play attention<br>2 = Look in pocket for fun<br></td>
    </tr>
    <tr>
      <td>1535</td>
      <td>INTERACTED_WITH_CHURCH_CHOIR_DOOR - Checked the choir door -</td>
      <td>bool</td>
      <td>Interacted with the church's choir room's door before going inside. <br></td>
    </tr>
    <tr>
      <td>1536</td>
      <td>INTERACTED_WITH_CHURCH_OFFICE_DOOR - Checked the church office door -</td>
      <td>bool</td>
      <td>Interacted with the church's office's door before going inside. <br></td>
    </tr>
    <tr>
      <td>1537</td>
      <td>OBTAINED_MONEYFOUNTAIN_CHEST - Got the Money Fountain chest -</td>
      <td>bool</td>
      <td>Got the Darker Candy / Scarlixir / Revive Mint / Bitter Tear / Gold Widow from the chest in the money fountain room. <br></td>
    </tr>
    <tr>
      <td>1538</td>
      <td>MOVED_MOVABLE_PIANO - Moved the movable piano -</td>
      <td>bool</td>
      <td>Moved a movable piano. <br></td>
    </tr>
    <tr>
      <td>1539</td>
      <td>OBTAINED_LIBRARYCONNECTOR_CHEST - Got the library-connector chest -</td>
      <td>bool</td>
      <td>Got the Rhapsotea from the chest in the Second Sanctuary's library connector room. <br></td>
    </tr>
    <tr>
      <td>1540</td>
      <td>OBTAINED_LIBRARY_CHEST - Got the library chest -</td>
      <td>bool</td>
      <td>Got the Revive Mint from the chest in the Second Sanctuary's library. <br></td>
    </tr>
    <tr>
      <td>1541</td>
      <td>BREAKABLE_BOOKSHELVES_STATE_ALT - Breakable Bookshelves State Alt -</td>
      <td>number</td>
      <td>Tracks the state of the breakable bookshelves in the unused alternate Second Sanctuary's library. <br></td>
    </tr>
    <tr>
      <td>1543</td>
      <td>REMOVED_PIANO_AND_BOOKSHELVES - Removed the piano and bookshelves -</td>
      <td>bool</td>
      <td>Flag never set, but would have removed the moving piano and bookshelves in the Second Sanctuary's library. <br></td>
    </tr>
    <tr>
      <td>1544</td>
      <td>ALERTED_MIZZLES - Alerted the Mizzles -</td>
      <td>bool</td>
      <td>Prevented future Mizzles to start a battle tired, by ringing the bell or waking up an initially tired Mizzle. <br></td>
    </tr>
    <tr>
      <td>1545</td>
      <td>OBTAINED_GALLERY_CHEST - Got the gallery chest -</td>
      <td>bool</td>
      <td>Got 500 Dark Dollars from the chest in the Second Sanctuary's gallery. <br></td>
    </tr>
    <tr>
      <td>1547</td>
      <td>SOLVED_GOLDEN_PIANO - Solved the golden piano -</td>
      <td>bool</td>
      <td>Played the golden piano and opened the fireplace secret passage in Gerson's study. <br></td>
    </tr>
    <tr>
      <td>1548</td>
      <td>INTERACTED_WITH_FIREPLACE_MURAL - Checked the fireplace mural -</td>
      <td>bool</td>
      <td>Interacted with the mural in Gerson's study and read about the cool axe. <br></td>
    </tr>
    <tr>
      <td>1549</td>
      <td>TALKED_TO_GERSON_ABOUT_MAGIC_AXE - Talked Gerson About Magic Axe -</td>
      <td>bool</td>
      <td>Talked to Gerson in his study about the Magic Axe. <br></td>
    </tr>
    <tr>
      <td>1550</td>
      <td>OPENED_GERSON_CHASE_CHEST - Opened the Gerson-chase chest -</td>
      <td>bool</td>
      <td>Got the Scarlixir from the chest in the Gerson chase room. <br></td>
    </tr>
    <tr>
      <td>1551</td>
      <td>SHOULD_CHECK_ON_RALSEI - Should Check On Ralsei -</td>
      <td>map</td>
      <td>What you said to Susie when asked if you should check on Ralsei, after rain starts if you haven't returned to Castle Town in chapter 4 yet. <br>0 = Default state<br>1 = Yeah<br>2 = Nah<br></td>
    </tr>
    <tr>
      <td>1552</td>
      <td>TALKED_TO_NAPSTABLOOK_ABOUT_UNDYNE - Talked to Napstablook about Undyne -</td>
      <td>bool</td>
      <td>Talked to Napstablook about Undyne. <br></td>
    </tr>
    <tr>
      <td>1553</td>
      <td>TALKED_TO_NAPSTABLOOK_ABOUT_SHELTER - Talked to Napstablook about the shelter -</td>
      <td>bool</td>
      <td>Talked to Napstablook about the Shelter. <br></td>
    </tr>
    <tr>
      <td>1554</td>
      <td>TALKED_TO_CATTI_ABOUT_SUSIE_IN_CHURCH - Talked to Catti about Susie in church -</td>
      <td>bool</td>
      <td>Talked to Catti about Susie. <br></td>
    </tr>
    <tr>
      <td>1555</td>
      <td>KRIS_SUSIE_LOCKED_OUT - Locked Kris and Susie out -</td>
      <td>bool</td>
      <td>Tried to enter Kris's house after rain started and realized it's locked. <br></td>
    </tr>
    <tr>
      <td>1556</td>
      <td>INTERACTED_WITH_GERSON_REMAINS - Checked Gerson's remains -</td>
      <td>bool</td>
      <td>Interacted with the glass container containing Gerson's remains after the cutscene where it's discovered. <br></td>
    </tr>
    <tr>
      <td>1557</td>
      <td>WHY_WE_SHOULD_ENTER_CHURCH - Why We Should Enter Church -</td>
      <td>map</td>
      <td>What you said to Susie after she suggested waiting outside the church's Dark World. Unaccessed as of chapter 4. <br>0 = Default state<br>1 = But we aren't logical<br>2 = But Mom could be in there<br></td>
    </tr>
    <tr>
      <td>1558</td>
      <td>NOELLE_BEDROOM_ASGORE_CURRENT_LINE - Asgore line -</td>
      <td>map</td>
      <td>Tracks the current line in the Asgore cutscene in Carol's bedroom. <br>0 = Default state<br>1 = We're almost there, aren't we, old friend?<br>2 = This time for sure... Tori will finally see.<br>3 = ... see what really happened.<br>4 = ... that I just wanted to... protect everyone...<br>5 = And this time, she'll have to believe me.<br>6 = ... they all will.<br>7 = Then...<br>8 = We'll all be a happy family again... won't we?<br>9 = ...<br>10 = It sure is beautiful, isn't it...?<br>11 = ... this black shard.<br></td>
    </tr>
    <tr>
      <td>1559</td>
      <td>KEPT_NOELLE_WAITING - Kept waiting -</td>
      <td>map</td>
      <td>Whether you did something after opening the gate at Noelle's house while she was waiting for you. <br>0 = Default state<br>1 = Had tea party with Ralsei<br>2 = Had diner with Susie<br></td>
    </tr>
    <tr>
      <td>1560</td>
      <td>GALLERY_CUTSCENE_PROGRESS - Gallery Cutscene Progress -</td>
      <td>number</td>
      <td>Tracks the progress of the unused Second Sanctuary's gallery cutscene. Mostly reused for the rotating tower monologue. <br></td>
    </tr>
    <tr>
      <td>1561</td>
      <td>PLAYED_MEGALOVANIA - Played MEGALOVANIA -</td>
      <td>bool</td>
      <td>Tried playing Megalovania on the piano and got ran over by the Annoying Dog. <br></td>
    </tr>
    <tr>
      <td>1562</td>
      <td>SEARCHED_DESS_BELONGINGS - Searched Dess's belongings -</td>
      <td>bool</td>
      <td>Dug through Dess' stuff in her room. <br></td>
    </tr>
    <tr>
      <td>1563</td>
      <td>TALKED_TO_NOELLE_AFTER_PHONE_THROW - Talked to Noelle after throwing away the phone -</td>
      <td>bool</td>
      <td>Talked to Noelle after Susie threw her phone. <br></td>
    </tr>
    <tr>
      <td>1564</td>
      <td>TALKED_TO_SUSIE_AFTER_PHONE_THROW - Talked to Susie after throwing away the phone -</td>
      <td>bool</td>
      <td>Talked to Susie after she threw Noelle's phone. <br></td>
    </tr>
    <tr>
      <td>1565</td>
      <td>ASKED_ASGORE_ABOUT_OUTFIT - Asked Asgore about outfit -</td>
      <td>bool</td>
      <td>Asked Asgore about his outfit after coming out of Noelle's house. <br></td>
    </tr>
    <tr>
      <td>1566</td>
      <td>ASKED_ASGORE_IF_OKAY - Asked Asgore if okay -</td>
      <td>bool</td>
      <td>Asked Asgore if he's okay after coming out of Noelle's house. <br></td>
    </tr>
    <tr>
      <td>1567</td>
      <td>PRESSED_KNIGHTCLIMBPOST_SWITCH - Pressed the Knight-climb bridge switch -</td>
      <td>bool</td>
      <td>Pressed the switch making a bridge at the end of the Second Sanctuary. <br></td>
    </tr>
    <tr>
      <td>1569</td>
      <td>SUSIE_LEARNED_BETTER_HEAL - Taught Susie BetterHeal -</td>
      <td>bool</td>
      <td>Whether Susie's OKHeal spell improved to BetterHeal, by winning against Gerson or starting the fight against the Sound of Justice. <br></td>
    </tr>
    <tr>
      <td>1570</td>
      <td>INTERACTED_WITH_ITEM_FOUNTAIN - Used the item fountain -</td>
      <td>bool</td>
      <td>Interacted with the item fountain in Gerson's study. <br></td>
    </tr>
    <tr>
      <td>1571</td>
      <td>ACTIVATED_TRUE_CLIMB_RIGHT_SHORTCUT - Activated the right shortcut -</td>
      <td>bool</td>
      <td>Rung the right bell to activate the right shortcut in the climbing room leading to the grand piano. <br></td>
    </tr>
    <tr>
      <td>1572</td>
      <td>SUSIE_BELLROOM_PROGRESS - Susie Bellroom Progress -</td>
      <td>map</td>
      <td>Tracks the progress of Susie in the bell room cutscene. <br>0 = Default state<br>1 = Moved to first point<br>2 = Moved to second point<br></td>
    </tr>
    <tr>
      <td>1573</td>
      <td>WINDOWS_LOOPED - Window loops -</td>
      <td>number</td>
      <td>Number of loops done in the Sanctuary's window room. At 8, the Egg door appears. <br></td>
    </tr>
    <tr>
      <td>1574</td>
      <td>INTERACTED_WITH_TV_BROKEN - Checked the broken TV -</td>
      <td>bool</td>
      <td>Interacted with the TV at Kris's house, if it wasn't repaired. <br></td>
    </tr>
    <tr>
      <td>1575</td>
      <td>SUGGESTED_TENNA_TO_METTATON - Suggested Tenna -</td>
      <td>bool</td>
      <td>Suggested Tenna to Mettaton, if it wasn't repaired. <br></td>
    </tr>
    <tr>
      <td>1576</td>
      <td>INTERACTED_WITH_TV_FIXED - Checked the fixed TV -</td>
      <td>bool</td>
      <td>Interacted with the TV at Kris's house, if it was repaired. <br></td>
    </tr>
    <tr>
      <td>1577</td>
      <td>TALKED_TO_SWATCH_IN_CAFE - Talked to Swatch -</td>
      <td>bool</td>
      <td>Talked to Swatch in the Cafe, if you've recruited Tasque Manager, Tasque and Shadowguy. <br></td>
    </tr>
    <tr>
      <td>1578</td>
      <td>TALKED_TO_JIGSAW_JOE_IN_LOVE_DOJO - Talked to Jigsaw Joe -</td>
      <td>bool</td>
      <td>Talked to Jigsaw Joe now that the dojo has become the Love Dojo. <br></td>
    </tr>
    <tr>
      <td>1579</td>
      <td>MADE_NOISE_IN_NOELLE_HOUSE_COUNT - Noise count -</td>
      <td>number</td>
      <td>Number of times you touched a dancing Santa or a bell and made noise in Noelle's house. <br></td>
    </tr>
    <tr>
      <td>1580</td>
      <td>LEVEL_UP_COUNT_CH4 - Times Leveled -</td>
      <td>number</td>
      <td>The number of times you have leveled up by violently defeating an encounter. Used for certain increases that only occur every 2, 4, or 10 encounters. <br></td>
    </tr>
    <tr>
      <td>1581</td>
      <td>OBTAINED_PROPHECYMAZE_CHEST - Got the prophecy-maze chest -</td>
      <td>bool</td>
      <td>Got the Scarlixir from the chest in the Second Sanctuary's statue maze room. <br></td>
    </tr>
    <tr>
      <td>1582</td>
      <td>OPENED_BOOKSHELF_PUZZLE_CHEST - Opened the bookshelf-puzzle chest -</td>
      <td>bool</td>
      <td>Got the Absorb Ax from the chest in the bookshelf puzzle room. <br></td>
    </tr>
    <tr>
      <td>1583</td>
      <td>SPAWN_CLOUD_DEATH_COUNT - Times Killed By Spawncloud -</td>
      <td>map</td>
      <td>Number of times you died from the spawns chasing you vertically (used to reduce their speed). <br>0 = Default state<br>1 = Died once<br>2 = Died twice<br>3 = Died thrice or more<br></td>
    </tr>
    <tr>
      <td>1584</td>
      <td>BREAKABLE_BOOKSHELVES_STATE - Bookshelves -</td>
      <td>number</td>
      <td>Tracks the state of the breakable bookshelves in the Second Sanctuary's library. <br></td>
    </tr>
    <tr>
      <td>1585</td>
      <td>MOVING_PIANO_XY - Piano coordinates -</td>
      <td>number</td>
      <td>Combination of X and Y coordinates of the moving piano. <br></td>
    </tr>
    <tr>
      <td>1586</td>
      <td>OBTAINED_RIGHTCONNECT_CHEST - Got the right-connector chest -</td>
      <td>bool</td>
      <td>Got the Winglade from the chest in the room on the right of Gerson's study. <br></td>
    </tr>
    <tr>
      <td>1587</td>
      <td>OBTAINED_MINORLEGEND_CHEST - Got the Minor Legend chest -</td>
      <td>bool</td>
      <td>Got the Rhapsotea from the chest in the Jockington prophecy room. <br></td>
    </tr>
    <tr>
      <td>1588</td>
      <td>OPENED_RIGHT_PIANO_PIECE_CHEST - Opened the right piano-piece chest -</td>
      <td>bool</td>
      <td>Got the Revive Mint from the chest in the right piano piece room. <br></td>
    </tr>
    <tr>
      <td>1589</td>
      <td>OPENED_TRUE_CLIMB_CHEST - Opened the True Climb chest -</td>
      <td>bool</td>
      <td>Got the Tension Gem from the chest in the climbing room. <br></td>
    </tr>
    <tr>
      <td>1590</td>
      <td>OBTAINED_JACKENSTEIN_CHEST - Got the Jackenstein chest -</td>
      <td>bool</td>
      <td>Got 500 Dark Dollars from the chest in the Jackenstein room. <br></td>
    </tr>
    <tr>
      <td>1591</td>
      <td>RALSEI_BLOODY_FACE - Bloody face -</td>
      <td>bool</td>
      <td>Whether Ralsei got blood on his face from Susie at the end of chapter 4. <br></td>
    </tr>
    <tr>
      <td>1592</td>
      <td>MOSS_OUTCOME_CH4 - Moss -</td>
      <td>map</td>
      <td>Whether you got the moss in chapter 4. <br>0 = Default state<br>1 = Consumed with gusto<br>2 = Left for the next person<br></td>
    </tr>
    <tr>
      <td>1593</td>
      <td>CHECKED_GERSON_TABLE_SECOND_SANCTUARY - Interacted Gerson Table Second Sanctuary -</td>
      <td>map</td>
      <td>Interacted with the table in Gerson's study in the Second Sanctuary. <br>0 = Default state<br>1 = Tried to take items<br>2 = Didn't try to take items<br></td>
    </tr>
    <tr>
      <td>1594</td>
      <td>RHAPSOTEA_EXTRA_DOLLARS - Rhapsotea Extra Dollars -</td>
      <td>number</td>
      <td>Number of dollars paid extra for the Rhapsoteas in Gerson's study in the Second Sanctuary. <br></td>
    </tr>
    <tr>
      <td>1595</td>
      <td>WAFER_ROOM_STATE - Room state -</td>
      <td>map</td>
      <td>Tracks your progression in obtaining the Third Sanctuary Waferguard chest. See also flag 1616. <br>0 = Default state<br>1 = Revealed chest<br>2 = Wafer obtained, area locked (nothing more to do, so the game has blocked off the area)<br></td>
    </tr>
    <tr>
      <td>1596</td>
      <td>SAW_ANGEL_PROPHECY - Saw the Angel prophecy -</td>
      <td>bool</td>
      <td>Viewed the cutscene of the gang looking at the angel prophecy. <br></td>
    </tr>
    <tr>
      <td>1597</td>
      <td>PURIFIED_COUNT - Purified -</td>
      <td>number</td>
      <td>Number of Titan spawns purified. The Purify ACT will always add two to this flag, even if you've already slain one. <br></td>
    </tr>
    <tr>
      <td>1598</td>
      <td>SLAIN_COUNT - Slain -</td>
      <td>number</td>
      <td>Number of Titan spawns slain. <br></td>
    </tr>
    <tr>
      <td>1599</td>
      <td>INTERACTED_WITH_CUPSTACK_LIFT - Used the cup-stack lift -</td>
      <td>bool</td>
      <td>Interacted with the cup stack lift. <br></td>
    </tr>
    <tr>
      <td>1600</td>
      <td>CHECKED_GERSON_STUDY_SAVE_POINT - Save point -</td>
      <td>map</td>
      <td>Interacted with the save point in Gerson's study. <br>0 = Default state<br>1 = First interaction<br>2 = Second interaction if mural wasn't checked yet<br></td>
    </tr>
    <tr>
      <td>1601</td>
      <td>INTERACTED_WITH_NORTHWEST_CONNECTOR_SAVE_POINT - Used the northwest-connector save point -</td>
      <td>bool</td>
      <td>Interacted with the save point in the north-west connector room. <br></td>
    </tr>
    <tr>
      <td>1602</td>
      <td>INTERACTED_WITH_PIANO_PUZZLE_SAVE_POINT - Used the piano-puzzle save point -</td>
      <td>bool</td>
      <td>Interacted with the save point in the piano puzzle room before Jackenstein. <br></td>
    </tr>
    <tr>
      <td>1603</td>
      <td>CHECKED_THIRD_SANCTUARY_MUSIC_SAVE_POINT - Interacted Superprophecies Savepoint -</td>
      <td>bool</td>
      <td>Interacted with the save point in the room where the Third Sanctuary music starts playing. <br></td>
    </tr>
    <tr>
      <td>1604</td>
      <td>GERSON_LEFT_ROOM_WITHOUT_OTHERS - Left Gerson's room without the others -</td>
      <td>bool</td>
      <td>Talked to Gerson after his walk is completed without Susie running ahead. <br></td>
    </tr>
    <tr>
      <td>1605</td>
      <td>ASKED_GERSON_ABOUT_KNIGHT_AFTER_SHEET_MUSIC - Talked Gerson Postsheet Knight -</td>
      <td>bool</td>
      <td>Talked to Gerson in his study about the Knight after using the sheet music. <br></td>
    </tr>
    <tr>
      <td>1606</td>
      <td>THIRD_SANCTUARY_MISSED_SOMETHING_RESPONSE - Missed-something response -</td>
      <td>map</td>
      <td>Your interaction when asked if you missed something on the other side of your mind. <br>0 = Default state<br>1 = Didn't miss anything (while not having the Egg)<br>2 = Already have the Egg<br></td>
    </tr>
    <tr>
      <td>1607</td>
      <td>ASKED_GERSON_ABOUT_HIS_WORK_AFTER_JACKENSTEIN - Talked Gerson Postjack Letter -</td>
      <td>bool</td>
      <td>Talked to Gerson in his study and asked him what he's doing after healing Jackenstein and before getting the sheet music. <br></td>
    </tr>
    <tr>
      <td>1608</td>
      <td>ASKED_GERSON_ABOUT_HIS_WORK_AFTER_SHEET_MUSIC - Talked Gerson Postsheet Letter -</td>
      <td>bool</td>
      <td>Talked to Gerson in his study and asked him what he's doing after getting the sheet music. <br></td>
    </tr>
    <tr>
      <td>1609</td>
      <td>TRIGGERED_FIRST_SANCTUARY_INTRO_TEMP_SAVE - Triggered the First Sanctuary temporary save -</td>
      <td>bool</td>
      <td>Entered the room with the prophecies at the start of the First Sanctuary (makes a temporary save). <br></td>
    </tr>
    <tr>
      <td>1610</td>
      <td>OBTAINED_PROPHECIES_CHEST - Got the prophecies chest -</td>
      <td>bool</td>
      <td>Got the Princess Ribbon from the chest next to the Tail of Hell prophecy. <br></td>
    </tr>
    <tr>
      <td>1611</td>
      <td>RETURNED_SECOND_JOCKINGTON_PROPHECY - Returned Second Jockington Prophecy -</td>
      <td>bool</td>
      <td>Returned from the second Jockington prophecy room in the Third Sanctuary. Unaccessed as of chapter 4. <br></td>
    </tr>
    <tr>
      <td>1612</td>
      <td>CHECKED_GERSON_TABLE_FIRST_SANCTUARY - Checked Gerson's table in the First Sanctuary -</td>
      <td>bool</td>
      <td>Interacted with the table in Gerson's study in the First Sanctuary. <br></td>
    </tr>
    <tr>
      <td>1613</td>
      <td>CHECKED_GERSON_TABLE_THIRD_SANCTUARY - Interacted Gerson Table Third Sanctuary -</td>
      <td>bool</td>
      <td>Interacted with the table in Gerson's study in the Third Sanctuary. <br></td>
    </tr>
    <tr>
      <td>1614</td>
      <td>OBTAINED_ENCOUNTER2_CHEST - Got the second-encounter chest -</td>
      <td>bool</td>
      <td>Got 100 Dark Dollars from the chest in the Third Sanctuary's dark maze room. Inaccessible as there isn't actually a chest in this room. <br></td>
    </tr>
    <tr>
      <td>1615</td>
      <td>STARTED_THIRD_SANCTUARY_MUSIC - Started the Third Sanctuary music -</td>
      <td>bool</td>
      <td>Entered the room where the Third Sanctuary music plays. <br></td>
    </tr>
    <tr>
      <td>1616</td>
      <td>OBTAINED_TREASURE_CHEST - Got the treasure chest -</td>
      <td>bool</td>
      <td>Got the Wafer Guard from the chest in the Third Sanctuary's treasure chest room. <br></td>
    </tr>
    <tr>
      <td>1617</td>
      <td>INTERACTED_WITH_USELESS_GLOVES - Checked the useless gloves -</td>
      <td>bool</td>
      <td>Interacted with the hidden chest with the gloves that make you worse at climbing. <br></td>
    </tr>
    <tr>
      <td>1618</td>
      <td>AT_MAGIC_GAIN_COUNT_CH4 - Times Gained AT -</td>
      <td>number</td>
      <td>The number of times your AT and Magic have increased due to leveling up (every ten encounters). <br></td>
    </tr>
    <tr>
      <td>1619</td>
      <td>CHURCH_CLUES_GATHERED - Clues gathered -</td>
      <td>map</td>
      <td>Number of clues gathered at church. <br>0 = Default state<br>1 = 1 clue<br>2 = 2 clues, ready to tell Susie<br></td>
    </tr>
    <tr>
      <td>1620</td>
      <td>OBTAINED_NOELLE_CLUE - Got Noelle's clue -</td>
      <td>bool</td>
      <td>Talked to Noelle about the locked door at church. <br></td>
    </tr>
    <tr>
      <td>1621</td>
      <td>OBTAINED_ALPHYS_CLUE - Got Alphys's clue -</td>
      <td>bool</td>
      <td>Talked to Alphys about the shelter at church. <br></td>
    </tr>
    <tr>
      <td>1622</td>
      <td>WASHED_HANDS_THERAPY - Washed hands during therapy -</td>
      <td>bool</td>
      <td>Used the sink to wash your hands after getting the Egg in chapter 4. Unaccessed as of chapter 4. <br></td>
    </tr>
    <tr>
      <td>1623</td>
      <td>GLASS_NOELLE_WHISPERING - Glass whisper -</td>
      <td>bool</td>
      <td>Used the Glass in Noelle's house in chapter 4. <br></td>
    </tr>
    <tr>
      <td>1624</td>
      <td>SHADOW_SANCTUARY - Sanctuary -</td>
      <td>bool</td>
      <td>Used the Shadow Crystal in the Sanctuary. <br></td>
    </tr>
    <tr>
      <td>1625</td>
      <td>SHADOW_FINAL_PROPHECY - Final prophecy -</td>
      <td>bool</td>
      <td>Used the Shadow Crystal in front of the final prophecy in the Third Sanctuary. <br></td>
    </tr>
    <tr>
      <td>1626</td>
      <td>SHADOW_FAILED_CH4 - Failed -</td>
      <td>bool</td>
      <td>Whether you used the Shadow Crystal in Chapter 4 and saw nothing. 1624 and 1625 are more interesting. <br></td>
    </tr>
    <tr>
      <td>1627</td>
      <td>PRESENTS_CHECKED - Presents -</td>
      <td>number</td>
      <td>Number of presents checked in Noelle's present room. <br></td>
    </tr>
    <tr>
      <td>1628</td>
      <td>CHAIR_SKIP_CH4 - Chair skip -</td>
      <td>bool</td>
      <td>Whether you used the chair to skip to the First Sanctuary in chapter 4. <br></td>
    </tr>
    <tr>
      <td>1629</td>
      <td>STARTED_GERSON_BATTLE - Started Gerson's battle -</td>
      <td>bool</td>
      <td>Started the battle against Gerson. <br></td>
    </tr>
    <tr>
      <td>1630</td>
      <td>TALKED_TO_MALIUS_ABOUT_NEW_FUSIONS - Talked to Malius about new fusions -</td>
      <td>bool</td>
      <td>Talked to Malius at the Bakery about NEW FUSIONS. <br></td>
    </tr>
    <tr>
      <td>1631</td>
      <td>SELECTED_MALIUS_LEAVE_OPTION - Talked Malius Leave -</td>
      <td>bool</td>
      <td>Selected Malius's Leave dialogue option in chapter 4. <br></td>
    </tr>
    <tr>
      <td>1632</td>
      <td>TALKED_TO_MALIUS_CH4 - Talked to Malius -</td>
      <td>bool</td>
      <td>Talked to Malius at the Bakery in chapter 4. <br></td>
    </tr>
    <tr>
      <td>1633</td>
      <td>TALKED_TO_TOPCHEF_CH4 - Talked to Topchef -</td>
      <td>bool</td>
      <td>Talked to Top Chef at the Bakery in chapter 4, if not currently eligible for a SpinCake. <br></td>
    </tr>
    <tr>
      <td>1634</td>
      <td>SPOOKY_HAND_PUSHED_BACK - Pushed back the Spooky Hand -</td>
      <td>bool</td>
      <td>Tried to go back after the final prophecy cutscene, and was pushed back by a mysterious hand out of view. <br></td>
    </tr>
    <tr>
      <td>1635</td>
      <td>KNOCKED_EAST_DOOR_END_CH4 - Knocked on the east door -</td>
      <td>bool</td>
      <td>Knocked on the door at the east of Hometown at the end of chapter 4. <br></td>
    </tr>
    <tr>
      <td>1636</td>
      <td>RUN_REMINDER_CH4 - Run Reminder -</td>
      <td>bool</td>
      <td>Whether Susie reminded you you can run at the start of Chapter 4. <br></td>
    </tr>
    <tr>
      <td>1637</td>
      <td>PUMPKIN_PROGRESS - Pumpkin Progress -</td>
      <td>map</td>
      <td>Tracks the progress of Ralsei's interaction with the pumpkin NPC after the Jackenstein battle. <br>0 = Default state<br>1 = Told a joke<br>2 = Told a story<br></td>
    </tr>
    <tr>
      <td>1638</td>
      <td>OBTAINED_DOGCLIMB_CHEST - Got the dog-climb chest -</td>
      <td>bool</td>
      <td>Got the Dog Dollar from the chest in the Annoying Dog climbing race room. <br></td>
    </tr>
    <tr>
      <td>1639</td>
      <td>USED_PARTY_ACTION_ON_GUEI - Used the party ACT on Guei -</td>
      <td>bool</td>
      <td>Used S-Action or R-Action during the first Guei encounter, or was reminded if you didn't. <br></td>
    </tr>
    <tr>
      <td>1640</td>
      <td>TITAN_ATTEMPT_COUNT - Attempts -</td>
      <td>number</td>
      <td>Number of times you fought the Titan. <br></td>
    </tr>
    <tr>
      <td>1641</td>
      <td>SOUND_OF_JUSTICE_ATTEMPT_COUNT - Attempts -</td>
      <td>number</td>
      <td>Number of times you fought the Sound of Justice. <br></td>
    </tr>
    <tr>
      <td>1642</td>
      <td>FINISHED_ANNOYING_DOG_RACE - Finished the Annoying Dog race -</td>
      <td>bool</td>
      <td>Finished the climbing race against the Annoying Dog. <br></td>
    </tr>
    <tr>
      <td>1643</td>
      <td>ENTERED_NOELLE_KITCHEN_COUNT - Entry count -</td>
      <td>number</td>
      <td>Number of times you entered Noelle's kitchen while being in the vent. Maximum 3. <br></td>
    </tr>
    <tr>
      <td>1644</td>
      <td>TOOK_SHADOW_CRYSTAL_IN_CLIFF - Took the Shadow Crystal at the cliff -</td>
      <td>bool</td>
      <td>Whether there is a Shadow Crystal to grab in the left cliff. Also requires other save data. <br></td>
    </tr>
    <tr>
      <td>1645</td>
      <td>UNLOCKED_MIKE_ZONE_DOOR - Unlocked the Mike Zone door -</td>
      <td>bool</td>
      <td>Unlocked the Mike zone door using the 6453 combination. <br></td>
    </tr>
    <tr>
      <td>1646</td>
      <td>OBTAINED_SHADOW_CRYSTAL_CH1 - Got the Shadow Crystal -</td>
      <td>bool</td>
      <td>Obtained the Shadow Crystal from Jevil in chapter 1. <br></td>
    </tr>
    <tr>
      <td>1647</td>
      <td>OBTAINED_SHADOW_CRYSTAL_CH2 - Got the Shadow Crystal -</td>
      <td>bool</td>
      <td>Obtained the Shadow Crystal from Spamton NEO in chapter 2. <br></td>
    </tr>
    <tr>
      <td>1648</td>
      <td>OBTAINED_SHADOW_CRYSTAL_CH3 - Got the Shadow Crystal -</td>
      <td>bool</td>
      <td>Obtained the Shadow Crystal from the Knight in chapter 3. <br></td>
    </tr>
    <tr>
      <td>1649</td>
      <td>OBTAINED_SHADOW_CRYSTAL_CH4 - Got the Shadow Crystal -</td>
      <td>bool</td>
      <td>Obtained the Shadow Crystal from Gerson in chapter 4. <br></td>
    </tr>
    <tr>
      <td>1650</td>
      <td>TALKED_TO_CUP_STACK_DURING_FINAL_CLIMB - Talked Cupstack Finalclimb -</td>
      <td>bool</td>
      <td>Talked to the cup stack in the fragile tower room. <br></td>
    </tr>
    <tr>
      <td>1651</td>
      <td>TEMMIE_SONG_LINE - Song line -</td>
      <td>map</td>
      <td>Tracks the current line of Temmie singing Don't forget in Alphys' classroom. <br>0 = When the light is running low<br>1 = And the shadows start to grow<br>2 = And the places that you know<br>3 = Seem like fantasy<br></td>
    </tr>
    <tr>
      <td>1652</td>
      <td>TALKED_TO_GERSON_AFTER_BATTLE - Talked to Gerson after the battle -</td>
      <td>bool</td>
      <td>Talked to Gerson in his study after defeating him and before saying goodbye to him. <br></td>
    </tr>
    <tr>
      <td>1654</td>
      <td>INTERACTED_WITH_CHAIRIEL_SUSIE - Interacted with Chairiel with Susie -</td>
      <td>bool</td>
      <td>Interacted with Chairiel in front of Susie. <br></td>
    </tr>
    <tr>
      <td>1655</td>
      <td>FIRST_ADDED_JUICE - First juice -</td>
      <td>bool</td>
      <td>Added juice to your glass at least once at church. <br></td>
    </tr>
    <tr>
      <td>1656</td>
      <td>WEIRD_ROUTE_FAIL_CH4 - Weird Route Fail -</td>
      <td>bool</td>
      <td>Aborted the Weird Route during chapter 4. Unaccessed as of chapter 4. <br></td>
    </tr>
    <tr>
      <td>1657</td>
      <td>TALKED_TO_RUDY_AT_CHURCH_WEIRD_ROUTE - Talked Rudy Church Weird -</td>
      <td>bool</td>
      <td>Talked to Rudy at church during the Weird Route. <br></td>
    </tr>
    <tr>
      <td>1658</td>
      <td>MIKE_PORTAL_UNLOCKED - Portal unlocked -</td>
      <td>bool</td>
      <td>Unlocked the way back to Castle Town by finishing chapter 4 and returning to the Third Sanctuary. <br></td>
    </tr>
    <tr>
      <td>1659</td>
      <td>MIKE_PORTAL_CUTSCENE - Cutscene -</td>
      <td>bool</td>
      <td>Viewed the cutscene of the pillar of light in the Third Sanctuary. <br></td>
    </tr>
    <tr>
      <td>1660</td>
      <td>MIKE_PORTAL_RETURN_CHOICE - Return choice -</td>
      <td>bool</td>
      <td>Chose or not to return to Castle Town after getting to the pillar of light for the first time. <br></td>
    </tr>
    <tr>
      <td>1661</td>
      <td>MIKE_PORTAL_TRIP_COUNT - Trips -</td>
      <td>number</td>
      <td>How many times Kris went into the pillar of light to come back to Castle Town. <br></td>
    </tr>
    <tr>
      <td>1663</td>
      <td>INTERACTED_WITH_MICROPHONE_CRYSTAL - Used the microphone crystal -</td>
      <td>bool</td>
      <td>Interacted with the microphone crystal in the Mike zone. <br></td>
    </tr>
    <tr>
      <td>1664</td>
      <td>CHECKED_KRIS_ROOM_SAVE_POINT - Used the save point in Kris's room -</td>
      <td>bool</td>
      <td>Interacted with the save point in Kris's room. <br></td>
    </tr>
    <tr>
      <td>1665</td>
      <td>INTERACTED_WITH_RUDY_FLOWERS_CH4 - Checked Rudy's flowers -</td>
      <td>bool</td>
      <td>Interacted with the flowers in Rudy's hospital room in chapter 4. <br></td>
    </tr>
    <tr>
      <td>1666</td>
      <td>TV_TIME_HISCORE - It's TV Time! Hiscore -</td>
      <td>number</td>
      <td>Score on the It's TV Time! rhythm game <br></td>
    </tr>
    <tr>
      <td>1667</td>
      <td>TV_TIME_HARD_HISCORE - It's TV Time! Hard Hiscore -</td>
      <td>number</td>
      <td>Score on the It's TV Time! rhythm game, Hard Mode <br></td>
    </tr>
    <tr>
      <td>1668</td>
      <td>KNOCK_YOU_DOWN_HISCORE - Knock You Down!! Hiscore -</td>
      <td>number</td>
      <td>Score on the Knock You Down!! rhythm game <br></td>
    </tr>
    <tr>
      <td>1669</td>
      <td>KNOCK_YOU_DOWN_HARD_HISCORE - Knock You Down!! Hard Hiscore -</td>
      <td>number</td>
      <td>Score on the Knock You Down!! rhythm game, Hard Mode <br></td>
    </tr>
    <tr>
      <td>1688</td>
      <td>JUSTICE_AXE_REWARD_STATE - Justice Axe -</td>
      <td>map</td>
      <td>Got the Justice Axe after winning against Gerson. <br>0 = Default state<br>1 = Got the axe<br>2 = Won the fight with inventory full<br></td>
    </tr>
    <tr>
      <td>1689</td>
      <td>ENTERED_MIKE_ZONE_ACCOMPANIED - Entered with party -</td>
      <td>bool</td>
      <td>Went past the Mike locked door with Susie and Ralsei. <br></td>
    </tr>
    <tr>
      <td>1690</td>
      <td>PET_FIRST_MIKE_STATUE - Pet the first Mike statue -</td>
      <td>bool</td>
      <td>Pet the first cat-eared statue in the Mike zone. <br></td>
    </tr>
    <tr>
      <td>1691</td>
      <td>DIDNT_PET_FIRST_MIKE_STATUE - Didnt Pet First Mike Statue -</td>
      <td>map</td>
      <td>Whether you chose not to pet the first statue in the Mike zone when prompted. Unaccessed as of chapter 4. <br>0 = Default state<br>2 = Chose Don't pet<br></td>
    </tr>
    <tr>
      <td>1692</td>
      <td>SAVED_TERRIFIED_MAUS - Saved the terrified Maus -</td>
      <td>bool</td>
      <td>Viewed the cutscene of the MAUS turning into the MOUSE. <br></td>
    </tr>
    <tr>
      <td>1693</td>
      <td>PET_CHEST_MIKE_STATUE - Pet the chest Mike statue -</td>
      <td>bool</td>
      <td>Pet the tall statue in the Mike hat room which had a chest behind it. <br></td>
    </tr>
    <tr>
      <td>1694</td>
      <td>MIKE_STATUES_STATE - Statues -</td>
      <td>number</td>
      <td>Tracks which statues have been pet. <br></td>
    </tr>
    <tr>
      <td>1695</td>
      <td>STARTED_MIKE_BATTLE - Started the Mike battle -</td>
      <td>bool</td>
      <td>Started the battle against Mike. <br></td>
    </tr>
    <tr>
      <td>1696</td>
      <td>SAW_FAKE_MIKES_POST_BATTLE_SCENE - Saw the fake Mikes' post-battle scene -</td>
      <td>bool</td>
      <td>Viewed the cutscene of the fake Mikes after defeating them. <br></td>
    </tr>
    <tr>
      <td>1697</td>
      <td>OPENED_MIKE_DOOR - Opened the Mike exit door -</td>
      <td>bool</td>
      <td>Opened the volume-controlled door before the Mike battle. <br></td>
    </tr>
    <tr>
      <td>1698</td>
      <td>BATTAT_HIGH_SCORE - Battat -</td>
      <td>number</td>
      <td>High score on the BATTAT minigame. <br></td>
    </tr>
    <tr>
      <td>1699</td>
      <td>JONGLER_HIGH_SCORE - Jongler -</td>
      <td>number</td>
      <td>High score on the JONGLER minigame. <br></td>
    </tr>
    <tr>
      <td>1700</td>
      <td>PLUEY_HIGH_SCORE - Pluey -</td>
      <td>number</td>
      <td>High score on the PLUEY minigame. <br></td>
    </tr>
    <tr>
      <td>1701</td>
      <td>MIC_SENSITIVITY - Mic Sensitivity -</td>
      <td>number</td>
      <td>Flag never set, but would have been a microphone sensitivity setting. <br></td>
    </tr>
    <tr>
      <td>1702</td>
      <td>UNLOCKED_MIKE_MINIGAMES - Unlocked -</td>
      <td>bool</td>
      <td>Unlocked the Mike minigames room after the Mike battle. <br></td>
    </tr>
    <tr>
      <td>1703</td>
      <td>OBTAINED_TV_ZONE_3_CHEST - Got the Mike hat-room chest -</td>
      <td>bool</td>
      <td>Got the TV Dinner from the chest in the Mike hat room. <br></td>
    </tr>
    <tr>
      <td>1704</td>
      <td>KRIS_NOELLE_ESCAPE_WEIRD_ABORT - Escape abort -</td>
      <td>map</td>
      <td>Failed to enter Kris's body in time during the Weird Route cutscene and let them escape with Noelle. <br>0 = Default state<br>1 = Let Kris and Noelle escape<br>2 = Got put back in closet<br></td>
    </tr>
    <tr>
      <td>1747</td>
      <td>TALKED_TORIEL_LAST_NIGHT - Talked with Toriel last night -</td>
      <td>map</td>
      <td>Talked with Toriel about her behavior night before Festival. <br>0 = Default state<br>1 = We were locked out<br>2 = You were way too loud<br></td>
    </tr>
    <tr>
      <td>1780</td>
      <td>BALTHIZARD_ENCOUNTER_OUTCOME - Balthizard -</td>
      <td>map</td>
      <td>Tracks the state of the Balthizard encounter at the start of the First Sanctuary. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1781</td>
      <td>BALTHIZARD_OLDMAN_ENCOUNTER_OUTCOME - Balthizard -</td>
      <td>map</td>
      <td>Tracks the state of the Balthizard encounter at the start of the First Sanctuary when coming back with Gerson. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1782</td>
      <td>SECOND_GUEI_ENCOUNTER_OUTCOME - Guei -</td>
      <td>map</td>
      <td>Tracks the state of the Guei encounter when Gerson turns the lights back on in the dark maze room. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1783</td>
      <td>FIRST_MIZZLE_ENCOUNTER_OUTCOME - Mizzle -</td>
      <td>map</td>
      <td>Tracks the state of the Mizzle encounter in the room to the right of Gerson's study. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1784</td>
      <td>WINGLADE_ENCOUNTER_OUTCOME - Winglade -</td>
      <td>map</td>
      <td>Tracks the state of the Winglade encounter at the start of the Second Sanctuary. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1785</td>
      <td>SECOND_ORGANIKK_ENCOUNTER_OUTCOME - Organikk -</td>
      <td>map</td>
      <td>Tracks the state of the Organikk encounter in the Second Sanctuary's library connector room. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1786</td>
      <td>FIRST_ORGANIKK_ENCOUNTER_OUTCOME - Organikk -</td>
      <td>map</td>
      <td>Tracks the state of the Organikk encounter in the Second Sanctuary's worship room. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1787</td>
      <td>STEEL_ENCOUNTER_OUTCOME - Winglade + Organikk -</td>
      <td>map</td>
      <td>Tracks the state of the Winglade/Organikk encounter in the Second Sanctuary's money fountain room. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1788</td>
      <td>FIRST_WICABEL_ENCOUNTER_OUTCOME - Wicabel -</td>
      <td>map</td>
      <td>Tracks the state of the Wicabel encounter in the Second Sanctuary's bell room. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1789</td>
      <td>FIRST_CACOPHONY_ENCOUNTER_OUTCOME - Wicabel + Organikk -</td>
      <td>map</td>
      <td>Tracks the state of the Wicabel/Organikk encounter in the Second Sanctuary's gallery. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1790</td>
      <td>SECOND_CACOPHONY_ENCOUNTER_OUTCOME - Wicabel + Organikk -</td>
      <td>map</td>
      <td>Tracks the state of the Wicabel/Organikk encounter in the Second Sanctuary's room to the right of Gerson's study. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1791</td>
      <td>FLAPPING_ENCOUNTER_OUTCOME - Bibliox + Winglade -</td>
      <td>map</td>
      <td>Tracks the state of the Bibliox/Winglade encounter in the Third Sanctuary's bookshelf maze room. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1792</td>
      <td>THIRD_CACOPHONY_ENCOUNTER_OUTCOME - 2 Organikks + Wicabel -</td>
      <td>map</td>
      <td>Tracks the state of the Organikk/Organikk/Wicabel encounter in the Third Sanctuary's dark maze room. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1793</td>
      <td>ELEMENTS_ENCOUNTER_OUTCOME - Balthizard + Mizzle + Guei -</td>
      <td>map</td>
      <td>Tracks the state of the Balthizard/Mizzle/Guei encounter in the Third Sanctuary's angel prophecy room. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1794</td>
      <td>SECOND_WICABEL_ENCOUNTER_OUTCOME - Wicabel -</td>
      <td>map</td>
      <td>Tracks the state of the Wicabel encounter in the Third Sanctuary's golden piano room. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1795</td>
      <td>FIRST_GUEI_ENCOUNTER_OUTCOME - Guei -</td>
      <td>map</td>
      <td>Tracks the state of the Guei encounter at the start of the First Sanctuary. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1796</td>
      <td>BIBLIOX_ENCOUNTER_OUTCOME - Bibliox -</td>
      <td>map</td>
      <td>Tracks the state of the Bibliox encounter in the library. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1797</td>
      <td>SCENTED_CANDLES_ENCOUNTER_OUTCOME - Guei + Balthizard -</td>
      <td>map</td>
      <td>Tracks the state of the Guei/Balthizard encounter if you touch a roaming flame in the library. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1798</td>
      <td>SECOND_MIZZLE_ENCOUNTER_OUTCOME - Miss Mizzle -</td>
      <td>map</td>
      <td>Tracks the state of the Mizzle encounter in the watercooler room. <br>0 = Default state<br>1 = Violenced (includes SnowGrave)<br>2 = Spared<br>3 = Pacified<br>4 = In combat (Ch. 1)<br>5 = Violenced by uncontrolled Susie (unused in demo due to a bug)<br>6 = Frozen<br></td>
    </tr>
    <tr>
      <td>1846</td>
      <td>PINK_PROGRESS - Pink progress -</td>
      <td>map</td>
      <td>Progress through the Pink encounter and hideout sequence. <br>0 = Door closed<br>1 = Door opened<br>1.5 = Save point before the boss<br>2 = Defeated boss<br>3 = Entered hideout<br>4 = Cutscene starts after buying 3 items in hideout<br>5 = Cutscene ends<br></td>
    </tr>
    <tr>
      <td>1904</td>
      <td>PLATMODE_JUMP_COUNT - Platform mode jump count -</td>
      <td>number</td>
      <td>Kris's jump count in platform mode. <br></td>
    </tr>
    <tr>
      <td>1905</td>
      <td>PLATMODE_SWING_COUNT - Platform mode swing count -</td>
      <td>number</td>
      <td>Kris's swing count in platform mode. <br></td>
    </tr>
    <tr>
      <td>1908</td>
      <td>DEFEATED_PINK - Defeated Pink -</td>
      <td>bool</td>
      <td>Whether you defeated Pink. <br></td>
    </tr>
  </tbody>
</table>
</details>

## global.interact
Usage varies between games but generally is used to determine player state, please reference their specific articles as linked belowed

[global.interact in UNDERTALE](../DELTARUNE/general/GlobalVars.md#globalinteract)

[global.interact in DELTARUNE](../UNDERTALE/GlobalVars.md#globalinteract)


### Example Usage

```js
if (global.interact == 2 && dancing)
    global.flag[204]++
```

## global.typer
global.typer is used to determine who is currently speaking 

Below are the tables for their uses in both UNDERTALE and DELTARUNE

<details>
<summary>All Typers in UNDERTALE</summary>
</details>

<details>
<summary>All Typers in DELTARUNE</summary>

`global.typer` | Character
--- | ---
2 | Silent in the Light World.
4 | Default while fighting.
5 | Default in the Light World.
6 | Default in the Dark World.
7 | Toriel
10 | Susie in the Light World.
12 | Noelle in the Light World.
13 | Berdly in the Light World.
14 | Sans.
17 | Undyne.
18 | Asgore
20 | Alphys
21 | Temmie
30 | Susie in the Dark World.
31 | Ralsei
32 | Lancer
33 | King
35 | Jevil
36 | King before face reveal.
40 | Silent in the Dark World.
45 | Ralsei while fighting.
46 | Lancer while fighting.
47 | Susie while fighting.
48 | King while fighting.
50 | Enemy balloon.
55 | Rudy
56 | Noelle in the Dark World.
57 | Berdly in the Dark World.
58 | Queen
59 | Noelle while fighting.
62 | Queen alt.
66 | Spamton while not fighting.
67 | Spamton NEO.
68 | Spamton while fighting.
77 | Berdly while fighting.
82 | Jackenstein (cute)
83 | Jackenstein
84 | Tenna
85 | Gerson
87 | Carol
666 | Mysterious Voice

</details>