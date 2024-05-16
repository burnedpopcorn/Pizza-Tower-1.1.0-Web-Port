# Pizza Tower 1.1.0 Web Port

A Port of Pizza Tower 1.1.0 (The Noise Update) to the Web Browser

http://pt-emscriptenport.x10.mx/runner.html

(Update: No, not to the game. This is a Revision of runner.html that repurposed unused buttons and made them accessible while in-game, and this revision has been applied on the website)

## Please read the Entire README
### Although it is very long, there are lots of important information to developers and normal users alike, so please read it. It is worth your time if you are going to contribute or at least try the demo website above

Unfornately there are many bugs that can severely impact the game such as
- No sound
- Game Frame being heavily misplaced (Somewhat Fixable through ingame settings)
- Crash as Knight Peppino when slamming into a wall at high speed
- Knight Noise lagging the game on low end hardware when single jumping, falling, or ground pounding without high speed
- And many more I did not encounter during my time play testing (which only went up to Level 3)

Although saves do work correctly
> [!NOTE]
> You should immediately toggle Borderless, then toggle Fullscreen while in-game, as it resolves the Game Frame issue, and it improves performace on extremely low-powered hardware
such as school chromebooks (for some reason)
- Also, the game lags alot when spawning particle effects and/or when blocks change (Walkable Cheese blocks) / are destroyed on low-end hardware
- And the Debug Console is toggleable using F5, but ChromeBooks can't access it. But either way it has no purpose, as commands aren't functional (See Closed Issue #2)

## Also fixes are probably not going to happen by me if at all
  
  Why? Because I'm bad at coding, and I'm not sure if this will get any attention by any developers who are willing to waste time to contribute, although I would definitely appreciate it if a dev does contribute :)

## No files will be listed here, instead being downloadable by a Google Drive Link

This Link contains The Decompiled Files (data.win files are already extracted for you), the Full Compiled PT Web Build, and the Minimalized Build that cuts out files that aren't used, so you can host Pizza Tower on your own website
### https://drive.google.com/file/d/1Fwb4DBS9ZqnVfmSa4cKKoqZM3Cymn_gX/view?usp=sharing

> [!NOTE]
> PT_WebBuild_Minimal is the same as PT_WebBuild, but only includes the files from the runner folder, as that contains the only necessary files to run Pizza Tower, and you should definitely use the Minimal build, as the extra files in the extracted web build are completely useless and just waste space on your server
### The Revision Files are here:

This Link contains only the Revision 1 Minimalized Build, as I only modified runner.html, and added primoburg'.gif for the f u n n y (and because I couldn't think of any other use for the third button)
### https://drive.google.com/file/d/1kA2Brz4mh_3VjLj_kM1eXYPTFwLqUCGo/view?usp=sharing

## To Compile and Run it for Yourself

- Use GX.GAMES and VM options to compile it, and to obtain the compiled files from GameMaker Studio for free, just go to C:/Users/(your username)/AppData/Local/GameMakerStudio2-LTS/GMS2TEMP while locally running the game
- In which you will find a folder called PizzaTower_GMS_(some numbers)_VM after you compiled the project

The said files will NOT run locally as file:// will just result in CORS errors and will not allow runner.html (the main file that runs Pizza Tower) to read the game files

The only way for them to work is if you have a web server running this, or a local server using something like python
- Which you can do by entering the directory containing runner.html and other files and typing the command python3 -m http.server in the linux terminal or py -m http.server for windows powershell given you installed python
- At which point you can enter http://localhost:8000/runner.html to play the game locally

~~I won't be hosting these files as I don't have access to a server nor will I use my own computers as a server~~

(Update: I managed to host it for free using x10hosting's free plan using a minimalized version of the compiled files which is about 280MB from the normal version which is about 680MB)

## Thanks to
- loypoll for the full decompilation of the recent Pizza Tower Update
- krzys_h and UnderminersTeam for the UnderTaleMod and the ability to decompile GameMakerStudio2 games like Undertale and Pizza Tower
- And of course Tour de Pizza for the base game

## To certain users
This project was primarily made to play Pizza Tower on locked-down school chromebooks for lazy ass students. Please do not use this project to avoid paying for the PC version of the game. By doing this you not only harming the creator of Pizza Tower, but also harming your experience with this amazing game with a version filled with bugs, crashes, and lost functionality

## To Developers
For anyone that wants to spill time into this, Visit [Possible Fix Ideas.MD](https://github.com/burnedpopcorn/Pizza-Tower-1.1.0-Web-Port/blob/main/Possible%20Fix%20Ideas.md) within this repository to see my write-up on known issues listed above, and what I observed trying to troubleshoot this game. Not sure how well this will help since
I honestly have very little idea what I'm doing half the time
