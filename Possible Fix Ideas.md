# Possible Fix Ideas
This page is to document what I think are causing issues, which should (barely) help developers improve this project

## Game Frame Misplacement
The current Game Frame is heavily misplaced on most monitors. The best solution to this issue is probably to force fullscreen immediately after the game runs. The best way to force fullscreen is probably making changes in the decompiled game code
(using GameMaker Studio 2, obviously), but it also might be possible to modify runner.html to force fullscreen as well (but the former is probably better).
- It also could be because on start-up, it disables extensions by default (the console output proves this: ctx.enableExtensionsByDefault = 0 )

## No Sound (FMOD)
The game also has no sound, either because FMOD is not initializing during startup, or it cannot locate the .bank files (but it could be both idk). The directory where FMOD expects the .bank files to be should either be 
- /sound/desktop/[4 different bank files].bank
- Or /assets/sound/desktop/[4 different bank files].bank
- But the game can't locate them in either one.
This is probably due to the fact FMOD isn't officially supported on GX.GAMES (VM), and I have no idea how to fix this or even where to start, so I doubt seeing sound working anytime in the foreseeable future.
- It also could be because it disables extensions by default, like previously stated in Game Frame Misplacement, and/or it fails to start FMOD ( Initializing FMOD: 0 ), but I'm not sure if that means that it fails to Initialize, as it still calls for the .bank files

## Knight Peppino Crash
This crash occurs when hitting a wall as Knight Peppino when sliding. Also don't really know why it isn't working, but it does seem to be a problem with spr_knightpep_bump and its associated scripts, as the sprite never renders. Hopefully this
can be fixed quickly, and this is an issue I will continue to attempt to fix, as I want the full game to be at least fully playable (but remember, no promises). My next move to fix this is probably to compare Knight Peppino and Knight Noise and how they differ in the code, as Noise doesn't have this issue, so I could attempt to implement some of his code to Peppino, but this is just me throwing things at the wall without any knowledge of how things work, so who knows if this could work.

## Debug Console and Commands
This doesn't affect most players that much, but the Debug Console would be a nice addition, especally for players on school chromebooks, as their saves
don't persist after logging off their account. The Debug Console isn't unaccessable, as it enabled by default (for some reason, but I'm not complaining about that), but:
- Commands don't work and
- Chromebooks cannot access it because the lack the F5 key

Commands don't work probably because the text is Capitialized for some reason, and you can't type in underscores ( _ ), which are necessary for some commands. This is an issue that I again have no idea where to start when discussing
possible fixes.

Chromebooks are unable to access the console completely, because of a lack of an F5 key. I have managed to modify the decompiled code to allow F5 OR the Tab key to open the console (See Closed Issue #2), but I have not applied this "fix" onto the
demo site, or even into the recent Revision 1 Files that I have uploaded, because its kind of useless without functioning commands (also because I modified other scripts without reverting those changes, so it is untrustworthy at the moment).

Also I have no idea why Peppino's Clothes are Yellow
