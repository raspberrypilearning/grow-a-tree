## How still can you be?

If you have a Scratch account you can make a copy by clicking **Remix**.

Below, you should see a forest backdrop and a teeny tiny tree in the bottom centre of the screen. Stay as still as possible to make the tree grow. The project works best in full screen mode.

Click the green flag to play the game.

<div>
<iframe src="https://scratch.mit.edu/projects/396479175/editor/embed" allowtransparency="true" width="485" height="402" frameborder="0" scrolling="no" allowfullscreen></iframe>
</div>

## Set the screen

Replant the tree, grow it a little and improve the instructions for the player! You're going to work on the first part of the program.

--- task ---
+ Open the code editor. Tree sprite is currently planted at x: 0 and y: -160. Feel free to plant it in a different position. By the way, the very centre of the stage is x: 0 and y: 0.
```blocks3
move to (0) (-160) ::motion
```
+ At the start of the game, Tree sprite is scaled to 10% of its actual size. Kick start its size by changing its percentage (%) value.
```blocks3
set size to [10%] ::looks
```
+ The instructions currently say "Keep still!". That's a bit dull, eh? Can you jazz up the instructions a bit?
```blocks3
say [Keep still!] for (2) seconds ::looks
```
Run the program to check your modifications for the program's set-up.
--- /task ---

## Build the camera detector
That's the set-up done. Now, a forever block wraps around the rest of the program so it runs forever until the game ends.

Inside the forever block are two conditions - they are great for developing user interaction. Let's see how.

The camera is set to pick up any motion on the stage.
```blocks3
<(video [motion v] on [stage v] ::video) < (10)>
```
In the first condition:
if the player moves less than 10 then, the size of Tree sprite increases by 1.
else the Tree sprite shrinks by -1! 

```blocks3
	if <(video [motion v] on [stage v] ::video) < (10)> then ::control 
		change size by (1) ::looks
	else 
		change size by (-1) ::looks ::control
	end
```
Shrinking the tree by -1 is the player's punishment for moving too much!.

--- task ---
+ Test the game for future players by changing Tree sprite's size.
```blocks3
change size by (1) ::looks
```
```blocks3
change size by (-1) ::looks
```
Run the program to check your modifications.
--- /task ---
Does the game feels more reactive if you increase and/or decrease Tree sprite's size? These are the kind of thing that Games Developers have to consider when designing for user interaction.

## Stop the tree from getting too big!
There's a second condition.

if the Tree sprite touches the edge of the stage then, say block is actioned with "Try again!" 
```blocks3
if (touching [edge v] ? ::sensing) then ::control
			say [Try again.] for (2) seconds ::looks
			stop [this script v]
```
Also included in this action is 'stop this script' - this stops the tree from growing so it doesn't get too big for the stage.

'stop this script' also stops the forever block. It can now relax.

--- task ---
+ Test the second condition by dragging it away from the main scripts. Below highlights which blocks to drag away. Run the program again.
```blocks3
if (touching [edge v] ? ::sensing) then ::control
			say [You did it! Stand on one leg to make it harder and click the green flag to play again.] for (2) seconds ::looks
			stop [this script v]
```
+ Does that tree just keep on growing? Hmmm, nice but remember we do need to end this game sometime soon!

+ Drag the blocks back in to script again and re-run the program. Finger's crossed no blocks have gone astray. 

+ Run the program to check.
--- /task ---
