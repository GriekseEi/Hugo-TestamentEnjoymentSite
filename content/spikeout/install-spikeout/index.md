+++
date = '2025-03-08T08:46:24+01:00'
draft = false
title = "How To Setup SpikeOut"
summary = 'Click here to learn how to install SpikeOut!'
tags = ['spikeout', 'guide']
blueskyPostUri = 'at://did:plc:b7wncmt7q7rqwzu5enl5gsya/app.bsky.feed.post/3l7aqo3bysx2t'
listEntryImage = './catalog-cover.webp'
showToc = true
showWordCount = false
weight = 1
+++

## Intro

For the longest time, playing *SpikeOut* on home systems was near impossible. Outside of *SpikeOut: Battle Street* for the original Xbox, it never received an official home release. SpikeOut had the rather bad luck of only being released on the Sega Model 3 arcade hardware and the original Xbox, both of which were notoriously hard-to-emulate systems.

Although we have yet to see an official release of *SpikeOut* on modern platforms, emulation for both the Model 3 and Xbox has improved significantly in the past few years to the point where you can play any edition of SpikeOut with no major issues. Sega Model 3 games can be emulated using the [Supermodel emulator](https://www.supermodel3.com/), and Xbox games using the [Xemu](https://xemu.app/) emulator. To play SpikeOut you can use one of the following methods, ordered in terms of which I recommend the most:

1. [My PowerShell installer script](#1-recommended-my-powershell-installer-script)
2. [Setting up the Sega Model 3 emulator yourself with a GUI](#2-setting-up-the-sega-model-3-supermodel-emulator-yourself-with-gui-and-launchbox-presets)
3. [SpikeOut: Battle Street with Xbox emulation](#3-spikeout-battle-street-with-xbox-emulation)
4. [SpikeOut through Like a Dragon: Infinite Wealth](#4-spikeout-through-like-a-dragon-infinite-wealth)
5. [Playing SpikeOut on an actual arcade PCB](#5-playing-spikeout-on-an-actual-arcade-pcb)

## Ways to play SpikeOut

### 1. (Recommended!) My PowerShell installer script

![The gamepad control preset for SpikeOut when using my PowerShell installer script](spikeout-controller-setup.webp?fit=50x50#center "The gamepad control preset for SpikeOut when using my PowerShell installer script")

To make setting up SpikeOut and the Supermodel emulator less of a hassle, I've [published a PowerShell setup script](https://github.com/GriekseEi/GriekseEi-RandomPowerShellScripts) that helps set everything up with some sane defaults and integrates the SpikeOut launcher shortcuts into your Steam library, but optionally also allows for non-Steam desktop shortcuts.

However, I *highly recommend* that you go for the Steam option, because this allows the script to set up a controller preset using Steam Input, which adds some extra macros that aren't possible with the non-Steam option (such as binding Supermodel savestate controls to a radial menu on the right analog stick), but also makes it much easier to rebind the controls to your liking.

> The way that the Steam Input setup works it that the Supermodel control config is set up with only keyboard inputs, and Steam Input does all the work of identifying your gamepad and making sure your buttons are bound to the keyboard keys, no matter your controller type. *This also means that if you start rebinding the keyboard inputs in Supermodel, the Steam Input binds may no longer work.*

&nbsp;

#### How to install

To run the script, open a PowerShell window (administrator privileges are not required) and run the following two commands. It will grab the script from my GitHub and immediately run it. The script is compatible with Windows PowerShell 5.0+, which is installed by default on any modern Windows installation.

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Method Get 'https://raw.githubusercontent.com/GriekseEi/GriekseEi-RandomPowerShellScripts/refs/heads/main/Setup-SpikeOut/Setup-SpikeOut.ps1' | Invoke-Expression
```

The script starts a setup which will download the latest version of the Supermodel emulator, prompt you with some questions about what settings you want to emulate SpikeOut with, and then set up Steam shortcuts for both SpikeOut versions in your Steam library, or your desktop if you chose the non-Steam option.

*However, for legal reasons this installer script does **NOT** include the SpikeOut ROMs.* You will have to find these (*spikeout.zip* for Digital Battle Online and *spikeofe.zip* for Final Edition) yourself. If you got the SpikeOut ROMs by way of a MAME ROM set megapack, make sure they are NON-MERGED romsets. Merged romsets will NOT work.

> If you end up breaking your Supermodel installation somehow (or you just want the newest Supermodel version), you can simply run the script again and it will reinstall everything from scratch.

&nbsp;

**Pros**:

- Easy to run, and comes with a setup asking you what settings you want to use.
- Sets up both arcade versions of SpikeOut.
- Can add SpikeOut launcher shortcuts to your Steam Library for ease of use, but a non-Steam option is also available.
- The Steam option sets up a controller preset using Steam Input, which will recognize pretty much any controller type, allows for a bunch of useful macros, and makes it easier to rebind the controls yourself inside the Steam Controller Configurator.
- Comes with control presets for both gamepads and fightsticks/arcade sticks.
- Can be played with online co-op using Parsec.
- Uses the Launchbox presets for better-adjusted audio volume/balance presets (see option below for more info).

**Cons**:

- Only works on Windows. I may port the script over to Nushell in the future for cross-platform support.
- Gamepad keybindings using non-Steam shortcuts are not guaranteed to work for every gamepad.
- For legal reasons, you'll have to find the SpikeOut ROMs yourself.
- You shouldn't be running random PowerShell scripts off the internet in general. You're going to have trust that this remotely executed PowerShell script won't do anything malicious.

If you find any issues with my PowerShell script, please contact me [on my socials](/about/#find-me-on-these-websites).

&nbsp;

### 2. Setting up the Sega Model 3 Supermodel emulator yourself (with GUI and Launchbox presets)

![A screenshot of the Sega Model 3 UI program](supermodel-gui.webp#center "Sega Model 3 UI")

It is also possible to set up the Supermodel emulator yourself. The only problem is that at the time of writing, Supermodel is still a terminal application with no GUI. Unless you have no problem with this, another solution is to use one of the unofficial GUI wrappers for it, such as [Sega Model 3 UI](https://github.com/BackPonBeauty/Sega-Model-3-UI-for-20240128-/releases/tag/Supermodel3UIver20250221). Simply unzip the Sega Model 3 files in your Supermodel folder, and you're good to go. 

I would also recommend that you apply the Launchbox configuration presets to Supermodel. [The LaunchBox thread](https://forums.launchbox-app.com/files/file/3857-sega-model-3-supermodel-git-everything-pre-configured-inc-controls-for-pc-controller-mouse-light-guns-test-menus-configured-free-play-all-games-in-english-2-player-mouse-support-audio-adjusted-layout-imagesthe-whole-9-yards?_fromLogin=1) contains all the info you need to set it up yourself. If you prefer, there is also a [YouTube guide by the author of these updated configs](https://www.youtube.com/watch?v=htNM8kbpEFk&t=0s) to help you walk through the installation step-by-step. As with my PowerShell script, you have to find the SpikeOut ROMs yourself.

**Pros**:

- You can more easily adjust any Supermodel settings via the Sega Model 3 UI.
- If you intend to to play other Model 3 games besides SpikeOut (such as Daytona 2 and Sega Rally 2), you're better off using this option instead of my installer script.
- Can be played with online co-op using Parsec.
- The Launchbox pack comes with manually adjusted audio volume and balance levels for all Model 3 games, instead of the default everything being set to 100%.

**Cons**:

- The GUI only works in Windows.
- Does not come with config presets for SpikeOut (the Launchbox control presets for SpikeOut are functional but not 100% optimal).
- Can't rebind controls via the GUI. Any control rebinding has to be done via Supermodel's unwieldy terminal tool.
- For legal reasons, you'll have to find the SpikeOut ROMs yourself.

&nbsp;

### 3. SpikeOut: Battle Street with Xbox emulation

![SpikeOut: Battle Street](spikeout-bs.webp#center "SpikeOut: Battle Street")

While *Battle Street* is narratively a sequel, in terms of gameplay it might as well be a remaster of *Final Edition*. Nearly all the levels and encounters are exactly the same as *Final Edition*, just with completely remade visuals, music and sound effects. Enemy behavior and gameplay systems haven't significantly changed much either, although there are a few balance changes that make me prefer *Final Edition* over it. However, you do get 4 new additional playable characters, every boss enemy as an unlockable playable character, and a training room.

Short of playing it with a physical copy on the original hardware, the only way to play this on PC is using the [Xemu](https://xemu.app/) emulator. Keep in mind you do need decently powerful hardware for Xbox emulation. Another important thing to know is that any Xbox ISOs you find have to be converted to a XISO format for Xemu for it to be able to read it. Read [this page](https://xemu.app/docs/disc-images/#xdvdfs-web-or-command-line) to learn how to do it.

**Pros**:

- Easiest way to play SpikeOut... *if* you have a physical copy and an original Xbox.
- Supports online co-op through the original hardware or the Xemu emulator.
- Has the most content out of all SpikeOut versions.
- It comes with an actual training/practice room that you can practice combos in or learn how to deal against certain enemies.
- Comes with macros for multi-button moves (such as super attacks, homing attacks and sweeps) out of the box!
- Has a Story Mode if you're into that sort of thing.
- New soundtrack by SuperSweep masters [Shinji Hosoe](https://vgmdb.net/artist/247) and [Ayako Saso](https://vgmdb.net/artist/298) ([it's really good, I'd say even better than the original soundtracks!](https://www.youtube.com/watch?v=bKQ1esP4n50&list=PLP8_sGncyT5R_5EvmwFytXhfRegLg2OxB)).

**Cons**:

- Xbox emulation still requires a mid-to-high end PC to run games at a stable framerate.
- Physical copies of Battle Street these days are [rather expensive](https://www.ebay.com/sch/i.html?_nkw=spikeout&_sacat=0&_from=R40&_trksid=p2332490.m570.l1313).
- At the time of writing, the pre-rendered cutscenes for Battle Street in Xemu are still riddled with a lot of visual artifacts.
- The new visuals just look drab compared to the arcade versions.
- Some minor questionable balance changes (super throw -> C4 combos dealing even absurdly more damage???).

&nbsp;

### 4. SpikeOut through Like a Dragon: Infinite Wealth

![The *SpikeOut: Final Edition* cabs in *Like a Dragon: Infinite Wealth*](spikeout-lad.webp#center?height=200&quality=60 "The SpikeOut: Final Edition cabs in Like a Dragon: Infinite Wealth")

It is also possible to play *SpikeOut: Final Edition* as a minigame in *Like a Dragon: Infinite Wealth* (amongst other Model 3 games). This uses SEGA's own internal emulator, and appears to be relatively accurate (albeit with some very minor changes, such as the red cross on medkits being changed to a green cross to avoid legal issues). This is also the only legal way you can play SpikeOut at the time of writing.

This is the technically easiest way to play SpikeOut, but it also lacks several options, such as the ability to play the original *Digital Battle Online* version and to play on higher difficulties. Emulator niceties such as savestates and display hacks aren't available either. In terms of user experience it is also rather cumbersome to have to boot up SpikeOut as a minigame inside another game.

**Pros**:

- Supports splitscreen offline multiplayer!
- On PS5 only, technically supports online multiplayer through the Share Play feature (but this only allows one extra player to join, and Share Play sessions can only last for a maximum of an hour).
- It's legal!
- No technical knowhow required or any risk of fiddling with programs!
- The only way to play SpikeOut on PS4/PS5/Xbox One/Xbox Series X.

**Cons**:

- Only *Final Edition* is available. The original *Digital Battle Online* version is **NOT** available.
- The only available difficulty settings are Easy and Normal. It is not possible to play on Hard or Hardest.
- You have to have a copy of *Like a Dragon: Infinite Wealth*, and your computer has to be able to run it.
- Savestates are not available.
- Requires playing through *Like a Dragon: Infinite Wealth* a bit before you're able to unlock the SpikeOut minigame (est. 30 minutes).

&nbsp;

### 5. Playing SpikeOut on an actual arcade PCB

![A picture of a SpikeOut PCB](spikeout-pcb.webp#center "A Sega Model 3 Step 2.1 Board with SpikeOut: Digital Battle Online on it")

Yes, playing it on the actual arcade board. If you're lucky enough to be near an arcade hall or see a SpikeOut PCB for sale, you *could* play it that way.
On the other hand, chances are the only arcade halls running SpikeOut cabs are a few places in Japan (to my knowledge, in Kyoto and Osaka), and SpikeOut PCBs are very rarely for sale, and at enormous prices at that. But if you are that lucky, you do end up with the most accurate way to play SpikeOut.

**Pros**:

- The experience is as accurate as you can get!

**Cons**:

- **EXPENSIVE**.
- Only way to play this co-op is if you or a nearby arcade hall has multiple SpikeOut cabs.
- Even if you can afford it, you'll have an even harder time finding a PCB for sale, let alone one for Final Edition.
- 99.9% chance you're nowhere near an arcade hall hosting a SpikeOut cab.
- I hope you know or know someone else who knows how to set up a Model 3 Step 2.1 PCB and/or repair it if needed.
