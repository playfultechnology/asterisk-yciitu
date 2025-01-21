# asterisk-yciitu
"Your Call Is Important To Us" - a multi-state IVR telephony maze game for Asterisk PBX 

# Objective / How to Play
The objective of the game is simple, and should be instantly familiar to many players: you simply need to find a way to get hold of the customer service department of a fictional company. That's it. I'll even give you phone number: 
0800 123123
I've heard they're experiencing an unusually high volume of calls at the moment though, so you might need to be transferred to another department.

# Disclaimer
Any resemblance between the frustration of events depicted in this game and any real-life customer service experience are entirely intentional.

# About the Game
The thematic inspiration for this game will probably be immediately familiar to many players: trying to get hold of the customer service department of a large organisation can seem like a complex bureaucratic maze – endlessly being transferred between different departments, often only to end up back where you started. Or, worse still, nearly reaching the end goal (often after spending a significant amount of time) only to “fall into a pit” when your call becomes suddenly disconnected.

In terms of the implementation of the game mechanics, I was inspired by classic text adventure computer games. Mazes have a long history of being used in such games, and one particularly interesting example appeared in Colossal Cave Adventure, a game published in 1976. Colossal Cave Adventure was noted for featuring a maze where each of ten room descriptions was exactly the same: “YOU ARE IN A MAZE OF TWISTY LITTLE PASSAGES, ALL ALIKE.” Aside from the non-specific description, another confusing detail of this maze was that it was non-Euclidean; that is to say, going due North from one room, and then immediately due South, did not necessarily place you back where you started. 

In Colossal Cave Adventure, one method players could use to map the maze was by dropping objects to act as landmarks as they passed through the rooms, creating a breadcrumb trail that enabled the layout to be mapped. In Your Call is Important to Us, there are no items to drop, but players seeking to find the way out of this bureaucratic nightmare should take careful note not only of their current location in the maze, but how they got there. 

Robert Abbott created a "real-world" analogue version of such a multistate maze on which this game is also heavily inspired, which is described here: http://www.logicmazes.com/bur.html 

# Need a Hint?
 - Hint #1: Use pen and paper to map out the "route" taken between departments
 - Hint #2: Take note not only of the department to which you are currently on hold, but also the department *from which you were transferred* to get there
 - Hint #3: The optimal solution requires only 5 button presses from the initial call being made

# Installation
1. Install Debian OS, Asterisk, and FreePBX as per the instructions at https://github.com/playfultechnology/RasPBX
2. Use WinSCP to login to the Raspberry Pi as root user (root:raspberry)
3. Copy `extensions_custom.conf` to `/etc/asterisk/`
4. Copy `extensions_yciitu.conf` to `/etc/asterisk/`
5. Copy contents of `souds/en/custom/yciitu` to `/var/lib/asterisk/sounds/en` 
6. Use PuTTY to reload dialplan `rasterisk –rx 'dialplan reload'`  (or, you can do this via the FreePBX GUI by going `Settings-> Advanced -> Leave Reload Bar Up` and then hitting `Apply Config`)

# Editing the game
1. All game logic is contained in `extensions_yciitu.conf`
2. https://g711.org is a useful resource for converting audio into the appropriate format for Asterisk to play
