## How still can you be?

If you have a Scratch account you can make a copy by clicking **Remix**.

You should see a forest backdrop and a teeny tiny tree in the bottom centre of the screen. Remember, stay as still as possible and the tree will grow.

Click the green flag to play and follow the instructions embedded in the game.

<div>
<iframe src="https://scratch.mit.edu/projects/396479175/embed" allowtransparency="true" width="485" height="402" frameborder="0" scrolling="no" allowfullscreen></iframe>
</div>

## Set the screen

First we have set the scene with a Forest backdrop and a Tree sprite. Can you help replant the tree and improve the instructions for the player?

--- task ---

```blocks3
+when flag clicked
+move to (0) (-160) ::motion
+set size to [10%] ::looks
+say [Keep still to grow the tree. Top tip - it helps to lean on your hands.] for (2) seconds ::looks
forever
	if <(video [motion v] on [stage v] ::video) < (10)> then ::control 
		change size by (1) ::looks
	else 
		change size by (-1) ::looks ::control
	end
	if (touching [edge v] ? ::sensing) then ::control
			say [You did it! Stand on one leg to make it harder and click the green flag to play again.] for (2) seconds ::looks
			stop [this script v]
		end
end
```
+ Open the code editor. Tree sprite is currently planted at x: 0 and y: -160. Feel free to plant it in a different position. 

```blocks3
move to (0) (-160) ::motion
```
+ Tree sprite is scaled to 10% of the size of the original tree image. Alter its size by changing the percentage (%).

```blocks3
set size to [10%] ::looks
```
+ Next we need to let the player know how to play the game! The instructions currently day "Keep still to grow the tree. Top tip - it helps to lean on your hands." That's a bit dull, eh? Can you jazz up the instructions a bit?

```blocks3
say [Keep still to grow the tree. Top tip - it helps to lean on your hands.] for (2) seconds ::looks
```
--- /task ---

## Build the camera detector

Currently the camera is set to pick up any motion on the stage. For this we are using a forever block to ensure that all the following conditions are checked - forever - throughout the game.

```blocks3
when flag clicked
move to (0) (-160) ::motion
set size to [10%] ::looks
say [Keep still to grow the tree. Top tip - it helps to lean on your hands.] for (2) seconds ::looks
+forever
	if <(video [motion v] on [stage v] ::video) < (10)> then ::control 
		change size by (1) ::looks
	else 
		change size by (-1) ::looks ::control
	end
	if (touching [edge v] ? ::sensing) then ::control
			say [You did it! Stand on one leg to make it harder and click the green flag to play again.] for (2) seconds ::looks
			stop [this script v]
		end
end

```
As well as the forever block there are two conditional statements. Conditional statements are great for creating games which involve user interaction.

Let's address the first conditional statement; if then, else.
if then, else checks whether a condition has been met. If it has, then it allows the stated action to go ahead, else it allows another stated action. 

It's even simpler to say:
if a condition is met > then action
else other action

In the Grow a tree program:
if (the player) moves less than 10 > then the action is to change the size (value) of Tree sprite by 1.
else the action is to shrink the size (value of Tree sprite by -1! 

```blocks3
	if <(video [motion v] on [stage v] ::video) < (10)> then ::control 
		change size by (1) ::looks
	else 
		change size by (-1) ::looks ::control
	end
```
Shrinking the tree vy -1 is the player's punishment for moving too much!.

--- task ---
+ Test the game for other players by changing the Tree sprite's size (value).
```blocks3
change size by (-1) ::looks
```
--- /task ---
Do you think the game feels more reactive when you increase or decrease the image size (value)?

## Stop the tree from getting too big!
There's one more conditional statment; if then. It's a little simpler:

if the Tree sprite touches the edge of the stage > then the action is say "You did it! Stand on one leg to make it harder and click the green flag to play again." 
```blocks3
if (touching [edge v] ? ::sensing) then ::control
say [You did it! Stand on one leg to make it harder and click the green flag to play again.] for (2) seconds ::looks
```
Also included in the action is 'stop this script' - this stops the whole program!
```blocks3
stop [this script v]
```
Importantly 'stop this script' stops the tree from growing. If the tree grew too big it would fill the screen and the game would never end. And we all need to go home sometime today!

'stop this script' also stops the forever block from checking those conditions. The forever block can now relax.

--- task ---
+ Test the last conditional statement; if then by dragging the if then blocks away from the main scripts. See below for whcih blocks to drag away. Run the program again.

+ Does that tree just keep on growing? Hmmm, nice but remember we do need to go home at some point!

+ Put the blocks back in the program again and re-run the program. Finger's crossed no blocks have gone astray. It should look like this:
```blocks3
if (touching [edge v] ? ::sensing) then ::control
say [You did it! Stand on one leg to make it harder and click the green flag to play again.] for (2) seconds ::looks
stop [this script v]
```
--- /task ---
