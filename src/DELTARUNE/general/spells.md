# Spells

> **Relevant Scripts:**
>
> - `gml_GlobalScript_scr_spell`
> - `gml_GlobalScript_scr_spelltext`
> - `gml_GlobalScript_scr_spellinfo`
> - `gml_GlobalScript_scr_spellinfo_all`
> - `gml_GlobalScript_scr_iteminfo`
> - `gml_Object_obj_battlecontroller_Step_0`

<details>
<summary>Table of All Spells</summary>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Spell ID</th>
      <th>Spell Name</th>
      <th>Battle Alias</th>
      <th>Description</th>
      <th>Battle Description</th>
      <th>Cost</th>
      <th>Spell Target?</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td></td>
      <td></td>
      <td>[EMPTY]</td>
      <td>None</td>
      <td>-1 ( actual TP amount -0.4%) <br></td>
      <td>0 - No decision given</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Rude Sword</td>
      <td>RudeSword</td>
      <td>Deals moderate Rude-elemental damage to#one foe. Depends on Attack &amp; Magic.</td>
      <td>Rude#damage</td>
      <td>125 ( actual TP amount 50.0%) <br></td>
      <td>2 - Selects an opponent</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Heal Prayer</td>
      <td>Heal Prayer</td>
      <td>Heavenly light restores a little HP to#one party member. Depends on Magic.</td>
      <td>Heal#ally</td>
      <td>80 ( actual TP amount 32.0%) <br></td>
      <td>1 - Selects an ally</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Pacify</td>
      <td>Pacify</td>
      <td>SPARE a tired enemy by putting them to sleep.</td>
      <td>Spare#TIRED foe</td>
      <td>40 ( actual TP amount 16.0%) <br> If Ralsei has the item with the ID 32 Pacify will cost 0 TP</td>
      <td>2 - Selects an opponent</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Rude Buster</td>
      <td>Rude Buster</td>
      <td>Deals moderate Rude-elemental damage to#one foe. Depends on Attack &amp; Magic.</td>
      <td>Rude#damage</td>
      <td>125 ( actual TP amount 50.0%) <br> If Susie has the item with the ID 7 Rude Buster will cost 40 TP</td>
      <td>2 - Selects an opponent</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Red Buster</td>
      <td>Red Buster</td>
      <td></td>
      <td>Red#damage</td>
      <td>0 ( actual TP amount 0.0%) <br></td>
      <td>2 - Selects an opponent</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Dual Heal</td>
      <td>Dual Heal</td>
      <td></td>
      <td>Heal All#30 HP</td>
      <td>0 ( actual TP amount 0.0%) <br></td>
      <td>0 - No decision given</td>
    </tr>
    <tr>
      <td>7</td>
      <td>ACT</td>
      <td>ACT</td>
      <td>It's not magic, is it?#No, not something like this.</td>
      <td>Use#action</td>
      <td>0 ( actual TP amount 0.0%) <br></td>
      <td>0 - No decision given</td>
    </tr>
    <tr>
      <td>8</td>
      <td>SleepMist</td>
      <td>Sleep Mist</td>
      <td>A cold mist sweeps through,#sparing all TIRED enemies.</td>
      <td>Spare#TIRED foes</td>
      <td>80 ( actual TP amount 32.0%) <br></td>
      <td>0 - No decision given</td>
    </tr>
    <tr>
      <td>9</td>
      <td>IceShock</td>
      <td>IceShock</td>
      <td>Deals magical ICE damage to#one enemy.</td>
      <td>Damage#w/ ICE</td>
      <td>40 ( actual TP amount 16.0%) <br> If Noelle has the item with the ID 13 IceShock will cost 50% less TP</td>
      <td>2 - Selects an opponent</td>
    </tr>
    <tr>
      <td>10</td>
      <td>SnowGrave</td>
      <td>SnowGrave</td>
      <td>Deals the fatal damage to#all of the enemies.</td>
      <td>Fatal</td>
      <td>250 ( actual TP amount 100.0%) <br> If Noelle has the item with the ID 13 SnowGrave will cost 50% less TP</td>
      <td>0 - No decision given</td>
    </tr>
    <tr>
      <td>11</td>
      <td>BetterHeal</td>
      <td>BetterHeal</td>
      <td>A healing spell that has grown#with practice and confidence.</td>
      <td>Heal#ally</td>
      <td>999 ( actual TP amount 399.6%) <br></td>
      <td>1 - Selects an ally</td>
    </tr>
    <tr>
      <td>12</td>
      <td>ReviveSong</td>
      <td>ReviveSong</td>
      <td>Revives a DOWNed ally and heals them.#Otherwise, heals a lot of HP.</td>
      <td>Revive#ally</td>
      <td>212 ( actual TP amount 84.80000000000001%) <br></td>
      <td>1 - Selects an ally</td>
    </tr>
  </tbody>
