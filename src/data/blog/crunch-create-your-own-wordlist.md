---
title: "Crunch - create your own wordlist"
pubDatetime: 2019-03-04T00:00:00Z
modDatetime: 2019-03-04T00:00:00Z
featured: false
draft: false
tags:
  - "Terminal"
  - "Tools"
description: ""
---





Crunch is a wordlist generator useful for password cracking. Sometimes, you don’t want to use large precomputed wordlists and instead you may want to create your own. Crunch is your solution! It is a small but powerful command line tool allowing you to specify the criteria for the wordlists and generate it for you.

The most common and useful features include minimum maximum length, pattern specification and resume capability [very handy when the input is large].

Create and save your wordlist to a file using the `-o` option. You can specify special patterns using `-t` option followed by any of these:

`%` [percent] for numbers
`^` [caret] for  symbols: ! @ # $ % ^ & * ( ) – _ + = ~ ` [ ] { } | \ : ; ” ‘ < > , . ? / [space]

`@` [at] for lower case letters 

`,` [comma] for Upper case letters

If you wish to include any of these characters (% ^ @ ,) in your wordlist, you can do so by using the literal `-l` option [lowercase for L] along with `-t` option. Here are some examples:

- **Wordlist with  characters, using 'abcdefgh'**
    
    `crunch   abcdefgh -o eight_char.txt`
    In this example, crunch will generate a wordlist of  min characters,  maximum characters from these characters ‘abcdefgh’.
    
- **Wordlist with specific characters at specific positions**
    
    `crunch   -t a%b^c@d, -o special.txt`
    In this example, the characters a,b,c,d are fixed in those positions and will not change. Hence the output file will contain ab!cadA upto ab[space]czdZ
    
- **Wordlist with special characters**
    
    `crunch   -t abcd,%@^ -l zzzz,z@z -o literals.txt`
    In the third example, special characters `,` and `@` will not be replaced with uppercase and lowercase letters, instead they’ll be treated as a literal character. Note that the length of `-t` and `-l` option should match and hence should be padded with some character (z in this case).
    
- **Wordlist with permutations**
    
    `crunch   -o possibilities.txt -p In Any Order`
    In the last example, different permutation of the words In, Any, Order will be output to the file. In this case, output will contain  lines. Here, we specify the min and max length as  as they are mandatory options for crunch.
    

The tool comes in built on Kali Linux. Although, on Windows, you cannot run crunch through command prompt, although, you can set it up by downloading the files from [SourceForge](https://sourceforge.net/projects/crunch-wordlist/) and installing them on a linux terminal.
