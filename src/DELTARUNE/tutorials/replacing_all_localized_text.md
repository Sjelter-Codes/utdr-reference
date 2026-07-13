# Replacing Localized Text

You can add a custom handler for all localized text in Chapter 1 by using `gml_GlobalScript_scr_84_get_lang_string`.

```js
function scr_84_get_lang_string(arg0) {
    var value = ds_map_find_value(global.lang_map, arg0);
    // do stuff with `value`
    return value;
}
```

In Chapter 2 onwards, alongside removing the lang strings from being easily accessible, the code to access them has been changed.

```js
function scr_84_get_lang_string(arg0) {
    var lang_string_id = arg0;
    var str = ds_map_find_value(global.lang_map, lang_string_id);
    
    if (is_undefined(str))
    {
        if (!ds_map_find_value(global.lang_missing_map, lang_string_id))
            ds_map_add(global.lang_missing_map, lang_string_id, true);
        
        str = "--missing-string--";
    }
    
    // do stuff with `str`
    return str;
}
```
On top of that this script only runs if `is_english()` is false. 

---

Instead of trying to use `scr_84_get_lang_string()` try using `msgsetloc()` as shown below:

```js
function c_msgsetloc(arg0, arg1, arg2)
{
    var msg_index = arg0;
    var english = arg1;
    var localized_string_id = arg2;
    var str = english;
    if (!is_english())
        str = scr_84_get_lang_string(localized_string_id);
    // do stuff with `str`
    c_msgset(msg_index, str);
}
```