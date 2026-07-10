# Text & Dialogue

## Control Characters

Symbol | Description
--- | ---
`[G]` | Represents Gold
`[I]` | Represents the current ITEM (used when dropping items)
`[1-9]` | Refers to arguments 1-9 (these are temporary variables for specific dialogue or text, such as how much gold you gain or what armor Papyrus tells Undyne you were wearing)
`\(capital letter)` | Changes the color of text to the right of it to that color (\X changes it back to white)
`\C`* | When specifically at the end of the dialogue box signifies a choice.
`\T(number)` | Switches the voice of the text, primarily during dialogue box chains. <br>`\T0 = default`<br>`\TS = silent`<br>`\TF = Flowey`<br>`\Tf = also Flowey`<br>`\TT = Toriel`<br>`\Ts = Sans`<br>`\Tt = Sans's Toriel voice`<br>`\TP = Papyrus`<br>`\TA = Alphys`<br>`\Ta = Asgore`<br>`\TM = Mettaton`<br>`\TR = Asriel `<br>
`\F(number)` | Changes the character who's portrait is shown in a dialogue box in the overworld, and also the expression of the second character in battle scenarios such as the alphys date. <br>`\F0 = no portrait`<br>`\F1 = Toriel`<br>`\F3 = Sans`<br>`\F4 = Papyrus`<br>`\F5 = Undyne`<br>`\F6 = Alphys`<br>`\F7 = Asgore`<br>`\F8 = Mettaton EX` <br> The second function is likely controlled in a similar fashion as \E
`\M` | Controls the pose of the body of the character in battle (usually the first character in battle) or in dates.
`^[1-9]` | This is a control character that tells Undertale to wait a certain amount of frames before continuing to write dialogue. <br> It is most commonly used right before commas and ellipses. <br> Each number corresponds to a different amount of frames. Undertale runs at 30 frames per second. <br> `1`: 5 frames. <br>`2`: 10 frames. <br> `3`: 15 frames. <br> `4`: 20 frames. <br> `5`: 30 frames. <br> `6`: 40 frames. <br> `7`: 60 frames. <br> `8`: 90 frames. <br> `9`: 150 frames.
`^ on its own` | This (might) signify the end of monster dialogue and the start of an attack turn.
`&`| Begins a new line in textbox, naming screen, and battle dialogue
`#` | begins a new line in the naming screen text, the sound test text, and the credits.
`\E[alphanumeric]` | This a control character that tells Undertale to change the current face’s emotion. <br> <br> The number or letter after “E” tells Deltarune what emotion index to use. <br> `0-9` uses index 0-9. <br> `A-Z` uses indexes 10-35. <br> `a-z` uses indexes 36-60.
`/` | This is a control character that tells Undertale to stop writing dialogue for the current message. This doesn’t end the conversation, as pressing [CONFIRM] advances the text to the next message.
`% and %%` | This (could) signify the end of a chain of text boxes. no clear difference.