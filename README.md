# sonolus-psekai-engine
A recreation of Project Sekai engine in Sonolus

## Instructions
The following instructions will teach you how to get your PSekai levels running on your game. But before everything, make sure you have your own private server to test on. [Guide on how to set up local Sonolus server (for Windows)](https://docs.google.com/document/d/11rMD_wd-oXA6Qtvpk3gn_StZMO-XTMBWA_EVI-ksfXs/edit?usp=sharing)

### 1. Get a .sus file
Project Sekai uses .sus files as charts.
* If you wish to play official charts, ask people who already have access to the assets as you may not be able to find them publicly on the Internet.
* Alternatively, you can create your own chart using [Ched](https://github.com/paralleltree/Ched/releases/tag/v2.6.3.0), a chart editor for Chunithm format games.
  * Project Sekai uses 12 lanes and Chunithm uses 16 lanes, so make sure you don't use the 2 leftmost and rightmost lanes when you are charting in Ched, or they will look out of place.
  * Since there is no curve-support for the engine yet, it is reccomended to use higher Division to make curves (64-note Division/ 128-note Division). 
  * Fun fact, it's in [Be-Music Source](https://en.wikipedia.org/wiki/Be-Music_Source) format.
  
### (SHORTCUT) Convert the chart
Now you have a .sus file, you can use .sus-to-Sonolus Converter to convert .sus into Sonolus compatable chart file!
* Go to [.sus-to-Sonolus Converter](https://miku-yay.netlify.app/)
* Copy and Paste your .sus in the Input section
* Save the top section of Output as `level.json`
* Save the bottom section of Output as `options.json`
#### You can now skip to Step 4

### 2. Get the chart for your engine
Now you have a .sus file, you can use sus2entities to convert .sus into Sonolus compatable chart file!
* Download [sus2entities](https://github.com/LeptailurusServal/sus2entities/releases)
* Prepare a folder to store your output file. 
  * Make sure there is no space between characters and prevent using symbols
* Launch sus2entities.exe
* When prompted
  * `Where is your .sus file?`: Enter the location of your .sus .
  * `Where is the destination of your file?`: Enter the location of where your file would be, as well as its name.
  * For example:
```
Where is your .sus file?
...\psekaiengine\mychart.sus
Where is the destination of your file?
...\psekaiengine\mychart.json
```

### 3. Create the level
Now you have a chart, it's time to make a Sonolus level!
* Get the files in the \engine folder
* Go to [Sonolus Intermediate Language Compiler](https://sonolus.com/developer/compiler/)
  * Put `SIL.txt` in the Script (SIL) section
  * Put `script.json` in the Level (JSON) section
  * Put your chart in the Entities (JSON) section
  * Hit the [Compile] button when you are done
  * Save the texts in the Output (JSON) section as `level.json`
  
### 4. Add the level to your server
Now you have the level, it's just a few steps from being able to play it!
* Move the `options.json` from the engine, as well as the `level.json` you got from the previous step, into `...\yourserver\levels\yourlevel\`
* Add your level in `list.json` in `...\yourserver\levels\`

#### Congratulations! now you can play the level in Sonolus.

## Work-in-process Features
### 1. Curvy Slides
Since this engine is modified from the Bandori engine, slides currently look like those in Bandori instead of those in Project Sekai. I am still figuring out how to do it.
### 2. Project Sekai Skin
It will be available when the assets of PSekai is publicly released.
