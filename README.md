# whatisthis
Discover what a linux file or desktop link is from GUI file manager before clicking on it

## as in what is this file:  whatisthis filename 

## Why 
I found an item on my linux Mint desktop called "Access Archive".  I wanted to know what it was, without clicking on it to see what would happen if I clicked it. 

It turns out there are a lot of commands involved in discovering about a file before clicking on it.  It is a URL, where does it send you, will it launch an executable, will automatic app will process it and so on. 

## Solution 

Copilot and I developed this script to explore a file before clicking it.
Show: If the file is a URL and to where, an executable file (with warning), resolve Symlinks, ...  

As a CLI, you can enter "whatisthis filename".  
From GUI add ability to for right click context menu. 



Gemini and I resolved the escaped space issue on some versions of nemo 


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
Name=What Is This
Comment=Runs whatisthis command on selected file
Exec=gnome-terminal -- bash -c 'whatisthis "$1"; read' dummy %F
Quote=double
Selection=any
Extensions=any;

* save 
* restart nemo from cli: nemo -q 

## version history 
* v1 = initial working code 
* v1.1 = fixed "Nemo Action", on some systems Nemo passed filenames with spaces as escaped characters which confused whatisthis. Solution: tell nemo don't do that. 

