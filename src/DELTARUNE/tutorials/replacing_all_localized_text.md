# Replacing Localized Text

You can add a custom handler for all localized text in Chapter 1 by using `gml_GlobalScript_scr_84_get_lang_string`.
This may work in other chapters, but I haven't checked.

```js
function scr_84_get_lang_string(arg0) {
    var value = ds_map_find_value(global.lang_map, arg0);
    // do stuff with `value`
    return value;
}
```