</table>
</details>

Spells are casted either during battle or in the Power menu (This goes nearly completly unusued however because TP gets turned into extra dark dollars after pretty much every battle.) 

> [!NOTE]
> While the word "spells" may imply that this code is only used for spells you can cast this also applies to items in scr_spell. Pretty much everywhere else though this doesn't apply.

## Spell Structure

In DELTARUNE spells contain:

View `gml_GlobalScript_scr_spellinfo` to compare

- An ID
    - This is used in the switch case statement inside of `scr_spell` to decide what code to run and is checked in `scr_spelltext` to decide which code to display upon use.
- Spell Name
    - Known as `spellname`, this is the name that will show up in the Power Menu
- Battle Alias
    - Known as `spellnameb`, this is the name that will show up during battle
- Spell Description
    - Known as `spelldesc`, this is the description that will show up in the Power Menu
- Battle Description
    - Known as `spelldescb`, this is the description that will show up during battle
- Spell Target
    - Known as `spelltarget`, this is the target of the spell
        - 0 doesn't give a decision
        - 1 selects an ally
        - 2 selects an opponent
- TP Cost
    - Known as `cost`, this is the amount of TP it costs to use that spell. Please note that the TP cost will be 2/5 of what you put here. 80 cost = 32% TP
- Overworld Usability
    - Known as `spellusable`, this determines wether or not the spell is usable in the overworld.
- Spell Usability
    - Known as `usable`, this variable's use is currently unknown, it is most likely a remnant of `scr_iteminfo`.

## Related Variables

### global.spell
global.spell is a 2D array that stores the spell each party member currently has. The first value is the party member, the second is the ID for the spell in question.

```js
global.spell[1][32]
```

### global.spelldelay
global.spelldelay is the time it takes between spells to be casted during battle.
```js
global.spelldelay = 32
```
## Scripts
This section is an overview of individual scripts related to spells

### scr_spell
Handles how spells are cast during battle. 

- arg0/spell is the ID of the spell to be cast
- arg1/caster is the caster of the spell
- star is the star of the attack/the one who is targetted by the attack

#### Example Usage

```js
    case 32:
        healnum = global.battlemag[arg1] * 999;
        scr_heal(star, healnum);
        global.charinstance[star].healnum = healnum;
        global.spelldelay = 15;
        break;
```

### scr_spell_overworld
Handles what happens when a spell is run in the overworld. Only used by Heal Prayer (ID:2)

#### Example Usage

```js
    case 32:
        scr_healitem(global.charselect, 999);
        break;
```

### scr_spellinfo_all
Inerts the spells from `scr_spellinfo` into the global versions of their respective functions
```js
global.spellname[j][i] = spellname;
```

### scr_spellget
> [!INFO] Only works in Chapter 2+
The recommended way to give a spell to a party member.
- arg0 is the party member
- arg1 is the ID of the spell to be given


#### Example Usage

```js
scr_spellget(4, 32)
```