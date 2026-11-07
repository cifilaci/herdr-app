# Herdr 98

A Windows 98 layout for Herdr: `layouts/win98.json` + `themes/win98.json` +
this mod. One mod, many roles (`main.js`): taskbar, desktop, window (pane
title bars), menu (Start menu too), dialog, mines, sol, clippy. `kit.js`
draws the Win98 bits (bevels, buttons, title bars) in whole device pixels at
any zoom; Display Properties > Settings switches Small/Large Fonts (1x/2x).

The bundled fonts load with this mod; no system installation is needed.
Pixelated MS Sans Serif (from 98.css) for the UI, PxPlus IBM
VGA 8x16 (int10h.org, CC BY-SA 4.0) for terminals.

Keys (`keys.json`, section `layout:win98`): Ctrl+Esc opens the Start menu
(`win98.start`), Ctrl+Shift+Esc the Task Manager (`win98.taskman`), F1 the
welcome screen (`win98.welcome`), F3 Run (`win98.run`), F4 Display
Properties (`win98.display`), F5 Shut Down (`win98.shutdown`), F6 Log Off
(`win98.logoff`), F7 the date and time (`win98.datetime`), F8 Mines
(`win98.mines`), F9 Solitaire (`win98.sol`), F10 My Computer
(`win98.mycomputer`), F11 the small fonts (`win98.small_fonts`) and F12 the
large ones (`win98.large_fonts`). The other commands (new tab, new space,
rename, close) keep the app's global chords; the Start menu and the
taskbar's tab and space menus still reach them.

The taskbar carries a virtual-desktop switcher: the button beside Start and
the icon in the notification area both open the same list, above the control
that opened it. One workspace is one virtual desktop: the list is your
workspaces, each with its agents' status (blocked, working, done), and one
click switches to it.

`art/` holds the icon, image and sound generators. Run with Bun and an
optional output root (default: `/var/tmp/herdr98`):

```sh
bun defaults/mods/win98/art/generate.ts /var/tmp/herdr98
bun defaults/mods/win98/art/sheet.ts /var/tmp/herdr98
bun defaults/mods/win98/art/sounds.ts /var/tmp/herdr98
```

Images and the contact sheet need ImageMagick (`magick`); sounds need
FFmpeg (`ffmpeg`). Fonts are read from this mod's `fonts/` directory.
Generated mod assets go under `<root>/mods/win98/`; intermediate art and
the contact sheet go under `<root>/art/`.
