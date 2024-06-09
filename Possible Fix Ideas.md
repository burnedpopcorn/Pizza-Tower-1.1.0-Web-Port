# Possible Fix Ideas
This page is to document what I think are causing issues, which should (barely) help developers improve this project

(Update: See Open Issue #14, I had a thought but I ain't placing it here because this place is already too unreadable)

## Game Frame Misplacement
The current Game Frame is heavily misplaced on most monitors. The best solution (as in a duct-tape fix) to this issue is probably to force fullscreen immediately after the game runs. The best way to force fullscreen is probably making changes in the decompiled game code
(using GameMaker Studio 2, obviously), but it also might be possible to modify runner.html to force fullscreen as well (but the former is probably better).

## No Sound (FMOD)
The game also has no sound, either because FMOD is not initializing during startup, or it cannot locate the .bank files (but it could be both idk). The directory where FMOD expects the .bank files to be should either be 
- /sound/desktop/[4 different bank files].bank
- Or /assets/sound/desktop/[4 different bank files].bank
- But the game can't locate them in either one.
This is probably due to the fact FMOD isn't officially supported on GX.GAMES (VM), and I have no idea how to fix this or even where to start, so I doubt seeing sound working using FMOD anytime in the foreseeable future.
- It also could be because it disables extensions by default, like previously stated in Game Frame Misplacement, and/or it fails to start FMOD ( Initializing FMOD: 0 ), but I'm not sure if that means that it fails to Initialize, as it still calls for the .bank files

What will work is to extract all the sound files from the .bank files and place them into a sound folder, which then we would manually remove and replace all FMOD sound functions with functions that would call the appropriate sound file when needed. This would most likely work, as I'm pretty sure the April 2021 build did that and it's sound actually worked, but it would take alot of time.

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

## ~~Debug Console and Commands~~
This has been fixed for the most part. I say that as some commands take in extra instructions after the base commmand that won't work, as the Caps Lock issue is still present, and the game still expects
them to be lower case.

Also I have no idea why Peppino's Clothes are Yellow
