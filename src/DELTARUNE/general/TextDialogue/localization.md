# Localization & 8-4 Scripts
## Lang Files

All of DELTARUNE Chapter 1's dialogue is stored in the Chapter 1 `lang` folder, which is located in the same directory as where the [Chapter 1 WAD file resides](../../Tools/GameMaker/WADFiles.md#deltarune). The English and Japanese translations are named `lang_en.json` and `lang_ja.json` respectively. 

The beginning of Chapter 1's `lang_en.json` is shown below:

```json
{
  "date": "1540902565549",
  "DEVICE_CONTACT_slash_Step_0_gml_5_0": " ^9 ^8 %",
  "DEVICE_CONTACT_slash_Step_0_gml_6_0": " ARE YOU^6& THERE^6?\\M1 ^6 %",
  "DEVICE_CONTACT_slash_Step_0_gml_7_0": "^6 \\M0ARE WE^6&CONNECTED^6?\\M1 ^6 ^6 %%",
  ...
}
``` 

Each JSON file contains a `date` key whose value is a timestamp encoded in unix time. Each subsequent key is a dialogue ID (e.g. `DEVICE_CONTACT_slash_Step_0_gml_5_0`) with the appropriate translation as the corresponding value. The dialogue IDs are the same between the English and Japanese JSONs, making it easy for the game to find the correct text translation just from the text's dialogue ID.

Starting from Chapter 2, DELTARUNE's English dialogue no longer exists in a `lang_en.json` file but is instead embedded in the code of the WAD file. However, Japanese dialogue still remains in a `lang_ja.json` file.  

## 8-4 Localization Scripts

The `scr_84` scripts, likely named after DELTARUNE's localization company "8-4", handle DELTARUNE's localization system. 

> [!NOTE] DELTARUNE Demo Chapter 1 Scripts
> The DELTARUNE demo contains `_ch1` versions of the 8-4 scripts to differentiate them from Chapter 2's scripts. Most of these scripts function exactly the same as the non-`_ch1` versions, but some have small changes to be compatible with Chapter 1's code. For example, `scr_84_lang_load_ch1` reads `lang_en.json` if the current language is English, which is not a feature in `scr_84_lang_load` as English dialogue is embedded in the WAD file post-Chapter 1 instead of being in an external file.

### Initialization Script

DELTARUNE's initializer object, `obj_initializer2`, calls in its Create event the localization initialization script, `scr_84_init_localization`.

In essence, this script initializes some important global variables:

Variable Name | Type | Notes
--- | --- | ---
`global.lang` | `string` | <ul><li>Can either be `en` or `ja`.</li><li>First tries to read the value from the `LANG` key in the `LANG` header of `true_config.ini`</li><li>Otherwise, the variable is set via the builtin GameMaker function `os_get_language`.</li><li>Determines whether the other global variables, besides `global.lang_map` post-Chapter 1, load the English or Japanese translation.</li></ul>
`global.lang_map` | `DS Map` | <ul><li>A DS map containing all of DELTARUNE's Japanese dialogue.</li><li>`scr_84_init_localization` calls `scr_84_lang_load`, which, if the language is set to Japanese, loads this variable by reading the `lang_ja.json` file through the wrapper script `scr_84_load_map_json`.</li><li>In Chapter 1, this variable may also hold the contents of `lang_en.json` if the language is set to English.</li></ul>
`global.font_map` | `DS Map` | <ul><li>A DS map that contains either English or Japanese fonts based on the current language.</li><li>The font IDs are the font names without the `fnt_` or `fnt_ja_` prefix.</li><li>Example: Font ID `main` is mapped to `fnt_main` in English and to `fnt_ja_main` in Japanese.</li></ul>
`global.chemg_sprite_map`<br>`global.chemg_sound_map`| `DS Map` | <ul><li>DS maps that contain either English or Japanese assets based on the current language.</li><li>The asset IDs are the English asset names.</li><li>Example: In `global.chemg_sound_map`, sound ID `snd_flowery_voiceclip_glue` is mapped to `snd_flowery_voiceclip_glue` in English and `snd_flowery_voiceclip_glue_ja` in Japanese.</li></ul>

