# Possible Fix Ideas
This page is to document what I think are causing issues, which should (barely) help developers improve this project

# Active Issues:

## No Sound (FMOD)
The game also has no sound, maily because FMOD can't access the .bank files, as it look into IndexedDB for the files instead of the server where the main game files come from

For this reason, FMOD will most likely NEVER work on a Web Port, unless there is a method I haven't tried yet
> Yes, I've tried pointing FMOD to look at direct download links to the files, but nothing

What will work is to extract all the sound files from the .bank files and place them into a sound folder, which then we would manually remove and replace all FMOD sound functions with functions that would call the appropriate sound file when needed. This would most likely work, as I'm pretty sure the April 2021 build did that and it's sound actually worked, but it would take alot of time.
> I have made a seperate repo about that

## Clothes don't Work
Clothes can be collected, but cannot be applied

What is the problem is that the Retro Palette Shader, ```shd_pal_swapper```, doesn't support a GX.GAMES build
> It supports a HTML build, but the rest of the source code does not

Because of this, this issue will probably never be fixed

# Fixed Issues:

## ~~Game Frame Misplacement~~

This was caused by the GameFrame Gamemaker Extension still being in use in the web port. Removing code that initalizes the GameFrame Extension from ```obj_screensizer``` (Create) seems to fix it, but the remaining code should be forcfully set to a specific width and height to avoid possibly calling another GameFrame function (and to ensure specified width and height across the game). 
- Also included some code from the Eggplant Build's ```obj_screensizer``` (just in case it was needed)
- Other additions and removals that I will not specify here (just download the source code in the releases tab to see all changes within the code itself)

## ~~Knight Peppino Crash~~

This was caused by missing parenthesis in ```scr_player_knightpepslopes```. I realized this when looking at an Eggplant Decomp by loypoll (same guy that made the noise update decomp used in this project), and saw the missing parenthesis. This was probably caused by an oversight within the noise update decomp itself, so I would probably be notifying loypoll about this issue so he can fix it in his decomp.
> The problematic code line is Line 77 (```image_index = [ ]```)

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
This has been fixed for the most part. I say that as commands that take in extra instructions after the base commmand won't work, as the Caps Lock issue is still present, and the game still expects them to be lower case.

The Fix was to just make all the commands Upper-Case and into one Word (instead of underscores)

## ~~Mr. Mooney and Noisette Clothes Crash~~
> This was reported by @AJNurtnick (Issue #13), and has been fixed since Revision 5

loypoll ended up fixing it for me after I reported this issue to him, so easy fix on my part :)
- The problem ended up being him forgeting to provide a definition for the variable ```pals``` in ```obj_mrmooney``` in his decomp, which is the base for this port

But now he included it, so its fixed
