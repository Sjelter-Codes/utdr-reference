# Spells

> **Relevant Scripts:**
>
> - `gml_GlobalScript_scr_spell`
> - `gml_GlobalScript_scr_spelltext`
> - `gml_GlobalScript_scr_spellinfo`
> - `gml_GlobalScript_scr_spellinfo_all`
> - `gml_GlobalScript_scr_iteminfo`
> - `gml_Object_obj_battlecontroller_Step_0`

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