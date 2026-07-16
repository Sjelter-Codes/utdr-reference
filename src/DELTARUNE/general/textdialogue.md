# Text & Dialogue

## Localization
### Lang Files

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

### 8-4 Localization Scripts

The `scr_84` scripts, likely named after DELTARUNE's localization company "8-4", handle DELTARUNE's localization system. When DELTARUNE's initializer object, `obj_initializer2`, is created, it calls the localization initialization script, `scr_84_init_localization`, in its Create event.

In essence, this script initializes some important global variables:

Variable Name | Type | Notes
--- | --- | ---
`global.lang` | `string` | <ul><li>Can either be `en` or `ja`.</li><li>First tries to read the value from the `LANG` key in the `LANG` header of `true_config.ini`</li><li>Otherwise, the variable is set via the builtin GameMaker function `os_get_language`.</li><li>Determines whether the other global variables, besides `global.lang_map` post-Chapter 1, load the English or Japanese translation.</li></ul>
`global.lang_map` | `DS Map` | <ul><li>A DS map containing all of DELTARUNE's Japanese dialogue.</li><li>`scr_84_init_localization` calls `scr_84_lang_load`, which loads this variable by reading the `lang_ja.json` file through the wrapper script `scr_84_load_map_json`.</li><li>In Chapter 1, this variable may also hold the contents of `lang_en.json` if the language is set to English.</li></ul>
`global.font_map` | `DS Map` | <ul><li>A DS map that contains either English or Japanese fonts based on the current language.</li><li>The font IDs are the font names without the `fnt_` or `fnt_ja_` prefix.</li><li>Example: Font ID `main` is mapped to `fnt_main` in English and to `fnt_ja_main` in Japanese.</li></ul>
`global.chemg_sprite_map`<br>`global.chemg_sound_map`| `DS Map` | <ul><li>DS maps that contain either English or Japanese assets based on the current language.</li><li>The asset IDs are the English asset names.</li><li>Example: In `global.chemg_sound_map`, sound ID `snd_flowery_voiceclip_glue` is mapped to `snd_flowery_voiceclip_glue` in English and `snd_flowery_voiceclip_glue_ja` in Japanese.</li></ul>

The following wrapper scripts are used throughout the game's code to access these global variables:

Script Name | Usage Notes
--- | ---
`scr_84_get_font`| <ul><li>Takes a font ID and returns the corresponding font found in `global.font_map`</li><li>Example: `f = scr_84_get_font("mainbig");`</li></ul>
`scr_84_set_draw_font` | <ul><li>Takes a font ID and sets the current draw font to the corresponding font in `global.font_map`</li><li>Example: `scr_84_set_draw_font("dotumche");`</li></ul>
`scr_84_get_lang_string` | <ul><li>Takes a dialogue ID and returns the corresponding dialogue string in `global.lang_map`</li><li>Example: `s = scr_84_get_lang_string("scr_text_slash_scr_text_gml_2198_0");`</li></ul>
`scr_84_get_sprite` | <ul><li>Takes a sprite ID and returns the corresponding sprite found in `global.chemg_sprite_map`</li><li>Example: `menu_sprite = scr_84_get_sprite("spr_darkmenudesc");`</li></ul>
`scr_84_get_sound` | <ul><li>Takes a sound ID and returns the corresponding sound found in `global.chemg_sound_map`</li><li>Example: `snd_stop(scr_84_get_sound("snd_ja_kidding"));`</li><ul>

## Control Characters

