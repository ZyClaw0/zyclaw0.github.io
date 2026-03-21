---
title: "cURL - Command line URL tool"
pubDatetime: 2019-01-18T00:00:00Z
modDatetime: 2019-01-18T00:00:00Z
featured: false
draft: false
tags:
  - "Terminal"
  - "Tools"
  - "cURL"
description: ""
---





cURL doesn’t stand for command line URL tool but it is one of the tools available for transferring of files seamlessly through the terminal. cURL is considered an abbreviation for **Client URL Request Library**. cURL supports multiple network protocols allowing to access files through HTTP(S), FTP(S), SCP to name a few.

Even though I have heard and seen what cURL is, I haven’t used it until yesterday when I had to download multiple audio files from a website (say 50). The site didn’t allow to directly download all the files at once, but had to navigate to different pages to get the link to download the file. After downloading two files manually, I realised that the only difference between the files were, in their filenames with serial numbers ( file-001.mp3, file-002.mp3 & so on). A perfect use case for cURL to download the files, all at once! I decided not to search the internet on how to do it and instead opened the terminal and started reading the man page. Nothing fancy, `-O` (uppercase o) to save the file using the remote name, as stored in the server.
`curl -O <https://website.com/media/file-001.mp3`

Failed!

The output was all zeroes. Tried navigating to the url through the browser to verify if the path is correct and it works perfect. Decided to try again ensuring to make no typos. Again, failed! Although my hands were itching to perform a google search to figure out the answer, decided to run through the manual one more time. Didn’t find anything helpful in particular but read something interesting about redirects with `-L` option. Even though I didn’t notice any redirects occurring on the webpage, decided to try it out before losing to the search engines.
`curl -LO <https://website.com/media/file-001.mp3`
Yes! The file started downloading without any errors. Now to get the files in sequence, as stated in the manual surrounded them using `[ ]` 

`curl -LO <https://website.com/media/file-[001-050].mp3`
Bingo! Within a minute, all the 50 files were downloaded to the current working directory!

I was quite happy to have found a use case and succeed in accomplishing it. It did save a plenty of time of navigating through each of those different pages to obtain the audio file.

One can learn more about cURL using the manual page or from their [website](https://curl.haxx.se/). They also have a book *Everything Curl* which is available in [Web Version](https://ec.haxx.se/), [PDF](https://ec.haxx.se/), [Mobi](https://legacy.gitbook.com/download/mobi/book/bagder/everything-curl) (ebook) and [ePub](https://legacy.gitbook.com/download/epub/book/bagder/everything-curl) (ebook)

---

🏠

---