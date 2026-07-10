# WAD Files

When a GameMaker game is compiled and distributed, all of the game's logic and most of its assets are stored in a WAD ("Where's All the Data?") file. The default name for the WAD file will change based on what operating system the game was compiled for.

Operating System | WAD File Name
--- | ---
Windows | `data.win`
Linux | `game.unx`
macOS / iOS | `game.ios`
Android | `game.droid`

Note that the WAD file is not the `.exe` file, which also usually exists in the same directory where the WAD file is.

The default location of the WAD file depends on which operating system the game was downloaded on. 

## UNDERTALE

The following are the default WAD file paths for UNDERTALE if it was installed through Steam:

Operating System | Default UNDERTALE WAD File Path
--- | ---
Windows | `C:\Program Files (x86)\Steam\steamapps\common\Undertale\data.win`
Linux | `~/.local/share/Steam/steamapps/common/Undertale/assets/game.unx`
macOS | `Library/Application Support/Steam/steamapps/common/Undertale/UNDERTALE.app/Contents/Resources/game.ios`

## DELTARUNE Demo

The WAD files for the DELTARUNE demo can be found in the following places if installed through Steam:

Operating System | Default DELTARUNE Demo WAD File Path
--- | ---
Windows | `C:\Program Files (x86)\Steam\steamapps\common\DELTARUNEdemo\data.win`
macOS | `Library/Application Support/Steam/steamapps/common/DELTARUNEdemo/DELTARUNE.app/Contents/Resources/game.ios`

## DELTARUNE

Instead of having all of DELTARUNE's logic in one WAD file, the purchasable release of DELTARUNE contains a Chapter Select WAD file and then individual WAD files for each chapter. The Chapter Select WAD file can be found in the following directories:

Operating System | Default DELTARUNE Chapter Select WAD File Path
--- | ---
Windows | `C:\Program Files (x86)\Steam\steamapps\common\DELTARUNE\data.win`
macOS | `Library/Application Support/Steam/steamapps/common/DELTARUNE/DELTARUNE.app/Contents/Resources/game.ios`

The directory that has the Chapter Select WAD file also contains folders for each chapter, with each folder containing the WAD file for that chapter. The folders are named as follows, with `X` representing the chapter number:

Operating System | Default DELTARUNE Chapter Folder Name
--- | ---
Windows | `chapterX_windows`
macOS | `chapterX_mac`