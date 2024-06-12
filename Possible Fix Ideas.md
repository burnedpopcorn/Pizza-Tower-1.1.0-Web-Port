# Possible Fix Ideas
This page is to document what I think are causing issues, which should (barely) help developers improve this project

# Active Issues:

## No Sound (FMOD)
The game also has no sound, either because FMOD is not initializing during startup, or it cannot locate the .bank files (but it could be both idk). The directory where FMOD expects the .bank files to be should either be 
- /sound/desktop/[4 different bank files].bank
- Or /assets/sound/desktop/[4 different bank files].bank
- But the game can't locate them in either one.
This is probably due to the fact FMOD isn't officially supported on GX.GAMES (VM), and I have no idea how to fix this or even where to start, so I doubt seeing sound working using FMOD anytime in the foreseeable future.
- It also could be because it disables extensions by default, as it fails to start FMOD ( Initializing FMOD: 0 ), but I'm not sure if that means that it fails to Initialize, as it still calls for the .bank files

What will work is to extract all the sound files from the .bank files and place them into a sound folder, which then we would manually remove and replace all FMOD sound functions with functions that would call the appropriate sound file when needed. This would most likely work, as I'm pretty sure the April 2021 build did that and it's sound actually worked, but it would take alot of time.

## Mr. Mooney and Noisette Clothes Crash
The game crashes when paying Mr. Mooney or Noisette for clothes
> This is in the Last Level of the Tower, and the game can still be beaten

This was reported by @AJNurtnick (Issue #13), and I haven't attempted to recreate this crash yet, so this will be investigated further eventually.

## Clothes don't Work
Clothes can be collected, but cannot be applied
> Not sure this will be fixed anytime soon (as it's not high priority)

# Fixed Issues:

## ~~Game Frame Misplacement~~

This was caused by the GameFrame Gamemaker Extension still being in use in the web port. Removing code that initalizes the GameFrame Extension from obj_screensizer (Create) seems to fix it, but the remaining code should be forcfully set to a specific width and height to avoid possibly calling another GameFrame function (and to ensure specified width and height across the game). 
- Also included some code from the Eggplant Build's obj_screensizer (just in case it was needed)
- Other additions and removals that I will not specify here (just download the source code in the releases tab to see all changes within the code itself)

## ~~Knight Peppino Crash~~

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

## ~~Debug Console and Commands~~
This has been fixed for the most part. I say that as some commands take in extra instructions after the base commmand that won't work, as the Caps Lock issue is still present, and the game still expects
them to be lower case.
