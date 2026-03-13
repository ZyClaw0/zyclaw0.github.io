---
title: "The Bash Bunny"
pubDatetime: 2020-05-11T00:00:00Z
modDatetime: 2020-05-11T00:00:00Z
featured: false
draft: false
tags:
  - "Bash Bunny"
  - "Tools"
  - "Websites"
description: ""
---

# The Bash Bunny




I have decided to learn and have fun with a new tool called the Bash Bunny by [Hak5](https://shop.hak5.org/products/bash-bunny). I have decided to create a series of posts dedicated to this learning journey.

In this introductory post, I'll explain what the Bash Bunny is. It looks like a normal USB device with an LED and a switch on it. You might be wondering why is there a switch on a normal USB? Well, that is one of the strengths of the Bash Bunny and it helps in automation or running scripts. *The Bash Bunny is a simple and powerful multi-function USB attack platform.* So what exactly can you do with the Bash Bunny?

![bb.png](The%20Bash%20Bunny/bb.png)

The Bash Bunny emulates a combination of USB devices that computers inherently trust like gigabit ethernet, serial, flash storage and a keyboard. It also gives you a full linux terminal. When plugged in to a machine, you decide what the computer should recognise this device as. With a multi positional switch, you have three switch position to choose from including the configuration mode - AKA "arming mode", which is the the switch position closest to the USB head or sometimes also referred to as "Switch 3". Therefore, you have two positions "Switch 1" and "Switch 2" for carrying out your attack (**Note:-** You could also use the arming mode as an attack position, although it is only recommended for advanced users). Here's a diagram explaining the switch positions:

![bb1.png](The%20Bash%20Bunny/bb1.png)

While the Bash Bunny is plugged in using arming mode, it allows you to configure payloads for various  attacks. The arming mode also allows you to connect through serial and access the linux terminal of your Bash Bunny. A simple bunny script that is easy to read and understand, is saved in a text file in the corresponding switch folder (say, Switch 1), which  triggers the payload when the bunny is inserted with switch at respective position (in this case, switch 1 - farthest away from the USB head).

The attack specified in the payload, firstly, could include the Bash Bunny being used as an Ethernet device - allowing you to bring your own network. The Bunny serves as a DHCP server and the computer plugged in to, receives an IP address from the bash bunny allowing you to carry out various network related attacks. Secondly, the Bash Bunny can be configured as a USB keyboard that can inject keystrokes to the plugged in computer. It builds up on another famous Hak5 gear - the [USB Rubber Ducky](https://shop.hak5.org/products/usb-rubber-ducky-deluxe). It mimics a USB keyboard and inputs the command that an attacker would like to execute on the machine. Thirdly, the Bash Bunny can be used as a storage device allowing you to move files across the victim machine. Most of all, you can use these attack modes in combination with each other allowing you to leverage the complete power of the Bash Bunny! Wonder what the LED is for? It can be used to give an indication to the attacker as to what stage the payload is in. You can configure the colour, speed and the blink pattern to notify when the payload is loading, attacking or completed with success or failure.

The Hak5 team has done so well with the documentation of the Bash Bunny making it easier for anyone to start playing around with the Bash Bunny as soon as possible. You can find the wiki here. They also encourage the community to develop payloads and share to their [Github](https://github.com/hak5/bashbunny-payloads) repository, where you can find many other payloads for the Bash Bunny.

I hope this post helped you understand what the Bash Bunny is and gave you an opportunity to imagine the various attacks that could be possible from this USB device.

---

🏠

---