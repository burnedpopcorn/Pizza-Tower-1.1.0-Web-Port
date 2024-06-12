# Pizza Tower 1.1.0 Web Port

A Port of Pizza Tower 1.1.0 (The Noise Update) to the Web Browser

https://pt-emscriptenport.x10.mx/runner.html

Minimalistic verison here: https://pt-emscriptenport.x10.mx/barerunner.html

### MORE UPDATES (6/11/24)
- Game Frame is fixed now
> Thanks to Neybo for leading me in the right direction (Issue #15)
- Level Select is now located in the Old Tower Secret Room and has its own dedicated Starting Gate
> The Old Pizza Box has been removed from Tower Entrance
- Tutorial Blocks have been removed from the Tower Entrance
> Tutorial Completion is still needed to unlock Lap 2

Also will include my barerunner.html project within the website, so you can visit https://pt-emscriptenport.x10.mx/runner.html AND https://pt-emscriptenport.x10.mx/barerunner.html
> barerunner.html is a minimalist verison of runner.html designed by me and is a complete replacement to it (see my barerunner repo if you're intrested)

This Patch has been applied to the main site (remember to clear your site cache)

### ANOTHER Update 6/10/24: 
> (Most) Commands now work, and I reused the Eggplant Build's Level Select and reimplimented it and redesigned it
>
> (Also the Noise is now unlocked by Default)
> 
> - Press CTRL or F8 for Debug HUD (Just FPS counter and Memory Visualizer)
> - Press ALT or F6 to Switch Characters (Peppino / Noise) on the Fly (Regardless of Save Type Selected)
> - Press F5 OR Tab to Open the Console

(Update 6/6/24: THE KNIGHT PEPPINO CRASH HAS BEEN FIXED! READ THE OTHER .MD FILE IN THIS REPO FOR MORE INFO)

### ALSO CLEAR YOUR SITE CACHE IF YOU HAVE PLAYED THIS PORT BEFORE THIS UPDATE 
(Outdated Cache causes another crash, so clear it)

## Please read the Entire README
### Although it is very long, there are lots of important information to developers and normal users alike, so please read it. It is worth your time if you are going to contribute or at least try the demo website above

Unfornately there are many bugs that can negatively impact the game such as
- No sound
- Crash when buying clothes from Mr. Mooney or Noisette in the last Level of the Tower (See Open Issue #13)
- And many more I did not encounter during my time play testing

Although saves do work correctly

## Downloads

For Self Hosting, Download the self hosting files in the Releases Tab

For Developing, Download The (Modified) Decompiled Files from the Releases Tab (data.win files are already extracted for you)

## To Compile and Run it for Yourself

> [!WARNING]
> Use the 2022 LTS Gamemaker runtime (Runtime 2022.0.1.30), as anything older or anything newer will eventually cause problems while compiling

- Use GX.GAMES and VM options to compile it, and to obtain the compiled files from GameMaker Studio for free, just go to ```C:/Users/(your username)/AppData/Local/GameMakerStudio2-LTS/GMS2TEMP``` while locally running the game
- In which you will find a folder called ```PizzaTower_GMS_(some numbers)_VM``` after you compiled the project

The said files will NOT run locally as file:// will just result in CORS errors and will not allow runner.html (the main file that runs Pizza Tower) to read the game files

> [!NOTE]
> The YYC Compiler Option does work, but you need Emscripten installed, and nothing is lost nor gained, so I recommend VM, as you don't need to waste time installing Emscripten and there are no upsides anyways

The only way for them to work is if you have a web server running this, or a local server using something like python
- Which you can do by entering the directory containing ```runner.html``` and other files and typing the command ```python3 -m http.server``` in the linux terminal or ```py -m http.server``` for windows powershell given you installed python
- At which point you can enter ```http://localhost:8000/runner.html``` to play the game locally

## Thanks to
- loypoll for the full decompilation of the recent Pizza Tower Update
- krzys_h and UnderminersTeam for the UnderTaleMod and the ability to decompile GameMakerStudio2 games like Undertale and Pizza Tower
- And of course Tour de Pizza for the base game

## To certain users
This project was primarily made to play Pizza Tower on locked-down school chromebooks for lazy ass students. Please do not use this project to avoid paying for the PC version of the game. By doing this you not only harming the creator of Pizza Tower, but also harming your experience with this amazing game with a version filled with bugs, crashes, and lost functionality

## To Developers
For anyone that wants to spill time into this, Visit [Possible Fix Ideas.MD](https://github.com/burnedpopcorn/Pizza-Tower-1.1.0-Web-Port/blob/main/Possible%20Fix%20Ideas.md) within this repository to see my write-up on known issues listed above, and what I observed trying to troubleshoot this game. Not sure how well this will help since
I honestly have very little idea what I'm doing half the time
