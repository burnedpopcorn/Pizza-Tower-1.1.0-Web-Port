# Pizza Tower 1.1.0 Web Port

A Port of Pizza Tower 1.1.0 (The Noise Update) to the Web Browser

NEW! Sound Build: https://www.autistici.org/burnedprojects/pt_noise_build/runner.html

NEW Minimalistic verison: https://www.autistici.org/burnedprojects/pt_noise_build/barerunner.html

> [!NOTE]
> No Sound Build is here:
> 
> https://pt-emscriptenport.x10.mx/runner.html
> 
> Minimalistic verison here: https://pt-emscriptenport.x10.mx/barerunner.html
> 
> itch.io Upload: https://burnedpopcorn.itch.io/pizza-tower-110-web-port

### Other Ports I've made:
- Cheesed Up Web Port
- Scoutdigo v1.2 Web Port
- Sugary Spire Web Port (Based Off Playtest 3.2 Source Code)

Look for them in my Repos!

## Current state of the Project

Unfornately there are still some bugs that can negatively impact the game such as
- No Clothes Swapping / Peppino's Clothes being forced Yellow
> Playtesting went as far as to beat the game (BOTH ENDINGS as Peppino & Noise) and basic use of Swap Mode

- Also gonna try and improve the Level Select some more

Luckily, I have managed to fix many crashes and issues along the way, so the game is very playable now with NO CRASHES, and has some added extra features that even the vanilla game lacks

## Extra Features
- Level Select
    > Level Select Entrance is located in the Old Tower Secret Room (First Floor)
- Custom Commands
    > Currently there is only one, ```LEVELSELECT```, which brings you to the Level Select (EXPERIMENTAL and currently has issues, so I recommend the Intended Entrance instead)
- Custom Keybinds
    > ```TAB / F5``` opens the Console
    >
    > ```CTRL / F8``` activates command ```DEBUGHUD```, which displays a FPS counter and what seems to be a Memory Visualizer
    > 
    > ```ALT / F6``` activates command ```SWITCHCHAR```, which lets you switch characters immediately (Certain animations can delay or prevent this effect)

## Downloads

For Self Hosting, Download the self hosting files in the Releases Tab

For Developing, Download The (Modified) Decompiled Files from the Releases Tab (data.win files are already extracted for you)

## To Compile and Run it Locally

> [!WARNING]
> For Legacy Revision 6, Use the 2022 LTS Gamemaker runtime (Runtime 2022.0.1.30)
>
> For the Latest Revision, Use GameMaker Version 2023.2.0.71

For Instructions on how to compile this Project, please read my WebAssembly Compilation Instructions [HERE](https://burnedwebsite.vercel.app/guide/)
> This guide should explain how you can compile any GameMaker Studio 2 project for the Browser with Maximum Compatibility, For completely Free, and without the terrible HTML Export

## Thanks to
- loypoll for the full decompilation of the recent Pizza Tower Update
> but still, fuck you for falsely DMCA'ing my Cheesed Up Web Ports
- krzys_h and UnderminersTeam for the UnderTaleMod and the ability to decompile GameMakerStudio2 games like Undertale and Pizza Tower
- Tour de Pizza for the base game
- And You for the support and playtesting!


## To Developers
For anyone that wants to spill time into this, Visit [Possible Fix Ideas.MD](https://github.com/burnedpopcorn/Pizza-Tower-1.1.0-Web-Port/blob/main/Possible%20Fix%20Ideas.md) within this repository to see my write-up on known issues listed above, and what I observed trying to troubleshoot this game. Not sure how well this will help since
I honestly have very little idea what I'm doing half the time
