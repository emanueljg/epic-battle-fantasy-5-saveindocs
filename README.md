# epic-battle-fantasy-5-saveindocs

Vanilla Epic Battle Fantasy 5 saves its state (save game, options, medals, logs) in the application directory. This is a mod that changes all data location to the user's document directory, under the subdirectory `ebf5`.

The documents directory is cross-platform. 
- Windows - `C:\Documents and Settings\Natalie\My Documents`
- MacOS - `/Users/Natalie/Documents`
- Linux - `/home/Natalie/Documents` (respects `xdg-user-dirs`)

# Installation

Download the modified [wrapper.swf](https://github.com/emanueljg/epic-battle-fantasy-5-saveindocs/blob/master/wrapper.swf) in this repo, put it in your game directory (replace the old `wrapper.swf`), and you're done.

To make sure everything works, run the game and get to the main menu (past the slime screen). Check your Documents directory. A new directory `ebf5` should've appeared with at least an `options.meow` file. Feel free to copy over 
old saves and config (BUT MAKE SURE TO MAKE BACKUPS!).

# Uninstallation

Copy back the original `wrapper.swf` from the repo ([wrapper-original.swf](https://github.com/emanueljg/epic-battle-fantasy-5-saveindocs/blob/master/wrapper-original.swf)).

# How?

I used the excellent [JPEXS decompiler](https://github.com/jindrapetrik/jpexs-decompiler), and hand-wrote the raw compiler P-code to substitute [flash.filesystem.applicationDirectory](https://airsdk.dev/reference/actionscript/3.0/flash/filesystem/File.html#applicationDirectory) calls with [flash.filesystem.documentsDirectory](https://airsdk.dev/reference/actionscript/3.0/flash/filesystem/File.html#documentsDirectory) calls. I'm sure it would've been possible to just edit the ActionScript normally, but I didn't feel like setting up the libraries in order to properly compile it :>)

# Why?
I wanted to package EBF5 for [Nix](https://nixos.org/) with the game running in the read-only Nix store.

# License
MIT 
