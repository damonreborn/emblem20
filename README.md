### Some frequently asked questions: ###

## What is Emblem20? ##

Emblem20 is a system of scripts and sheets built for Roll20 for [Xeohelios'](https://reddit.com/user/xeohelios) [Fire Emblem Tabletop system](https://www.dropbox.com/sh/fvib0sh0o4fqt8d/AACJ66fUDtxL5atM5-ZcE8Ypa?dl=0), automating most of the complicated calculations that go into one round of combat. This means that you can play fast-paced, full-scale Fire Emblem tabletop campaigns with your friends! As of now, Emblem20 *is* live on both the [Roll20 Character Sheets](https://github.com/Roll20/roll20-character-sheets) repository and the [Roll20 API Scripts Repository](https://github.com/missing-q/roll20-api-scripts), and can be added to a game on the main site. However, I can't guarantee those will always be 100% up-to-date, as pull requests only really get merged around Wednesday or so and I'm constantly making changes and updating things, etc. General rule of thumb is that this repository will have the newest updates, but the version on Roll20 will be the easiest to add to your game (and the most stable, probably).

## What Fire Emblem era/system does Emblem20 use? ##

Emblem20 is a mixture of Awakening/Fates mechanics (as per the original tabletop system) and GBA (FE6-8) mechanics, as well as a handful of homebrew fluff I've added myself. In the future, I plan to have different "packages" for different Fire Emblem game playstyles. Right now, mechanics include:
- 3 weapon triangles! The melee triangle (swords, axes, lances), the magic triangle (anima, light, dark), and the ranged weapon triangle (bows, daggers, firearms).
- Different healing and status staves
- Different promotional items for each class
- Light tomes deal little damage with a wide range, and dark tomes gain stacking bonuses when being used against another tome-user (not implemented yet).
- Firearms don't use strength in their calculations, instead running off of pure Might, and are counted as a separate damage type. 
- Weapon usabilty checking based on class and weapon rank. Not implemented yet for staves, but implemented for normal battle. 
- Broken weapons have "broken" appended to their names when they run out of uses, and their rank is set UU (unusable)! This allows for them to be repaired at the GM's discretion (or alternatively, deleted).
- A fully-fledged, dynamic skills system allowing for the creation of custom skills! See the [wiki](https://github.com/missing-q/emblem20/wiki) for more details!

## To Do ##
- Add more skill parameters, features, etc. as dictated by missing skills in the [wiki.](https://github.com/missing-q/emblem20/wiki)
- Implement the different effects of different magic types
- Make an easy way to do terrain bonuses and other out-of-battle factors that influence hit/crit/avo. Maybe a macro?
- Add different "FE Era packages"- one with pure Fates mechanics, pure Path of Radiance mechanics, etc.
- Stat initialization *before* adding a character's class for the possibility of creating attackable obstacles (alternatively, add an "object" class with no stats?)
- Change the way attacking without a weapon is handled-instead of checking to see if the unit can use the stones/other weapon type (which is the current system, to accomodate for the homebrew Fists weapon type), make a separate flag for if they can attack without a weapon (which should be set to false by default).
- Not a priority right now, but eventually style the battle messages to make them more visually appealing. It's possible to implement this at the moment, but I'd like to get more work done on more important features first.

## How can I use this now? ##

Well, right now, the best way to use it is copy-paste the code into your own game! Be warned, this requires a premium or a pro account.

1. Copy all of sheet.html, and when you open up your game management screen on Roll20, click on the dropdown to the right. You should see the **Game Settings** option. Open that up.
2. On your game settings, set the character sheet type to **custom sheet**. This will open up a code editor. Paste the entirety of sheet.html in the HTML tab.
3. Copy all of sheet.css, and likewise, paste it into the CSS tab. Save your game settings at this point.
4. Now go back to the game management screen, and click on API scripts. Click on the New Script tab. Copy and paste base.js, item.js, and staff.js into their own separate script tabs.
5. Finally, go into your game, and click to the macros tab. Copy-paste these macros into your game- the scripts won't work without them otherwise.

**Attack**

`!combat @{selected|token_id} @{target|token_id}`

**Use-item**

`!item @{selected|token_id} ?{Item|@{selected|item_name0}|@{selected|item_name1}|@{selected|item_name2}}`

**Use-staff**

`!staff @{selected|token_id} @{target|token_id}`

For convenience' sake, check the box that says "Show as token action". Make sure to select the token you're using before taking any actions.

**The macros and their linked scripts will *not work properly* on a token if it's not linked to a character in the Journal.**

Have fun!
