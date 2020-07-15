# auto-ytdl WIP

[![WIP](https://img.shields.io/badge/WIP-v0.3.0-red.svg)]

I know, _yet another_ youtube-dl wrapper. But this one does something others don't: ability to automate your new music downloads, just like package managers automate your updates.

```
aytdl update
```

And that's it.
(Some initial setup is required of course, so auto-ytdl knows what music to download, but the most used commands are that simple)

# Table of Contents

- [Why does it exist? / Motivation / Rant](#why-does-it-exist--motivation--rant)
- [Doesn't it exist already?](#doesnt-it-exist-already)
- [How does it works?](#how-does-it-works)
- [Features](#features)
- [Dependencies](#dependencies)
- [Install](#install)
- [Usage](#usage)
- [Examples](#examples)

# Why does it exist? / Motivation / Rant

[DISCLAIMER: unformal language]

Y'all know how we live in the 5G era, so for music folks that would mean streaming music 24/7... but (one or more of):

- there is no mobile network / wifi at your office / parent's home / hotel room / on the road / at the back of your house
- you have a limited data allowance anyway
- spotify feels like both an ad gatling gun and a noisy radio (because of the network bandwith playing yo-yo)
- your entry-level phone/PC 2.4GHz antenna can't deal with both Wi-Fi music streaming and bluetooth connection to headphone/speakers
- youtube/yt music either replay the same 5 songs forever or goes its way on some crappy music that's unlike everything you like. It's a nice tool to discover new things, but not to actually listen to music
- yeah, music streaming is pretty not here yet

[DISCLAIMER: personal opinion]

For people who truly enjoy music, nothing beats yet having a local library, even with the hassle of managing, de-duplicating, and updating it constantly.

Auto-ytdl is there to help (you) with all that: there are tons of great artists that publish new songs everyday; having a local music library should not mean that we have to forsake listening to those!
Plus, auto-ytdl comes with management of duplicates of newly-downloaded songs, based on metadata so you don't have multiples identical song but from different youtube channels.

# Doesn't it exist already?

No.

[deserves mention for existing]

The closest I could find is MediaHuman (paid, expensive, closed-source) Youtube-Downloader: as of writing, it seems to have 'tracking' capabilities, and little explications given.
All this looked a bit fishy, it has a nice GUI though.
Moreover, it only offers a .deb package for "GNU/Linux OS" and .deb support for Arch (btw I use Arch) is not first-class.

# How does it works?

see also [Usage](#usage) and [Examples](#examples)

1. Add some of your favorite (youtube\*) channels / referencers /artist

2. At your next update command, all newly-released music from specified sources will be downloaded, cleaned, de-duplicated, and added to your music library.

3. [optionnal] Tinker with the options

\* playlist or channels from Dailymotion, vimeo or anything youtube-dl can download from can in theory work, but have not been tested yet

# Features

- Auto-download of all new music from a simple command
- Add/remove/list all your favorite music providers (not tested on anything other than youtube channels)
- Clean and filter by tags so only 'true' and unique songs (according to config) end up in your library
- Can still handle one-shot downloads, or include older songs of (newly discovered) artists
- Comprehensive config
- WIP

# Dependencies

- youtube-dl
- ffmpeg
- python3-pip (for manual install)

# Install

- auto-ytdl will be available in the AUR
  [link placeholder]
- install from source:

```
git clone https://github.com/michaelb/auto-ytdl
cd auto-ytdl
pip install --user .
```

# Usage

Once installed you can run

```
aytdl [COMMAND][OPTIONS] [URLs ..]
```

# Examples

```
# asking for help
aytdl --help

#asking for help about 'update' command
aytdl update --help

#add Mr SuicideSheep to followed channels
aytdl add https://www.youtube.com/channel/UC5nc_ZtjKW1htCVZVRxlQAQ

#see all the added sources
aytdl list

> url1
> url2
> ...

#remove Mr SuicideSheep channel from followed sources
aytdl remove https://www.youtube.com/channel/UC5nc_ZtjKW1htCVZVRxlQAQ

#download all new music from all sources
aytdl update


#download rick's astley famous song
aytdl update https://www.youtube.com/watch?v=dQw4w9WgXcQ

#download all music ever from Mr SuicideSheep, no just new ones
aytdl update --include-old https://www.youtube.com/channel/UC5nc_ZtjKW1htCVZVRxlQAQ

# download a 1-hour concerto (not fitting the (configurable) criteria for 'normal' music)
aytdl update https://www.youtube.com/watch?v=PM0HqmptYlY --force

#edit the config file
aytdl edit
```
