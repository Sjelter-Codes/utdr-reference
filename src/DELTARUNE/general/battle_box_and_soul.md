# Battle Box and SOUL Modes

> **Relevant Scripts:**
>
> - `gml_Object_obj_growtangle_Create_0`
> - `gml_Object_obj_growtangle_Step_0`
> - `gml_Object_obj_growtangle_Step_2`
> - `gml_Object_obj_heart_Create_0`
> - `gml_Object_obj_heart_Draw_0`
> - `gml_Object_obj_heart_Step_0`

The battle box is described by `obj_growtangle`.
It's color is a 50% blend of `c_green` and `c_lime`.

`growcon` | Meaning
--- | ---
`1` | Animate in
`2` | Static
`3` | Animate out

The animation is done using the `growth` variable and handled in `gml_Object_obj_growtangle_Step_0`.

> [!NOTE]
> In most chapters, the SOUL's hitbox is the SOUL sprite itself.
> However, in Chapter 3 only, its hitbox is its bounding rectangle.

## Soul Modes

### Red

The SOUL moves by 4 pixels (`global.sp`, `wspeed`) in each cardinal direction (or 2 if in focus mode).
Note that the focus mode code takes the **ceiling** of half the speed, so setting `wspeed` to a different value may mean focus mode ends up being slower in one direction.
Both `gml_Object_obj_heart_Step_0` and `gml_Object_obj_growtangle_Step_2` clamp the heart to bounds.

Invincibility frames are done using `global.inv` (remaining frames) and `global.invc` (total frames).
`global.inv` is decremented every 4 game frames.
