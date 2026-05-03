<img src="https://raw.githubusercontent.com/clover-moe/lilium-arena/master/misc/lilium.png" width="64">

**Lilium Arena** is an engine and game-logic compatible with Quake III Arena 1.32.

The goal is to maintain the original Quake 3 gameplay, visuals, and audio experience while also providing a reliable code base for derivative projects and continued support for Windows XP+, macOS 10.5+, and GNU/Linux.


## Features

### ZTM's Flexible Display

Lilium Arena defaults to displaying the game as 4:3 letterbox with console/notify text at the same relative size as 640x480 resolution for an authentic Quake 3 experience on modern displays in high resolution.

Lilium Arena includes ZTM's Flexible Display; the successor to _ZTM's Flexible HUD mod for ioq3_. Flexible Display offers aspect correct widescreen but with various new enhancements, including support for mods and joining pure servers.

There are six widescreen presentation modes (controlled by `cl_flexibleDisplay` cvar):

1. Original 4:3 view/HUD (default).
2. Expanded view with 4:3 centered HUD.
3. Expanded view/HUD (not compatible with all mods, still under development).
4. Expanded view with stretched HUD.
5. Original stretched view/HUD.
6. Original widescreen view/HUD.

Expanded view respects `dmflags 16` (fixed fov) set by a server and switches to stretched view. There are `flexup` and `flexdown` commands that can be bound to conveniently switch modes while playing. You can optionally replace the original view `sizedown` / `sizeup` keys using `bind - flexdown; bind = flexup; bind + flexup;`.

Flexible Display is compatible with mods based on the original Q3 SDK and ioquake3 by running the mod logic at a fake 640x480 resolution and applying widescreen adjustments in the engine to match the window's resolution. `cl_flexibleDisplay 0` disables Flexible Display to access the mod's original resolution dependent behavior. Flexible Display can also be disabled at compile time if one wants to create a derivative project without this feature.

Additional enhancements in Flexible Display:

- Fixed player model being stretched in setup menu in widescreen when using the original pk3 files / ui.qvm.
- Fixed notify message position for Team Arena voice head in top-left in widescreen when using the original Team Arena pk3 files / cgame.qvm.
- Support for absolute mouse movement in the menu to make mouse movement sensitivity match desktop movement and move to the location touched on a touch screen. (Various iOS and Android ports have shipped a custom ui.qvm to add this, lacking support in mods.)
- Support for the mouse cursor leaving the window while in the menu.
- Support for resizing the window without reloading the game content (opengl1 renderer only).
- The console background and loading level image are aspect correct in "expanded view/HUD" mode; great for mods that add a logo to the console or level images.

General enhancements (usable independent of Flexible Display):

- Console text defaults to scaling to match 640x480 size; this can be overridden using `con_native 1; con_scale 2` to draw at native font resolution like the original Quake 3 with a custom scale factor to make it readable in 4K.
- The game window defaults to resizable.

All the changes for Flexible Display can be disabled by opening the console using Shift+Escape and pasting the following using Ctrl+V and pressing enter:

```
cl_flexibleDisplay 0; con_native 1; r_allowResize 0; vid_restart;
```

and re-enabled using:

```
cl_flexibleDisplay 1; con_native 0; r_allowResize 1; vid_restart;
```


## About

Lilium Arena is the base project for various Quake 3 projects maintained under Clover.moe, such as Spearmint. It is based on the Quake 3 GPL source code by id Software that was further developed in ioquake3.

zturtleman began developing a project on ioquake3 in 2008 and contributed to ioquake3 from 2010 to 2025. Lilium Arena is a continuation of his vision for a Quake 3 1.32 engine. Changes from ioquake3 may be selectively integrated.

Lilium Arena was established in 2021 with the intention of providing releases of a lightly modified ioquake3 to better match zturtleman's vision and to be the base for Lilium Arena Classic. In October 2025, zturtleman moved his primary development for Quake 3 1.32 to Lilium Arena and made it the base for all Quake 3 projects under Clover.moe. A vision for a series of engines under the title "Lilium" began in 2014 with Lilium Voyager.


## License

Lilium Arena is licensed under [the GNU GPLv2](COPYING.txt) (or at your option, any later version). The Quake 3 data files are not under a free license and must be purchased in order to play Quake 3.


## Resources

  * [Website](https://clover.moe/lilium-arena)
  * [Discussion / Technical support](https://clover.moe/open-source)


## Compiling

Lilium Arena is compiled using GNU Make (`make`) and requires a C compiler. Most dependencies are included in the repository. Compiling for Linux requires installing SDL 2 library and headers.


## Contributing

High quality code contributions are more helpful than rushed contributions. LLM ("AI") contributions are not desired.

Reviewing pull requests is sometimes more work than a reviewer doing the work in the first place so pull requests may be disregarded.


## Credits

Lilium Arena is maintained by Clover.moe at https://github.com/clover-moe/lilium-arena.

### id Software

  * John Carmack
  * Robert A. Duffy
  * Jim Dose'
  * Jan Paul van Waveren

### ioquake3 contributors

  * Tim Angus
  * James Canete
  * Vincent Cojot
  * Ryan C. Gordon
  * Aaron Gyes
  * Zack Middleton
  * Ludwig Nussel
  * Julian Priestley
  * Scirocco Six
  * Thilo Schulz
  * Jack Slater
  * Tony J. White
  * ...and many, many others!

### Clover.moe

  * Zack Middleton (zturtleman)


## Derivatives

If you create a derivative project that you plan for others to use, it would be preferred to give it a different title such as "Lilium Arena (_your name_ ver.)" to make it easier to discuss and reduce confusion with the project maintained by Clover.moe.

If you're going to pick a different title, it would be preferred that you pick a different song title to build on rather than use the word Lilium. (Lilium is the title of the opening song of the 2004 anime series Elfen Lied.)


