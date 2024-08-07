# Pizza Tower 1.1.0 Web Port

A Port of Pizza Tower 1.1.0 (The Noise Update) to the Web Browser

https://pt-emscriptenport.x10.mx/runner.html

Minimalistic verison here: https://pt-emscriptenport.x10.mx/barerunner.html

GX.GAMES Upload! https://gx.games/games/9s7us4/pizza-tower-1-1-0-web-port/
> Just a Launcher to normal website

itch.io Upload: https://burnedpopcorn.itch.io/pizza-tower-110-web-port

### Other Ports I've made:
- Cheesed Up Web Port
- Scoutdigo v1.2 Web Port
- Sugary Spire Web Port (Based Off Playtest 3.2 Source Code)

Look for them in my Repos!

## HOW TO CLEAR CACHE
> This is needed everytime I update the main website, else the game crashes


First Step: Go to the website, then press the lever/lock button in the left-side of the URL bar, then press ```Cookies and Data```
-> ```Manage on-device site data``` -> then delete cache by pressing the trash can icon that is next to the website URL

Last Step: Go to ```chrome://settings```, search for ```"cache"``` in the search bar, and click ```"Clear browsing data"```.
Enter and ONLY SELECT ```"Cached Images and files"``` (anything else is unnecessary)

Enjoy the New Update!

> [!IMPORTANT]
> Unfortunately, this deletes your save files, but at least you have Level Select and Commands

## Current state of the Project

Unfornately there are still some bugs that can negatively impact the game such as
- No sound
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
> Use the 2022 LTS Gamemaker runtime (Runtime 2022.0.1.30), as anything older or anything newer will eventually cause problems while compiling

- Use GX.GAMES and VM options to compile it, and to obtain the compiled files from GameMaker Studio for free, just go to ```C:/Users/(your username)/AppData/Local/GameMakerStudio2-LTS/GMS2TEMP``` while locally running the game
- In which you will find a folder called ```PizzaTower_GMS_(some numbers)_VM``` after you compiled the project
> The only really important files are in the ```/runner/``` folder

The said files will NOT run locally as file:// will just result in CORS errors and will not allow runner.html (the main file that runs Pizza Tower) to read the game files

> [!NOTE]
> The YYC Compiler Option does work, but you need Emscripten installed, and nothing is lost nor gained, so I recommend VM, as you don't need to waste time installing Emscripten and there are no upsides anyways

The only way for them to work is if you have a web server running this, or a local server using something like python
- Which you can do by entering the directory containing ```runner.html``` and other files and typing the command ```python3 -m http.server``` in the linux terminal or ```py -m http.server``` for windows powershell given you installed python
- At which point you can enter ```http://localhost:8000/runner.html``` to play the game locally

I also recommend using my custom version of ```runner.html```, or even my minimalized version of it called ```barerunner.html```, as they are just generally better than the stock output

## To Self-Host it
- Download and Extract the Latest Build from the Releases Tab (not the Source Code zip)
- Decide which website provider you will be using

> [!NOTE]
  > Your provider of choice has to provide at least 300mb of storage space
  > 
  > It is recommended to choose a provider that can provide Unlimited Bandwidth, as the website will transfer 300mb per visitor, so Bandwidth Use will probably skyrocket into the Terabytes

> For absolutely free hosting, I strongly recommend x10hosting, as they satisfy these requirements for free
- Go to your website's file manager, and go to the root of your website's domain (or wherever the public files go in your file manager)
- Upload all the files there (do not include any folders, just the assets such as runner.html)
- Check your self-hosted build at ```http:// (YOURDOMAIN.HERE) /runner.html``` or ```http:// (YOURDOMAIN.HERE) / barerunner.html``` if you included that file
> [!NOTE]
> If your website does not load the files, try waiting some time, and if it still doesn't work, check your provider's community forums for information regarding uploading files

## Thanks to
- loypoll for the full decompilation of the recent Pizza Tower Update
- krzys_h and UnderminersTeam for the UnderTaleMod and the ability to decompile GameMakerStudio2 games like Undertale and Pizza Tower
- Tour de Pizza for the base game
- And You for the support and playtesting!

## To certain users
This project was primarily made to play Pizza Tower on locked-down school chromebooks for lazy ass students. Please do not use this project to avoid paying for the PC version of the game. By doing this you not only harming the creator of Pizza Tower, but also harming your experience with this amazing game with a version filled with bugs, crashes, and lost functionality

But I know you probably won't care, so please at least support the creator in some way or at least plan to in the future (I definitely will)

## To Developers
For anyone that wants to spill time into this, Visit [Possible Fix Ideas.MD](https://github.com/burnedpopcorn/Pizza-Tower-1.1.0-Web-Port/blob/main/Possible%20Fix%20Ideas.md) within this repository to see my write-up on known issues listed above, and what I observed trying to troubleshoot this game. Not sure how well this will help since
I honestly have very little idea what I'm doing half the time
