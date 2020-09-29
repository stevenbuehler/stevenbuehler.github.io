---
layout: post
title: Memobird Workflows for macOS Automator and iOS/iPadOS Shortcuts
date: 2020-09-25
author: Steven Buehler
categories:
  - Geekery
  - macOS
  - iOS
  - iPadOS
  - memobird
---

There seems to be a trend developing for consumer-oriented thermal receipt printers for printing notes, lists, and other small items for transient use lately. Among one of the early entries into the space was Intertek's [Memobird](https://www.mymemobird.com), which uses an Android/iOS app, web app, or small desktop app to send text and images to be printed on standard 58-mm-wide thermal paper that the company offers in various colors in plain or sticker-backed rolls (you can also use regular reciept paper from your local office supply store, but the output quality is not as good).  You can also create codes to give to others so they can send messages to your little printer. Most of these printers use Epson's ESC/POS print language with a proprietary layer that obscures it from the end-user. 

The app that was designed for the memobird allowed mobile users to send text or images from any other application to the printer via the mobile OS' "share" functions&mdash;until about a year ago, when the functionality was inexplicably removed in an application update and never restored. Now, the content has to be copied and pasted into the memobird app and then sent to the printer, unless you know the API to develop another way to send content to the printer. That's what this post is about.

Not long after the sharing function was removed from memobird's app, the Chinese maker of the printer released an "Open API" specification for developers to send content to the printer through Intertek's Chinese print server. The API specification can be downloaded as an English `.pdf` from the [Chinese web site](http://api.memobird.cn). The API is pretty straightforward but certain details are not adequately disclosed (for example, the API prefers `application/x-www-form-encoded` input, although it can also handle `application/json`).

Before getting too much further into this how-to, you're going to need a developer access key from Intertek. The first part of their API docs explains how to get one, and also how to get the userID that you'll need for API requests (you'll only need to request it once).  You're also going to need the ID code from your printer and a means of generating a timestamp for the request (the API doesn't care what format the timestamp is in).

## General considerations

The API expects your input (the text or image you want to print) to be `base64` encoded. Fortunately, iOS shortcuts has a step that will do this; and if you're using Automator there is a `base64` command that can be run in the shell to handle it.

## Sending plain text

The first issue that will come up with sending plain text is print width&mdash;the printer's output is 32-columns across, and it doesn't know where to break up long lines, so long text just arbitrarily wraps around from one line to the next breaking up words wherever it wants to, rather than intelligently breaking up lines at the end of words, which looks much nicer. iOS Shortcuts does not provide any option for doing this, so I end up sending it to my Raspberry Pi (or your Mac can do this also) over SSH and using `fmt` on the outside machine to reformat the text before using `curl` to send it to the print server. If you're not concerned about this (or you're sending it as HTML), then this outside connection isn't needed.