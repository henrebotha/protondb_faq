## Why my games crash on start or run very slow?

Be sure that your system is up-to-date and that you use the latest drivers available for your graphics card.

Note: 

These are stable drivers if you want to use newer beta/devel drivers do it on your own!

LLVM 7 or newer is requiered to fix the most graphic/rendering issues. If your distro still use LLVM 6 like Solus for example then tell them to update!

#### AMD

Arch/Manjaro/Antergos: 
```
sudo pacman -S vulkan-radeon lib32-vulkan-radeon lib32-mesa lib32-vulkan-icd-loader vulkan-tools
```

Ubuntu 18.04: 
```
sudo add-apt-repository ppa:paulo-miguel-dias/pkppa
sudo apt-get update`
sudo apt install mesa-vulkan-drivers mesa-vulkan-drivers:i386
```
Ubuntu 18.10

```
sudo apt install mesa-utils
sudo apt install libvulkan1 mesa-vulkan-drivers vulkan-utils
```

#### Nvidia

Arch/Manjaro/Antergos: 
```
sudo pacman -S lib32-nvidia-utils lib32-opencl lib32-nvidia nvidia nvidia-utils
```

Ubuntu 18.10:
```
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt install nvidia-396
```

Ubuntu 18.04:
```
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt install nvidia-driver-396
```

#### Intel

Arch/Manjaro/Antergos: 
```
sudo pacman -S lib32-vulkan-intel vulkan-intel lib32-mesa lib32-vulkan-icd-loader vulkan-tools
```

Ubuntu 18.10:
```
sudo apt install mesa-utils
sudo apt install libvulkan1 mesa-vulkan-drivers vulkan-utils
```

Ubuntu 18.04:
```
sudo add-apt-repository ppa:paulo-miguel-dias/pkppa
sudo apt-get update`
sudo apt install mesa-vulkan-drivers mesa-vulkan-drivers:i386
```

## My game crashes after a while but works fine without esync

Most issues with esync are related to the limited amount of opened files. Before reporting issues with esync, check if the command `ulimit -Hn` reports much more than 4096. If not, you can follow [these instructions](https://github.com/zfigura/wine/blob/esync/README.esync) to raise the limit.

## The game doesn't show any text

Some games need Windows fonts to be installed. Since Proton version 3.16-4 this will be done for you automatically. If you are using Proton 3.7, try if switching to version 3.16-4 or higher fixes your problem.

To change the Proton version, go to the Steam settings and there to the tab Steam Play. You need to activate the option "Use this tool instead of game-specific selections from Steam". Then you can chose the Proton version in the drop down menu.

## Some games like Witcher 3 have missing textures/enemies

This is fixed since DXVK Version 0.90 and Vulkan 1.1.88. Unfortunately at time of this writing, you need beta drivers for Nvidia (396.54.09) and AMD users need at least Mesa version 18.3.

## Some reports say they made the game running by installing some software, how do I do that?

There are two ways to install additional software

#### Use of Winetricks
Open a Terminal and use
```
WINEPREFIX=(Steam-folder)/steamapps/compatdata/(GAME-ID)/pfx/ winetricks
```
(GAME-ID) must be replaced with the game id for example 4000 for Garry´s Mod, you can use [SteamDB](https://steamdb.info) to find out what id your game have.

(Steam-folder) must be replaced with your .steam folder loaction.

Here is an example

```
WINEPREFIX=/home/alexander/.steam/steam/steamapps/compatdata/4000/pfx/ winetricks
```

#### Use of Tools

The two most popular currently are [Protontricks](https://github.com/Sirmentio/protontricks) and [ProtonFixes](https://github.com/simons-public/protonfixes).

Please read the instructions about those tools on their respective sites.

## How do I run Windows games I don't own on Steam?

To run games which are not on Steam, you can use [Lutris](https://lutris.net/) to run them with Wine. Lutris is a game manager which offers support for a lot of different compatibility layers/emulators, including Wine/Proton.

## Games stored on my Windows partition (NTFS) won't start

By default Linux mounts NFTS partitions only writable by Root. [WIP]
