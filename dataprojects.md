---
layout: page
title: Personal Informatics
author: Steven Buehler
date: 2020-12-09
---
# Personal Informatics Projects

I'm a _huge_ fan of personal informatics (also known as "Quantified Self&trade;", "life hacking", "self-tracking", among many other descriptors). I suppose it goes right with my autistic tendencies to play around with data for fun as well as for a paycheck. It's also a good way to keep track of myself and the changes that happen in my body, my mood, my diet, &c., in ways that I can see patterns that may need changing or take pride in the progress that I make.

## Current Personal Informatics Projects

- **[Where I've Been](/whereivebeen)**  
  <font size="-1">Using the [Swarm](https://www.swarmapp.com) and [Google Maps](https://maps.google.com) <abbrev name="Application Programming Interface">API</abbrev>s to display the last 250 check-ins I've made in Swarm.</font>

## My Tracking Tools

- **[FitBit](https://www.fitbit.com) Charge 3**  
    <font size="-1">A simple wearable that tracks information throughout the day like steps, calorie burn, heart rate, sleep cycles&hellip; I pull my tracking data via the [FitBit API](https://dev.fitbit.com) for later analysis and to import into my Apple Health database, and also share it with my doctor. It also helps provide me with some motivation to keep trying to get in shape.  I use a [PowerShell Core](https://www.powershell.org) script to pull this data as comma-delimited files (CSVs) and then a paid app called "CSV Import" on my phone to import them into Apple Health.
    
    Why not just use an [Apple Watch](https://www.apple.com/watch), you ask? Because it's hard to track your sleep when you have to charge your device every night. The FitBit devices usually only need charging about once a week.  With Apple Fitness+ now about to come out, that may change my thinking.
    </font>

- **[Swarm](https://www.swarmapp.com) Mobile App**  
    <font size="-1">Swarm was spun off from [Foursquare](https://www.foursquare.com) as a separate app for life-logging and posting checkins to places that I find myself at.</font>

- **My [iPhone](https://www.apple.com/iphone) 11 Pro Max**  
    <font size="-1">Specifically, I've created workflows via the out-of-the-box [Shortcuts](https://support.apple.com/en-us/HT209055#:~:text=Find%20new%20shortcuts%20in%20the%20Gallery.%201%20On,to%20add.%205%20Tap%20Add%20to%20Siri.%20) app to maintain a "personal log" whenever I do something that I need to track or want to otherwise make a time-stamped entry. Each entry contains a timestamp, my location (as determined by the phone), and whatever text message I provide.  In theory this could replace Swarm for place check-ins, but Swarm is more consistent on locations.</font>

- **[Emacs `org-mode`](https://www.orgmode.org)**  
    <font size="-1">I use this extensively at work to track my hours on task, maintain a portable calendar I can easily load onto my other devices, make sortable tables and lists that I can later use as data for tracking, you name it. The `emacs` text editor itself has been around since the 1970s (if it ain't broke, why fix it?).</font>

-   I used to have apps like **Dash** and **Automatic** that use an <abbrev    name="On Board Diagnostics">OBD</abbrev> adapter device in my car to track where I drove and my car's performance metrics, but both services have since shut down and the only suitable alternative that I have is for Windows 10 (none of my Windows devices have built-in GPS) and Windows Phone (defunct).