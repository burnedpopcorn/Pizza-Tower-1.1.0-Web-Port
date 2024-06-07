# Possible Fix Ideas
This page is to document what I think are causing issues, which should (barely) help developers improve this project

(Update: See Open Issue #14, I had a thought but I ain't placing it here because this place is already too unreadable)

## Game Frame Misplacement
The current Game Frame is heavily misplaced on most monitors. The best solution (as in a duct-tape fix) to this issue is probably to force fullscreen immediately after the game runs. The best way to force fullscreen is probably making changes in the decompiled game code
(using GameMaker Studio 2, obviously), but it also might be possible to modify runner.html to force fullscreen as well (but the former is probably better).
- It also could be because on start-up, it disables extensions by default (the console output proves this: ctx.enableExtensionsByDefault = 0 )

## No Sound (FMOD)
The game also has no sound, either because FMOD is not initializing during startup, or it cannot locate the .bank files (but it could be both idk). The directory where FMOD expects the .bank files to be should either be 
- /sound/desktop/[4 different bank files].bank
- Or /assets/sound/desktop/[4 different bank files].bank
- But the game can't locate them in either one.
This is probably due to the fact FMOD isn't officially supported on GX.GAMES (VM), and I have no idea how to fix this or even where to start, so I doubt seeing sound working anytime in the foreseeable future.
- It also could be because it disables extensions by default, like previously stated in Game Frame Misplacement, and/or it fails to start FMOD ( Initializing FMOD: 0 ), but I'm not sure if that means that it fails to Initialize, as it still calls for the .bank files

One idea I have is to extract all the sound files from the .bank files and place them into a sound folder, which then we would manually remove and replace all FMOD sound functions with functions that would call the appropriate sound file when needed. This would most likely work, as I'm pretty sure the April 2021 build did that and it's sound actually worked, but this would take an immense amount of time, and I honestly see no reason to do this, as most people playing this game are on chromebooks playing in class, and would disable audio anyways as to not get caught by their teachers

## ~~Knight Peppino Crash~~
(Update 6/6/24) THIS CRASH HAS BEEN PATCHED

This was caused by missing parenthesis in scr_player_knightpepslopes. I realized this when looking at an Eggplant Decomp by loypoll (same guy that made the noise update decomp used in this project), and saw the missing parenthesis. This was probably caused by an oversight within the noise update decomp itself, so I would probably be notifying loypoll about this issue so he can fix it in his decomp.
> The problematic code line is Line 77 (image_index = [ ] )

Example of UNpatched code
```
		if ispeppino
		{
			instance_create(x + (xscale * 40), y, obj_bumpeffect);
			movespeed = 0;
			vsp = -6;
			sprite_index = spr_knightpepbump;
			image_index = floorimage_number - 1;
			state = states.knightpepbump;
			fmod_event_one_shot_3d("event:/sfx/pep/groundpound", x, y);
		}
```
Example of PATCHED code
```
		if ispeppino
		{
			instance_create(x + (xscale * 40), y, obj_bumpeffect);
			movespeed = 0;
			vsp = -6;
			sprite_index = spr_knightpepbump;
			image_index = floor((image_number - 1));
			state = states.knightpepbump;
			fmod_event_one_shot_3d("event:/sfx/pep/groundpound", x, y);
		}
```

## Debug Console and Commands
This doesn't affect most players that much, but the Debug Console would be a nice addition, especally for players on school chromebooks, as their saves
don't persist after logging off their account. The Debug Console isn't unaccessable, as it enabled by default (for some reason, but I'm not complaining about that), but:
- Commands don't work and
- Chromebooks cannot access it because the lack the F5 key

Commands don't work probably because the text is Capitialized for some reason, and you can't type in underscores ( _ ), which are necessary for some commands. This is an issue that I again have no idea where to start when discussing possible fixes, but all I know is that this is a GX.GAMES export only problem, as a Windows export works prefectly with Commands (same as with the Game Frame issue)

Chromebooks are unable to access the console completely, because of a lack of an F5 key. I have managed to modify the decompiled code to allow F5 OR the Tab key to open the console (See Closed Issue #2), but I have not applied this "fix" onto the
demo site, or even into the recent Revision 1 Files that I have uploaded, because its kind of useless without functioning commands (also because I modified other scripts without reverting those changes, so it is untrustworthy at the moment).

Also I have no idea why Peppino's Clothes are Yellow