### Accessing Translation Maps

The following scripts can be used to access the global translation maps populated in the above initialization script.

Script Name | Notes
--- | ---
`scr_84_get_font`| <ul><li>Takes a font ID and returns the corresponding font found in `global.font_map`</li><li>Example: `f = scr_84_get_font("mainbig");`</li></ul>
`scr_84_set_draw_font` | <ul><li>Takes a font ID and sets the current draw font to the corresponding font in `global.font_map`</li><li>Example: `scr_84_set_draw_font("dotumche");`</li></ul>
`scr_84_get_lang_string` | <ul><li>Takes a dialogue ID and returns the corresponding dialogue string in `global.lang_map`</li><li>Example: `s = scr_84_get_lang_string("scr_text_slash_scr_text_gml_2198_0");`</li></ul>
`scr_84_get_sprite` | <ul><li>Takes a sprite ID and returns the corresponding sprite found in `global.chemg_sprite_map`</li><li>Example: `menu_sprite = scr_84_get_sprite("spr_darkmenudesc");`</li></ul>
`scr_84_get_sound` | <ul><li>Takes a sound ID and returns the corresponding sound found in `global.chemg_sound_map`</li><li>Example: `snd_stop(scr_84_get_sound("snd_ja_kidding"));`</li><ul>

### Miscellaneous 8-4 Scripts

Listed below are some 8-4 scripts that do not have anything to do with the global translation maps.

Script Name | Notes
--- | ---
`scr_84_get_subst_string` | <ul><li>Is only used in Chapters 1 and 3; functions similarly to `substringargs`.</li><li>Takes an input string and multiple replacement strings; All instances of `~n`in the input string are replaced by the `n`th replacement string, where `n` is a positive integer.</li><li>Example: `s = scr_84_get_subst_string("* ~1 spared!/%", enemyname);` replaces `~1` with `enemyname` and sets `s` to the resultant string.</li></ul>
`scr_84_name_input_setup` | <ul><li>Sets up the character system used to name both the Vessel and the Player</li><li>Called in `DEVICE_CHOICE`'s `User Event 0` script for initialization, and then again in `DEVICE CHOICE`'s `Step` event if the character system has been changed.</li><li>Based on the value of `LANGSUBTYPE`, sets up (0) English, (1) Hiragana, (2) Katakana, or (3) English. A `LANGSUBTYPE` value of 0 is only used for English, while 1-3 are used for Japanese, with extra selectable options added at the bottom of the layout to swap between the different character systems. The addition of these options in 3 is why 0 and 3 are different.</li></ul> 
`scr_84_draw_text_outline` | <ul><li>A modified version of `draw_text` that creates outlined text by drawing the text in black in all cardinal directions before drawing the main text in the center</li><li>Doesn't draw the blackened text in all 8 directions and doesn't take an additional `color` argument used for the center text, unlike `draw_text_outline`</li><li>Example: `scr_84_draw_text_outline(myx, myy, "[Left / Right]")` draws an outlined version of `[Left / Right]` at `(myx, myy)`.</li></ul>
`scr_84_load_ini` | <ul><li>Initializes the name, room, level, and time information for each file in the file select screen; called in `DEVICE_MENU`.</li><li>Called right after [`scr_change_language`](#changing-languages) to update the text after the language has been changed.</li></ul>

### Unused/Debug Scripts

> **Unused 8-4 Scripts:**
>
> - `scr_84_add_menu_item`
> - `scr_84_draw_menu`
> - `scr_84_pop`
> - `scr_84_push`
> - `scr_84_is_digit`

There also exists a debug script, `scr_84_debug`, that is used in `obj_time` and takes a boolean argument. However, the script is empty. It is likely that the script's contents were removed for the release version of DELTARUNE.

## Changing Languages

The script used to change languages in the file select screen is `scr_change_language`. This script swaps `global.lang` from `en` to `ja` or from `ja` to `en` and then saves `global.lang` in `true_config.ini`, under the header `LANG` and the key `LANG`.

The script `is_english` can be used to determine if the current language is English (meaning by default `!is_english()` will return whether the current language is Japanese).
