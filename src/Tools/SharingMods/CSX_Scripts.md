# CSX Scripts

UTMT's scripting interface can be interacted with using `.csx` files. These files, written in C#, allow one to use and manipulate UTMT's internal data structures and functions.

In the UTMT GUI, the "Scripts" dropdown menu in the top left corner contains a variety of builtin `.csx` scripts used for various purposes, such as importing assets or running a find and replace. The files for these scripts are located in the "Scripts" folder in the UTMT executable directory.

It is also possible to create custom `.csx` scripts. When distributing a mod, `.csx` scripts can be used to import assets and code entries without dependence on the game version, which is an advantage over some other mod patching methods.

## Running a custom script

There are two ways to run a custom `.csx` script with the GUI:
1. Hover over the "Scripts" dropdown, click "Run other script...", and then select the `.csx` file.
2. Locate the directory where the UTMT executable resides, drop the `.csx` script in the "Scripts" folder, and then run the script from the "Scripts" dropdown in the GUI.

The latter method makes the script accessible straight from the GUI, which is useful for general usage scripts. However, the former method might be preferred for more complicated scripts or for scripts that require other files to be present, such as `.png`s for importing sprites.