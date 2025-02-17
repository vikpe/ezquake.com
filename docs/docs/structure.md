---
---

# Files and directory structure

(automatic conversion from internal help - last edited Sat 16-Oct-2004)

## Quake and QW directory structure

By default Quake is installed into x:\quake\ (where x is the letter of the harddrive). This directory contains the executable called ezquake.exe as well as
several other files, dll's and others. In the subdirectory called ..\id1\ the "pak" files are stored. These hold all the games' data like graphics, sounds,
models and maps. These so called pak-files are used both by NetQuake as well as QW.

After installing QW the x:\quake\ directory will also hold the two QW executables (ezquake.exe for software quake and ezquake-gl.exe for OpenGL QW), new DLL
files as well as a subdirectory called ../qw/ wherein there are various other subdirectories. Later when you downloaded maps form a server or when you have been
to a server running a mod others might be created like ../maps/, ../sound/ or ../cfg/. Furthermore the first time you run ezquake-gl.exe the models will be
meshed and stored in the ../qw/glquake/ directory. So the whole structure could look something like this:

```

C:\Quake\ \id1\ \ezquake\ \cfg \docs \fuhquake \help \commands \manual \demos \variables \xsd \xsl \sb \qw\ \demos\ \glquake\ \maps\ \lits\ \locs\ \skins\ \sound\ \textures\
```

## Quake and QW files

The only files absolutely required by QW from the original Quake are the two pak files in \id1\ called "pak0.pak" and "pak0.pak". In case you are using a Voodoo
graphics board you also need "opengl32.dll" in the main directory. Everything else QW needs (the base.pcx and config.cfg) are created on start if they do not
exist already. Thus you could get rid of everything else but the following to play QW:

```

ezquake.exe ezquake-gl.exe libexpat.dll libjpeg.dll libpng.dll zlib.dll opengl32.dll * \id1\pak0.pak \id1\pak1.pak \ezquake\pak0.pak
```

## QW config files

QW's default config file called "config.cfg" which can be found in the ..\qw\ directory (don't mix it up with the file of the same name in the ..\id1\ dir, it
belongs to NetQuake). This file contains all the default keybinds as well as video, mouse, etc. settings. In theory you could modify it to your own needs as
much as you want but it has a mayor drawback. As soon as you quit QW it always overwrites config.cfg with the actual configuration of that session. So if you
were testing some settings and you forget to reenter the previous ones you may end up getting bad settings at the next start of QW. What is also annoying is
that the order of the different commands is always scrambled when it is rewritten so that the file always looks chaotic.

A better way to store your personal .cfg is to create a file called "autoexec.cfg" in the ..\qw\ directory. This file will always be executed automatically when
starting QW. You can either put all commands in there or you can make it execute another custom cfg file. This is especially useful when you have more than one
cfg like one for your general settings, one for your teammessages or even different configs for different maps. To make autoexec.cfg execute your custom cfg
files use the "exec" command.

Example: "exec team.cfg". A config can be executed not only at start but at any time and will always override previous settings (note that some, especially
video commands only take effect when a new map is loaded or even when QW is restarted). The only thing you have to make sure is that your config files are in
the ..\qw\ directory (or one of its subdirectories).
