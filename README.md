EE Keeper
=========
Currently works on XP SP2/SP3, Windows Vista, Windows 7, Windows 8, and Windows 10. Mac is also semi-supported through use of Wineskin, and Linux with Wine.

For help/support questions, please go to the EE Keeper topic on the "Beamdog forum":http://forums.beamdog.com/discussions/16497/eekeeper/p1.

Version Information
===================
1.0.3.1
-------
* Fixed "Unable to locate the kit ability list" error when trying to add kit effects.
* Open Character File and Open CRE File dialog windows now replaced by standard Windows Open File dialog.  Supports multi-file selection.
* Added Character Browser.  Similar to the Creature Browser.  Can now edit characters pack into the games BIF files, not just those that have been exported.

1.0.3.0
-------
* Fixed memorisation list not clearing when the program is closed (memory leak).
* Implemented "Profiles..." menu item which loads known profiles for quicker switching.  Note: currently, it does not refresh for new profiles added after the list is loaded.
* Changing editor language via View⇒UI Language is now instant.
* Can now unzip save games from iOS/Android with the extension .bg1save: Works with or without save game number on bg1save archive.
> * If the file has no starting number, then one will be picked; priority is: if there are save games that already have numbers in excess of 100, then it will pick that number + 1.  If there are no save games with numbers in excess of 100, then it will start at 100.
> * If the file has a number, then it will use that.  Known issue:
> > * If your save game is named with just a number, e.g. 123.bg1save, then it will not be extracted.  I may or may not fix that since having a number on a bg1save file is not official behaviour.
> * Additional notes: Keeper will attempt to extract bg1save files every time the Open Save Game dialog is opened.  Keeper will delete any bg1save files it extracts to avoid repeated extraction—it will only delete items it can extract; if a save game with a number is present and is extracted once, and another bg1save by the same name and number (e.g. if there were 000000001-Quick-Save.bg1save) is present at a later time, it will not extract a second one nor will it delete the second archive.
* Update checker overhaul (code and appearance) -- no longer check for updates via About dialog.  Update checker now has its own window with a progress bar when downloading (saves a zip file to a specified location rather than doing an actual update).  Note: it should now also work slightly better with OSX, it'll look for updated wrapped versions; if no wrapped version is available, then it won't say there's an update.
* "Find Strings..." dialog changes:
> * Added "Resource" column for audio in Find Strings dialog.
> * Added "Save Strings to File" to save the current list to either CSV (default) or TXT.
* Under Settings⇒Miscellaneous, added a host of new options as well as grouping, previously only available via INI editing; as well as two new options for the new features:
> * Max HP on levelup (does exactly what you'd expect).
> * Divide HP after total sum (this applies to multi-class and dual-class characters; when enabled, you should get more HP on each roll.  The effect can be seen when comparing a freshly created character in BG:EE at level 1, and a new character in BG2:EE, then levelling up the BG:EE character and comparing the total HP).
*Update Bonus Stats and Recalculate Stats buttons added to main creature editor; Enhanced Editions only:
> * Update Bonus Stats updates only the total values, not the base stats.  This option does not change the creature/character/save in any way unless already edited (it makes sure that the values changed actually impact the total—so, for example, if you change dexterity, it'll set it and use the updated value when calculating the armour class total—this is the same as when making an edit and moving to another party character).
> * Recalculate Stats updates the base values and totals.  If you're using a custom value for something like HP, that's going to get reset.  This should reset everything to what they should be as per the engine rules.  Could be potentially hazardous.  HP, AC, THAC0, Thief Skills, and Saving Throws will all be set to their appropriate amount.  May or may not work with modded kits—feedback welcomed.  Might add spell slots and proficiency points display next—possibly also automating bonus spells if more are found in the list than there should be according to the game tables.
* Better thief skill readout; Enhanced Editions only:
> * Only works for classes that should have thief skills; thief, bard, ranger, monk, and dual/multi-classed thieves.
> * Displays bonuses from dexterity when Update Bonus Stats is pressed.
> * Readout to show the total available points to spend and how many are left to spend; [currently availably] / [total]
> * Dual-class thieves will not show points to spend if thief class is set to be the original class, will fix in next build.
> * Rangers and monks will increase as per game tables, they won't display points to spend.
* Changed types for THAC0 and Resistances (all); these are now signed values: -128 to 127.
* Saving throws can now go to 0, instead of being reset to 1. Thanks to @ogreb for pointing that out.
* Journal can now show time/date stamp (option "Show Journal Date"); there are four options for flavour (these have not been put into the settings dialog):
> * 0x00 - No date stamp
> * 0x01 - Date stamp on both journal entry in list and text output (default)
> * 0x10 - Date stamp on entry in list only
> * 0x11 - Data stamp on text output only

1.0.2.9
-------
* All windows now store size and state.
* Memorisation tab now includes Add, Edit, and Remove buttons.
> * This will also fix the issue with Innate abilities being added manually not showing up in-game.  if a save game does not include Innate, add it if desired.
* Added check for file length when using Convert to X options.  File name length can be no longer than 8, excluding the 4 characters that make up the extension.

1.0.2.8
-------
* Fixed window placement issue when minimised.
* Window placement is now restored when minimised or maximised.  If the window is maximised when exiting the application, it will be maximised when it is next launched.
* Window placement is now stored in a new INI setting - Window State.   This has found possible settings:- 0=Hidden (avoid using 0, it won't appear in the taskbar), 1=Normal, 2=Minimised, 3=Maximised.

1.0.2.7
-------
* Added 'Find Strings' to View menu.
* Added update checker to the About dialog.

1.0.2.6
-------
* Added sorting via any column in the creature browser.
* Improved the Folder Browser; now goes to whatever the folder location is currently in the text box, if no folder is selected then it will go to Documents.
* Another tweak to kit name detection.
* Overridden most windows registry calls; it should no longer read or write from or to the registry.
* Reduced the number of times EE Keeper reads and writes to the config INI file.
* Added six new INI options to replace calls to the registry:-
> * x = int
> * y = int
> * width = int
> * height = int
> * Show Status bar = boolean
> * Show Toolbar = boolean

1.0.2.5
-------
* Add new Miscellaneous and Local Variable tabs;
> * Miscellaneous tab allows editing of old proficiencies, scripts, and other miscellaneous chatacter options.
* Made Icewind Dale: Enhanced Edition ready.
> * This also includes a rewrite to the Black Pits code.
* Redesigned the Installation Directory settings and removed multiple buttons on the toolbar for each game.
* Redesigned the Effects editor; now includes IESDP descriptions.
* Implemented translations for Chinese, French, Italian, and Korean.

1.0.2.4
-------
* Implemented exporting as CHR rather than just as CRE.  Exporting an entire party can now be done directly from within Keeper.
* More information can be found in the Creature Browser by enabling that option.  To reduce clutter, this option can be disabled.
* Added AC Modifiers to editor under the Resistances tab.
> * Please note that results may vary and may not appear in-game under the character statistics.
* Removed Saving Throws tab and merged it with Resistances.
* Added three more options to the Characteristics tab for the sake of completeness.
* Tweaked the Appearance tab so that an option can be enabled to have the colour icons appear similar to how they appear in-game (round), square (original Shadow Keeper/EE Keeper), or a large variation of those two.
* Tweaked the Installation Directory settings dialog, it now how language names rather than system locale abbreviations; example, 'English' instead of 'lang/en_US/'
* Replaced almost all text strings and placed them into the resource file, this now makes translation possible and easy.
* Changed the way spell icons are read so that Innate spell icons now display appropriately.
* Language picker added to 'View'.  Available languages will appear here.
* Changed the way spell icons are read so that Innate spell icons now display appropriately.
* Incorporated use of an INI configuration file for the sake of portability and so that the editor can have multiple instances with different settings loaded.

1.0.2.3 - minor build for 'Stored Locations'
-------
* Fixed a bug from the original code where the stored locations would not write to the appropriate place if there was a stored location saved; e.g. a stored location for the Pocket Plane.
* As above, this also corrects an issue that occurred where the offset that denotes the end of the Familiar structure would never update.
* Added a portrait display under the game image; should save confusion if the user has multiple save games under the same name.
* Tweaks and additions for future updates; some are disabled.

1.0.2.2 - Unicode support
-------
* UTF-8 support for all files.
* Exporting item and spell lists now also supports UTF-8 encoding.
* Exporting item and spell lists has also been improved (no more "Include Descriptions?" message box).
* Kits now read from game files; please note any strange behaviour (especially with mods) on the Baldur's Gate forum.
* Other minor tweaks.

1.0.2.1 - minor build for Baldur's Gate II: Enhanced Edition release.
-------
* Fixed issue with loading Black Pits save games with less than six characters in the party.
* Added support for Baldur's Gate II: Enhanced Edition
* Rewrote the inventory icon display code for some of the higher resolution item icons.

1.0.2.0 - second revision.
-------
* Characteristics tab.
> * Added extra flags that were not in the original Shadow Keeper.
> > * Most powerful vanquished (this includes a new button similar to the character name selector).
> > * Number of kills: chapter.
> > * Number of kills: game.
> > * Experience value of kills: chapter.
> > * Experience value of kills: game.
> > * Set Exportable.
> > * Set Been in party.
> > * Set Uninterruptible.
> > * Added option for Fallen Paladin and Ranger.
> > * Dual class options.
> > > *  This also fixes a bug whereby any dual-class character saved would become a multi-class character.
> > > *  A bug was also fixed where dual-class detection was not working the way it is supposed to , and proficiencies were not being loaded correctly.

* Abilities tab.
> *  Added the following options.
> > * Morale.
> > * Morale break.
> > * Moral recovery.
> > * Fatigue.
> > * Intoxication.

* Inventory.
> *  New dialog window to set item flags; Identified, Given, Stolen, Undroppable.
> > * This also adds the option to identify only a selected item, or to undo an ID action on any item.

* Added Journal tab.
> *  Journal entries and flags are not currently editable.

* Removed State Flags tab.
> *  State flag has now been moved to the 'Characteristics' tab.
> *  This also fixed a bug where the new flags caused the program to save multiple flags that were not selected.  Since only flag is active at any given time, it has been replaced with a combo-box (drop-down list).

* Effects.
> * The 'Edit Affects' dialog now has pre-loaded drop-down lists for:
> > * Type
> > * Target
> > * Flags
> > * and Resistance.
> * Text (for example, target being "Self") now appears in the table instead of its numeric equivalent, this should help make it less confusing at a glance, and should make t easier when selecting a certain affect, such as Aura Cleansing, from within the editing dialog.
> * Affects for some old CRE files were not read correctly by either Shadow Keeper or EE Keeper, this has since been fixed and now reads and save correctly.

* UI Tweaks, save game, and game installation detection.
> * Now opens and saves Black Pits and Multiplayer save games, as well as the standard Single Player games.
> * EE Keeper no longer uses the Shadow Keeper method of executable detection, and instead uses the Chitin.key file to see if the directory is a valid installation.  This should remove the problem for both Steam users and Mac users.  Also note that this is entirely optional, even if the game cannot 'be found' the user can still click 'Yes' when asked if it is the correct directory; if it is not, resources simply won't load.
> * New toolbar with larger buttons.
> * Option to select custom save game location.
> > * Plesae note that when using a custom location, selecting a save game from anything other than the currently loaded resources will end up with errors (missing items, spells, etc.).
> * Save game image now displays instead of a grey box.
> * Options to set both BG:EE and BG2:EE installation locations will be available in the next build;
> > * Switching between the two from buttons provided on the toolbar will also be available in the next build.

* Spell and Item List Exporting.
> * Lists now export as either text or CSV.

* Spell Browser.
> * Numerous new options added to the filter dialog.

* Item Browser.
> * Some new options added to the filter dialog, as well as making item type detection slightly better.

1.0.1.0 - Initial release
-------
New features include:

* Delete button for both characters and save games.
* Resizing and using the standard Windows Common Controls to improve appearance.
* Now accepts BG:EE root directory (this was by request for cross-platform)
* Options for installation directory and language picker.
* Now uses the Documents directory for save games, characters, and portraits.
* Other misc improvements.

Licence
=======
Original Shadow Keeper licence:

Copyright (c) 2000 Aaron O'Neil
All rights reserved.


Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:


    1) Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.


    2) Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.


    3) Redistributions in binary form must reproduce the above copyright notice on program startup. Additional credits for program modification are acceptable but original copyright and credits must be visible at startup.


    4) You may charge a reasonable copying fee for any distribution of Shadow Keeper. You may charge any fee you choose for support of Shadow Keeper. You may not charge a fee for Shadow Keeper itself.


THIS SOFTWARE IS PROVIDED BY THE AUTHOR ''AS IS'' AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
