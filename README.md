# mpv-osc-framework

Oscf is an “osc framework” to help building your custom osc for mpv player.

--- 

### This repo diverges from UPSTREAM 

This repository is meant to hold a copy of local changes for testing, not for upstream pull requests, as our code will differ. 

## Objective

I will build from this, to create an OSC tailored for Windows 10/11. To create a MPV player that will look and feel like a native UWP (WinUI3) application.

:warning: Any and all code published will be 'proof of concept' and NOT meant to be used yet.

## Proposals

**Multi-Platform Support**
<br>
To make the script compatible for use on other platforms.
To do this, a fallback mechanism for parameters, such as 'font' will need to be in place, and platform OS detection function, to determine when the fallback values are to be used.

Note, that we can't rely on users to simply set an 'osc.conf' option. It must be done by the script.

Reason: 
`Segoe UI` and `Segoe Fluent Icons` are Windows system fonts, and can NOT be distributed and installed onto non-Windows machines. We would need to thus define a set of open source alternatives, and way to switch to them based on what platform OS the script is being run from, or more specifically the `mpv` program.

**Constrained Fixed Player Controls with Adaptable Menu**
<br>
Buttons or items in the OSC do not adapt to resizing and scaling like on Windows. The goal is to produce an OSC that functions like a Windows UWP (WinUI3) application. Effectively a minimal looking media player [like this](https://learn.microsoft.com/en-gb/windows/apps/design/controls/media-playback).

Proposal:
<br>
Make items adapt to layout changes by adding an ['Overflow'](https://learn.microsoft.com/en-gb/windows/apps/design/controls/custom-transport-controls#working-with-the-overflow-menu) state. Then as in the examples [shown here](https://www.fluentui-blazor.net/Overflow), instead of showing `[+N]` a menu button will appear (Segoe Fluent Icons: More) and all non critical items will be moved inside it. The affect will mean, when the window is resized beyond the `last item` in the row, some buttons will be moved to a menu [(refer to example)](https://raw.githubusercontent.com/Neuro-NX/mpv-osc-framework/main/github/images/proposal-player-controls-menu.png), rather than hide, so functionality is not hindered.

## Contribute

1. Fork this repo
2. create a new branch with your changes
3. Submit a pull request with commit message containing explanation
