## How still can you be?

**Online**: Open the 'Grow a tree' starter Scratch project [www.rpf.io/grow-a-tree-on](http://rpf.io/grow-a-tree-on){:target="_blank"}.

To open this project offline, follow the link to the Scratch Offline Editor: [www.scratch.mit.edu/download](https://scratch.mit.edu/download){:target="_blank"}.

If you have a Scratch account you can make a copy by clicking **Remix**.

Below, you should see a forest backdrop and a teeny tiny tree in the bottom right of the screen. Stay as still as possible to make the tree grow.

Click the green flag to play the game. The project works best in full screen mode.

<div>
<iframe src="https://scratch.mit.edu/projects/396932945/embed" allowtransparency="true" width="485" height="402" frameborder="0" scrolling="no" allowfullscreen></iframe>
</div>

## Set the screen

You're going to work on the first part of the program to grow Tree sprite a little and improve the instructions for the player!

--- task ---
+ Open the code editor. 

+ At the start of the game, Tree sprite is scaled to 10% of its actual size. Why not start the tree at a larger percentage (%).
```blocks3
set size to [10%] ::looks
```
+ The instructions currently say "Keep still!". That's a bit dull. Can you jazz up the instructions?
```blocks3
say [Keep still!] for (2) seconds ::looks
```
+ Run the program to check your changes.
--- /task ---

## Build the camera detector
That's the set-up done. A forever block wraps around the rest of the program so it runs forever (or until the game ends).

Inside the forever block are two conditions - they are great for developing user interaction. Let's see how.

The camera is set to pick up any motion on the stage.
```blocks3
<(video [motion v] on [stage v] ::video) < (10)>
```
In the first condition:
+ if the player moves less than 10 then, the size of Tree sprite increases by 1. 
+ else Tree sprite shrinks by -1! 

```blocks3
	if <(video [motion v] on [stage v] ::video) < (10)> then ::control 
		change size by (1) ::looks
	else 
		change size by (-1) ::looks ::control
	end
```
Shrinking Tree sprite by -1 is the player's punishment for moving too much!.

--- task ---
+ Test the game for future players by changing the amount Tree sprite's grows or shrinks.
```blocks3
change size by (1) ::looks
```
```blocks3
change size by (-1) ::looks
```
+ Run the program again to check your changes.
--- /task ---
Does the game feels more respinsive when you increase and/or decrease Tree sprite's size? These are the kind of things that Games Developers have to consider when designing for user interaction.

## Stop Tree sprite from getting too big!
Now to the second condition.

+ if Tree sprite touches the edge of the stage then, the say block says "Try again!" 
```blocks3
if (touching [edge v] ? ::sensing) then ::control
			say [Try again standing on one leg!] for (2) seconds ::looks
			stop [this script v]
```
Also included in this action is 'stop this script' - this stops everything including Tree sprite from growing so it doesn't get too big for the stage.

'stop this script' also stops the forever block. It can now relax!

--- task ---
+ Test the second condition by dragging it away from the main scripts. Below highlights which blocks to drag away. Run the program again.
```blocks3
if (touching [edge v] ? ::sensing) then ::control
			say [Try again standing on one leg!] for (2) seconds ::looks
			stop [this script v]
```
+ Does that tree just keep on growing? Hmmm, nice but remember we do need to end this game sometime soon!

+ Drag the blocks back in to the script again. Let's hope no blocks have gone astray.

+ Run the program to check your changes.
--- /task ---
