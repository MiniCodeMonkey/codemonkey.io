---
title: Customizing the look and feel of macOS
date: "2019-03-13T22:40:32.169Z"
template: "post"
draft: false
slug: "/posts/customizing-the-look-and-feel-of-macos/"
category: "Workflow"
tags:
  - "macOS"
  - "Development"
description: "A quick introduction to my adventures in customizing macOS, visually"
---

I recently went down the rabbit hole of completely customizing the look and feel of my development environment.

![](/media/chunkwm-screenshot.png)

> At first glance, there's not much revealing that this even macOS

I'm still just getting used to everything, but this is my setup so far:

* [ChunkWM](https://koekeishiya.github.io/chunkwm/) which neatly arranges all of the windows on my screen
* [skhd](https://github.com/koekeishiya/skhd) which allows me to define global hotkeys to control ChunkWM
* [Pecan](https://github.com/zzzeyez/Pecan) (built on [Übersicht](http://tracesof.net/uebersicht/)) which renders the neat status bar that you see at the top of the screen

## Preparation

Before I got started, I did the following:

* Configured the Dock to automatically hide (System Preferences > Dock > Automatically hide and Show the Dock)
* Configured the Menu Bar to automatically hide (System Preferences > General > Automatically hide and show the menu bar)

For iTerm 2:
* Hide the title bar for a nice, clean look (Preferences > Profiles > Default > Window > No Title Bar),

> I also added a little bit of transparency for some extra 👌

## ChunkWM and skhd

The best guide I found was from the [Hatena Blog](http://hde-advent-2017.hatenadiary.jp/entry/2017/12/24/000000), shihanng walks through the whole setup and how the pieces tie together. Here is my notes.

### ChunkWM

![](/media/chunkwm-insert.gif)

This is what ChunkWM does in a nut shell. ChunkWM runs as a daemon in the background (there's no UI) and when a new window is opened, Chunk adds it on to the stack and neatly arranges it. There are loads of customization options and ways to make Chunk work to your preference.

Here's my highlights so far:

* The FFM plugin, which automatically focuses the window that your cursor is over (takes some time to get used to, but I like it so far)
* The ability to customize the gap between windows and the side of the screen (which is how I make space for the "Pecan" status bar)
* Works exceptionally well with multiple monitors

## skhd

This little daemon was written by the same author as ChunkWM and they work great in conjuction with each other. I ended up printing out a little cheatsheet with all of the ChunkWM shortcuts, which I have been using all week to get up to speed.

Another neat advantage of skhd is that you can run any arbitary command. So I have configured a global `alt` + `return` hotkey to open a new Terminal window no matter where I'm at.

