---
title: "Linux Terminal on Windows 10"
pubDatetime: 2019-03-10T00:00:00Z
modDatetime: 2019-03-10T00:00:00Z
featured: false
draft: false
tags:
  - "Linux"
  - "Terminal"
  - "Tools"
  - "Windows"
description: ""
---

# Linux Terminal on Windows 10




Have you ever been stuck with the windows operating system when you wanted to run some bash commands? Probably, you even downloaded some emulators to run your bash commands! Well, in windows 10, Microsoft has included a feature to allow you to install a Linux distro through the Microsoft Windows Store.

Before installing your favourite Linux distro, you have to enable a feature named *“Windows Subsystem for Linux”* from the *“Turn Windows features on or off”* setting from the control panel. Alternately, you could also enable this feature by running the following command through a Powershell prompt running as an administrator.

**`Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`**

When it prompts, select *“Restart Now”* or enter *“yes”*. After windows restarts, open the windows store and search for Linux. The screen will read *“Linux on Windows? Totally.”* Click on *“Get the apps”* to find various flavours of Linux. Select the one you like the most and click install. After the installation is complete, open the app from the start menu. It will take a few minutes to setup the program and prompt for username and password for your new system. Enter your username and password to enjoy the power of Linux on Windows!
