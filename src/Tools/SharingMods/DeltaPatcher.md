# Delta Patcher

[Delta Patcher](https://www.romhacking.net/utilities/704/) is a software designed to create and apply `.xdelta` files. A `.xdelta` file is a type of patch file that stores the differences between two specific files. In the modding scene, Delta Patcher is used to create patches for WAD files, and it is one of the most common patching methods as it is relatively easy to make and apply patches.

Because of the way `.xdelta` patches store file changes, the original WAD file used to create the patch and the WAD file being patched must be the exact same for the patch to be guaranteed to work. In other words, any difference between the original WAD file used to create the patch and the WAD file that is being patched, even if small, may make a `.xdelta` patch incompatible. This also makes it very difficult for multiple patches to be usable on the same WAD file.

By default, Delta Patcher opens in patch application mode. To swap between applying and creating a patch, click on the blue button with two arrows in the bottom right. 

## Creating a patch

To create a patch, place the vanilla WAD file in the "Original file" entry and the modded WAD file in the "Modified file" entry. Then, enter a location in the "XDelta patch" entry where the `.xdelta` patch will be saved.

An optional description may also be added which will show up when the `.xdelta` patch is selected to be applied.

Having "Add Checksum to patch" on in the settings (accessible via the cog in the bottom right) will stop the patch from being applied if the source WAD files are not the same, assuming the person patching has the "Checksum validation" setting applied.

## Applying a patch

To apply a patch, select the vanilla WAD file in the "Original file" entry. Then, choose the `.xdelta` patch file in the "XDelta patch" entry. 

In the settings, "Checksum validation" will make the patch not apply if the incorrect WAD file was chosen and the person who made the patch turned on "Add Checksum to patch" when they were making the patch. This will cause a `XD3_INVALID_INPUT` error, and if this should happen, you should ensure you are using the same exact same WAD file version as the patch creator. Turning off this setting will attempt to apply the patch regardless if the WAD file and the patch file are incompatible, which may or may not work as intended.

Turning on "Backup original file" creates a new WAD file instead of irreversibly applying the patch to the WAD file directly. This new file is called the same as the original WAD file, but with `PATCHED` added to the end of the filename (so applying a patch to a `data.win` file will be saved as `dataPATCHED.win`).

