# whatisthis
Discover what a linux file or desktop link is from GUI file manager before clicking on it

## as in what is this file:  whatisthis filename 

## Why 
I found an item on my linux Mint desktop called "Access Archive".  I wanted to know what it was, without clicking on it to see what would happen if I clicked it. 

It turns out there are a lot of commands involved in discovering about a file before clicking on it.  It is a URL, where does it send you, will it launch an executable, will automatic app will process it and so on. 

## Solution 

Copilot and I developed this script to explore a file before clicking it.  As a CLI, you can enter whatisthis and the filename.  Also added the ability to for right context menu. 

## adding to nemu's GUI 

## roadmap, things I might add if needed or discovered or other distros 
* support for other graphical file managers than just nemo
* add other commands to explore results in more details
* validate if a command really exist for launching
* if URL link throw it into a security check 
* open for other suggestions

## Instructions for adding to context menu for nemo gui 
* create (nano, vim, ...): ~/.local/share/nemo/actions/whatisthis.nemo_action
* enter:
[Nemo Action]
Active=true
Name=What is this?
Comment=Show what this launcher actually does
Exec=gnome-terminal -- bash -c 'whatisthis "%F"; read'
Selection=Any
Extensions=desktop;
* save 
* restart nemo from cli: nemo -q 
  
