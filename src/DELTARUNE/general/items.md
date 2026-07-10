# Items

> **Relevant Scripts:**
>
> - `gml_GlobalScript_scr_spell`
> - `gml_GlobalScript_scr_itemuse`
> - `gml_GlobalScript_scr_spelltext`
> - `gml_GlobalScript_scr_iteminfo`
> - `gml_GlobalScript_scr_iteminfo_all`
> - `gml_GlobalScript_scr_itemnamelist`
> - `gml_Object_obj_battlecontroller_Step_0`
> - `gml_GlobalScript_scr_itemdesc_single`

Items can be used during or outside of battle to various effects from healing to reviving to even tension
> [!NOTE]
> This is based on Chapter 2's code, reminder to go back and verify if this functions in all versions

## Item Structure

In DELTARUNE items contain:

View `gml_GlobalScript_scr_iteminfo` to compare
- An ID
    - This is used in the switch case statement inside of `scr_spell` to decide what code to run and is checked in `scr_spelltext` to decide which code to display upon use. When it comes to items it appears that their IDs are offset by +200 in `spell` related scripts.
- Item Name
    - Known as `global.itemname[id]`, this is the name that will show up inside of overworld.
- Battle Alias
    - Known as `itemnameb`, this is the name that will show up during battle
- Item Description
    - Known as `itemdesc[id] in scr_itemdesc()`, this is the description that will show up in the the overworld.
- Battle Description
    - Known as `itemdescb`, this is the name that will show up during battle
- Item Target
    - Known as `target`, this is the target of the item
        - 0 doesn't give a decision
        - 1 selects an ally
        - 2 selects an opponent
- Value
    - Known as `value`, this is the amount of D$ you will gain from selling it at a shop.
- Usability
    - Known as `usable`, this determines wether or not the item is usable in the overworld.

## Key Items
Key Items do not appear in your invetory normally and as such have their own section

Key Items structure is much simpler, only containing a description. In `scr_itemuse` their ID's are offset by 300.

## Light World Items
Light World Items are also quite simple, all scripts pertaining to them are prefixed with `scr_litem`

`gml_GlobalScript_scr_litemname` contains the names of Light World Items

`gml_GlobalScript_scr_litemdesc` contains the descriptions of Light World Items

`gml_GlobalScript_scr_litemuseb` handles using of Light World Items

`gml_GlobalScript_scr_litemget` is the recommended way to give a player a Light World item

## Related Variables

### global.item
global.item is an array which contains the entire inventory.
```js
global.item[9] = 32
```

### global.pocketitem
global.pocketitem is an array which contains the entire storage.
```js
global.pocketitem[9] = 32
```

## Scripts
This section is an overview of individual scripts related to spells

### scr_spell
Handles how items are used during battle. 

- arg0/spell is the ID of the item to be used, offset by 200
- arg1/caster is the caster of the spell
- star is the star of the item's use/the one who is targetted by the item

> [!TIP]
> Tension items are not found in scr_spell, they can instead be found in  `gml_Object_obj_battlecontroller_Step_0`
> This is to make the item's give you TP before it switches to the next party member

#### Example Usage

```js
    case 232:
        scr_healitemspell(999);
        item_use = true;
        break;
```

### scr_spellinfo_all
Inserts the items from `scr_iteminfo` into the global versions of their respective functions.
```js
global.itemvalue[i] = value;
```

### scr_itemget
The recommended way to give a item to a party member. As of Chapter 2+ if it fails to give an item in the player's inventory it will attempt to give it to the player's storage.
- arg0 is the party member
- arg1 is the ID of the spell to be given


#### Example Usage

```js
scr_itemget(32)
```

### scr_itemuse
This is for when an item is used specifcally in the overworld. 
> [!TIP]
> The usable variable here determines wether or not the item gets used up.

#### Example Usage

```js
    case 32:
        usable = 1;
        scr_healitem_all(50);
        
        if (scr_havechar(2))
            scr_itemcomment(suspos, stringsetloc("Don't throw mints at me!", "scr_itemuse_slash_scr_itemuse_gml_538_0"));
```