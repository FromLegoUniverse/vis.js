NOTE: This was modified for personal use, however can be used for getting data of audio files.

Viewing:
<br>(Development) https://rawgit.com/Drybones3363/vis.js/gh-pages/index.html
<br>(Production) https://cdn.rawgit.com/Drybones3363/vis.js/gh-pages/index.html

# vis.js (FromLegoUniverse/TheNexusAvenger's Modifications)

vis.js is a modifcation of the [version owned by caseof](https://github.com/FromLegoUniverse/vis.js) for the use of getting sound data for use on ROBLOX. This is a more speicalized version, and you should refer to the original if you are looking at this one.

## Re-using for yourself

If you want to reproduce these files, do the following:
<br>1. Create a fork of this repositionary
<br>2. Go into /index.html, replace both cases of FromLegoUniverse (lines 21 and 32) with your GitHub username
<br>3. Go into /js/util/config.js and replace FromLegoUniverse (line 8) with your GitHub username
<br>4. Go into /README.MD and replace both case of FromLegoUniverse in the links(lines 4 and 5) with your GitHub username
<br>5. Keep the reference to the original under caseif. I just modified this, I didn't create it.

Note: This is meant to work with rawgit.com. You may need to modify teh links further in steps 2-4 to work with your domain or changed repositionary name.

## Song Data Exporting
The output of this modification is a ModuleScript in a .rbxmx file, which returns a table with each frame sample and an ordered set of the positions of the bars (in practice, the max they reach is ~240-250). This is meant to be directly inserted into Roblox Studio. If you need to change this to another format, the file is created in /js/audio.loader.js, /js/audio/node_helper.js, and /js/visual.js.

(Following was not modified as it is still relevant)
## Browser Support

:heavy_check_mark: Google Chrome

:heavy_check_mark: Microsoft Edge (minor issues but nothing huge)

:warning: Mozilla Firefox (works but sometimes freezes the browser)

:warning: Safari (Safari caps `fftSize` at 2048, resulting in odd/glitchy spectrum behavior)

:x: Microsoft Internet Explorer (no support for the AudioNode API)

## Common Issues

First and foremost, verify that you're using a supported browser as per the above section.

**Spectrum is jittery/choppy**

If the spectrum is jittery even though the framerate isn't dropping, you may need to reconfigure your system's audio settings. vis.js functions best at a sample rate of 44.1kHz. Higher rates may affect the visual quality of the spectrum.

**"Could not get audio context! (Are you using IE?)"**

The audio node could not be initialized because it is not supported by your browser. This is seen most commonly in Internet Explorer, which does not support the Audio API.

**"Could not set optimal fftSize! This may look a bit weird..."**

The audio node was not initialized properly. This might be resolved by using a different browser, although it may be a restriction caused by your system.

**404 in console on local install when loading audio**

vis.js needs a reverse proxy to be configured on the webserver in order to function due to Javascript restrictions. More specifically, `vis.mydomain.com/content/` should point to `docs.google.com`.

## Footnote

See the visualizer in action [here](http://vis.caseif.net/).

Based on [schisma/vis](https://github.com/schisma/vis).