Symbol | Description
--- | ---
`^[1-9]` | This is a control character that tells Deltarune to wait a certain amount of frames before continuing to write dialogue. <br> It is most commonly used right before commas and ellipses. <br> Each number corresponds to a different amount of frames. Deltarune runs at 30 frames per second. <br> `1`: 5 frames. <br>`2`: 10 frames. <br> `3`: 15 frames. <br> `4`: 20 frames. <br> `5`: 30 frames. <br> `6`: 40 frames. <br> `7`: 60 frames. <br> `8`: 90 frames. <br> `9`: 150 frames.
`/` | This is a control character that tells Deltarune to stop writing dialogue for the current message. This doesn’t end the conversation, as pressing [CONFIRM] advances the text to the next message.
`/%` | This is a control character that tells Deltarune to stop writing dialogue for the current message. After pressing [CONFIRM], the dialogue box goes away.
`%%` | This is a control character that tells Deltarune to immediately close the dialogue box after it is reached.
`\` | When using a control character with a backslash (\) in it, you must escape the backslash with another backslash. For example, `\\E1` is a valid control character that tells Deltarune to change the current character’s emotion to index 1.
`\E[alphanumeric]` | This a control character that tells Deltarune to change the current face’s emotion. <br> <br> The number or letter after “E” tells Deltarune what emotion index to use. <br> `0-9` uses index 0-9. <br> `A-Z` uses indexes 10-35. <br> `a-z` uses indexes 36-60.
`\F` | This a control character that tells Deltarune to change the current face. <br> The number or letter after “F” tells Deltarune what face to use. <br> `0`: No face. <br> `S`: Susie. <br> `R`: Ralsei. <br> `N`: Noelle. <br> `T`: Toriel <br> `L`: Lancer. <br> `A`: Asgore <br> `a`: Alphys <br> `B`: Berdly <br> `r`: Rudy <br> `u`: Rouxls Kaard <br> `K`: King
`\T(number)` | This a control character that tells Deltarune to change the typer, which controls how text is displayed and heard. <br> The number or letter after “T” tells Deltarune what typer to use. <br>`0`: Default <br>`1`: Silent in the Light World <br>`A`: Asgore <br>`a`: Alphys <br>`N`: Noelle <br>`n`: Noelle but with small text <br>`B`: Berdly <br>`S`: Susie <br>`R`: Ralsei <br>`L`: Lancer <br>`X`: Silent in the Dark World <br>`r`: Rudy <br>`T`: Toriel <br>`J`: Jevil <br>`K`: King
`\f[0-9]` | This a control character that tells Deltarune to add a small face and text to the screen. 
`\*` | This a control character that tells Deltarune to type a keyboard button or draw a controller button sprite. <br> This is only used when a controller is connected by calling scr_get_input_name(), where the first variable is a number from 0-9. <br>`0`: Move down <br>`1`: Move right <br>`2`: Move up <br>`3`: Move left <br>`4`: Confirm 1 (Defaults to Z) <br>`5`: Cancel 1 (Defaults to X) <br>`6`: Menu 1 (Defaults to C) <br>`7`: Confirm 2 (Defaults to Enter) <br>`8`: Cancel 2 (Defaults to Shift) <br>`9`: Menu 2 (Defaults to Control)
`\s` | This a control character that tells Deltarune whether the text is skippable or not. <br>`0`: False <br>`1`: True
`\c` | This a control character that tells Deltarune to color the following text a different color. <br> The letter or number after “c” controls what color to use.<br>`R`: Red <br>`B`: Blue <br>`Y`: Yellow <br>`G`: Lime <br>`W`: White <br>`X`: Black <br>`0`: Reset
`\C` | This a control character that tells Deltarune to bring up a choicer. <br><br> The number after “C” tells Deltarune whether to use the old choicer, and how many choices there should be. <br>`1`: Old Choicer (How Undertale’s choicer looks) <br>`2`: New Choicer, 2 Choices <br>`3`: New Choicer: 3 Choices <br>`4`: New Choicer: 4 Choices
`\M` | This a control character that tells Deltarune to change an overworld sprite using global.flag[20]. <br> The number after “M” tells Deltarune what to set the flag to.
`\S` | This a control character that tells Deltarune to play a sound while text is writing. <br> The number after “S” tells Deltarune which predefined sound to play using global.writersnd[0-9].
`\I` | This a control character that tells Deltarune to insert an image while text is writing. <br> The number after “I” tells Deltarune which predefined image to draw using global.writerimg[0-9].
`#` | This is essentially a replacement for the `\n` character, it is a new line character