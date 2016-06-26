# Seanchai
The main goal of this project is to create a language that gets compiled into a
set of characters and events to run in a main program. The main program will run
and the characters will choose actions and interactions to do as time goes on as well
as react to events. This should create a complete story, and can be leveraged as
a tool for creating AI for games that dynamically react to a player's actions and
create story without a set script. This would allow for an exponential number of
differing narrative experiences for a player, something that has never before been possible.


## The Main Loop
The main program takes in a set of characters, actions, and events and steps through
timesteps, allowing each AI driven character do decide what action they will take. 
The end state of this loop has yet to be determined. Possibilities are certain number of timesteps
or an ending event that is triggered under certain conditions.


## Events, Actions, and interactions
These are what the characters deal with directly.
1. Events are triggered from the world after certain prerequisites, such as a bomb going off, a volcano erupting, or a demon awakening.
2. Actions are things a character can do, such as go dancing at the club or quest for the holy grail.
3. Interactions are what a character can do with another character. These are things like converse, argue, fight and so on.
Tentatively, we will have interactions for some basic objects as well, such as weapons and other various items that characters commonly use.

## Characters
Characters do the bulk of the lifting. It is the characters that are responsible for the story.
Each one is made with different characteristics that affect how they make decisions. They have
varied stats, sets of knowledge, priorities, possible conditions, sexuality, and internal models
of other characters.
