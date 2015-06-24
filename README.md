# EEKeeper-OSX
EE Keeper with Wine-wrapper for OSX

/************************************************************************************
Copyright (c) 2000 Aaron O'Neil
All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

1) Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

2) Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

3) Redistributions in binary form must reproduce the above copyright notice on program startup. Additional credits for program modification are acceptable but original copyright and credits must be visible at startup.

4) You may charge a reasonable copying fee for any distribution of Shadow Keeper. You may charge any fee you choose for support of Shadow Keeper. You may not charge a fee for Shadow Keeper itself.

THIS SOFTWARE IS PROVIDED BY THE AUTHOR ``AS IS'' AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

**************************************************************************************/

/**************************************************************************************
Version Information
**************************************************************************************/

Currently works on XP SP2/SP3, Windows Vista, Windows 7, Windows 8.

1.0.2.4
* Implemented exporting as CHR rather than just as CRE. Exporting an entire party can now be done directly from within Keeper.
* More information can be found in the Creature Browser by enabling that option. To reduce clutter, this option can be disabled.
* Added AC Modifiers to editor under the Resistances tab.
	* Please note that results may vary and may not appear in-game under the character statistics.
* Removed Saving Throws tab and merged it with Resistances.
* Added three more options to the Characteristics tab for the sake of completeness.
* Tweaked the Appearance tab so that an option can be enabled to have the colour icons appear similar to how they appear in-game (round), square (original Shadow Keeper/EE Keeper), or a large variation of those two.
* Tweaked the Installation Directory settings dialog, it now how language names rather than system locale abbreviations; example, 'English' instead of 'lang/en_US/'
* Replaced almost all text strings and placed them into the resource file, this now makes translation possible and easy.
* Changed the way spell icons are read so that Innate spell icons now display appropriately.
* Language picker added to 'View'. Available languages will appear here.
* Changed the way spell icons are read so that Innate spell icons now display appropriately.
* Incorporated use of an INI configuration file for the sake of portability and so that the editor can have multiple instances with different settings loaded.

1.0.2.3 - minor build for 'Stored Locations'
* Fixed a bug from the original code where the stored locations would not write to the appropriate place if there was a stored location saved; e.g. a stored location for the Pocket Plane.
* As above, this also corrects an issue that occurred where the offset that denotes the end of the Familiar structure would never update.
* Added a portrait display under the game image; should save confusion if the user has multiple save games under the same name.
* Tweaks and additions for future updates; some are disabled.

1.0.2.2 - Unicode support
* UTF-8 support for all files.
* Exporting item and spell lists now also supports UTF-8 encoding.
* Exporting item and spell lists has also been improved (no more "Include Descriptions?" message box).
* Kits now read from game files; please note any strange behaviour (especially with mods) on the Baldur's Gate forum.
* Other minor tweaks.

1.0.2.1 - minor build for Baldur's Gate II: Enhanced Edition release.
* Fixed issue with loading Black Pits save games with less than six characters in the party.
* Added support for Baldur's Gate II: Enhanced Edition
* Rewrote the inventory icon display code for some of the higher resolution item icons.


1.0.2.0 - Second major release.
+ Characteristics tab, added extra flags that were not in the original Shadow Keeper.
    * Most powerful vanquished (this includes a new button similar to the character name selector).
    * Number of kills: chapter.
    * Number of kills: game.
    * Experience value of kills: chapter.
    * Experience value of kills: game.
    * Set Exportable.
    * Set Been in party.
    * Set Uninterruptible.
    * Added option for Fallen Paladin and Ranger.
    * Dual class options.
        * This also fixes a bug whereby any dual-class character saved would become a multi-class character.
        * A bug was also fixed where dual-class detection was not working the way it is supposed to , and proficiencies were not being loaded correctly.

+ Abilities tab, added the following options.
    * Morale.
    * Morale break.
    * Moral recovery.
    * Fatigue.
    * Intoxication.

+ Inventory.
    * New dialog window to set item flags; Identified, Given, Stolen, Undroppable.
        * This also adds the option to identify only a selected item, or to undo an ID action on any item.

+ Added Journal tab, removed State Flags tab.
    * Journal entries and flags are not currently editable.
    * State flag has now been moved to the 'Characteristics' tab.
        * This also fixed a bug where the new flags caused the program to save multiple flags that were not selected.  Since only flag is active at any given time, it has been replaced with a combo-box (drop-down list).

+ UI Tweaks, save game, and game installation detection.
    * Now opens and saves Black Pits and Multiplayer save games, as well as the standard Single Player games.
    * EE Keeper no longer uses the Shadow Keeper method of executable detection, and instead uses the Chitin.key file to see if the directory is a valid installation.  This should remove the problem for both Steam users and Mac users.  Also note that this is entirely optional, even if the game cannot 'be found' the user can still click 'Yes' when asked if it is the correct directory; if it is not, resources simply won't load.
    * New toolbar with larger buttons.
    * Option to select custom save game location.
        * Plesae note that when using a custom location, selecting a save game from anything other than the currently loaded resources will end up with errors (missing items, spells, etc.).
    * Save game image now displays instead of a grey box.
    * Options to set both BG:EE and BG2:EE installation locations will be available in the next build;
        * Switching between the two from buttons provided on the toolbar will also be available in the next build.

+ Affects.
    * The 'Edit Affects' dialog now has pre-loaded drop-down lists for:
        + Type;
        + Target;
        + Flags;
        + and Resistance.
    * Text (for example, target being "Self") now appears in the table instead of its numeric equivalent, this should help make it less confusing at a glance, and should make it easier when selecting a certain affect, such as Aura Cleansing, from within the editing dialog.
    * Affects for some old CRE files were not read correctly by either Shadow Keeper or EE Keeper, this has since been fixed and now reads and save correctly.

+ Spell and Item List Exporting.
    * Lists now export as either text or CSV.
+ Spell Browser.
    * Numerous new options added to the filter dialog.
+ Item Browser.
    * Some new options added to the filter dialog, as well as making item type detection slightly better.
    
+ Super sneaky ninja update
    * Fixed an issue with the new journal tab.
    * Some grammar fixes.


1.0.1.0 - Initial release, post-beta.
+ New features include:
    * Delete button for both characters and save games;
    * Resizing and using the standard Windows Common Controls to imporve appearence;
    * Now accepts BG:EE root directory (this was by request for corss-platform);
    * Options for installation directory and langauge picker;
    * Now uses the Documents directory for save games, characters, and portraits;
    * Other misc improvements.
