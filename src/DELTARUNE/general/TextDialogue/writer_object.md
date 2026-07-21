# Writer Object

The object `obj_writer` displays DELTARUNE's text. 

## Text Setup Scripts

When `obj_writer` is created, it runs `scr_texttype` in its Create event, which functions similarly to `SCR_TEXTTYPE` in UNDERTALE. This script initializes a `obj_writer` instance variable called `textscale` and assigns it a value of `1`. It then runs `scr_textsetup` with a specific set of arguments that is dependent on the value of [`global.typer`](../../UTDR/GlobalVars.md#globaltyper).

For example, if `global.typer` is set to `1`, `scr_texttype` calls `scr_textsetup(scr_84_get_font("main"), c_white, x, y, 33, 0, 1, snd_text, 8, 18, 0);`.

These arguments are used as values for `obj_writer` instance variables, as detailed below:

Variable Name | Argument Index | Notes
--- | --- | ---
`myfont` | `0` | The font asset to be used for the text, which is usually obtained via `scr_84_get_font` like in the example above with `scr_84_get_font("main")`.
`mycolor` | `1` | The text color to be used; `c_white` is the default and will produce white text
`writingx` | `2` | The starting `x` position of the text; is always set to the writer's `x` position
`writingy` | `3` | The starting `y` position of the text; is always set to the writer's `y` position 
`charline` | `4` | The max amount of characters in a line of text; usually hardcoded to be `33`, as it is what will fit in a generic dialogue box; if the amount of characters in a line surpasses this value, a newline is created.
`shake` | `5` | The amount of pixels the text can deviate from the center when shaking; usually set to `0` to disable shaking, but is set to `1` with certain "typers", such as the typer value used for the Chapter 2 Weird Route hospital interactions with Noelle.
`rate` | `6` | The number of frames between each text character rendering; usually set to `1` for normal dialogue interactions (i.e. a new text character appears each frame), but certain typers such as Gaster's typer (666) can bump it up all the way to `4`.
`textsound` | `7` | The asset for the "blip" sound that plays when a character is talking; usually the asset name begins with `snd_txt`
`hspace` | `8` | The number of pixels between characters, from the top left pixel of one character to the top left pixel of the next character; note this is not the amount of empty space between two characters; usually set to `8` for normal dialogue interactions
`vspace` | `9` | The number of pixels between lines, from the top left pixel of one line to the top left pixel of the line below it; note this is not the amount of empty space between two lines; usually set to `18` for normal dialogue interactions
`special` | `10` | A number ID from `0` to `5` that tells the renderer to apply certain effects to the text, where `0` refers to applying no special effects

If the current language is Japanese, `hspace` and `vspace` are tampered with at the bottom of `scr_texttype` to adjust character spacing for the relatively bigger Japanese characters. `extra_ja_vspace` here is set to `0` by default but is set to `2` for battle typers, with the exception of Spamton's battle(s).

```js
if (myfont == fnt_ja_main)
{
    hspace = ((hspace * 26) / 16) + 1;
    
    // There are no known typers with `vspace` set to 32.
    // This is likely a leftover from UNDERTALE.
    if (vspace == 32) 
        vspace = 36;
}
else if (myfont == fnt_ja_mainbig)
{
    hspace = ((hspace * 13) / 8) + 1;
}
else if (myfont == fnt_ja_comicsans)
{
    textscale = 0.5;
    hspace = ((hspace * 13) / 8) + 3;
}
else if (myfont == fnt_ja_tinynoelle)
{
    textscale = 0.5;
    hspace = ((hspace * 13) / 8) + 1;
}
else if (myfont == fnt_ja_dotumche)
{
    hspace = ((hspace * 26) / 16) + 1;
}
else if (myfont == fnt_ja_small)
{
    hspace = ((hspace * 13) / 8) + 1;
}

vspace += extra_ja_vspace;
```

### Control Characters

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