## How still can you be?

If you have a Scratch account you can make a copy by clicking **Remix**.

Below, you should see a forest backdrop and a teeny tiny tree in the bottom centre of the screen. Remember, stay as still as possible to make the tree grow.

Click the green flag to play and follow the instructions embedded in the game.

<div>
<iframe src="https://scratch.mit.edu/projects/396479175/editor/embed" allowtransparency="true" width="485" height="402" frameborder="0" scrolling="no" allowfullscreen></iframe>
</div>

## Set the screen

The scene is set with a Forest backdrop and a Tree sprite. Can you help replant the tree and improve the instructions for the player? We're going to work on the first part of the program outlined in black.

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
+ Open the code editor. Tree sprite is currently planted at x: 0 and y: -160. Feel free to plant it in a different position. The very centre of the stage is x: 0 and y: 0.
```blocks3
move to (0) (-160) ::motion
```
+ The tree is scaled to 10% of the size of the original Tree sprite graphic. Reset its visible size by changing the percentage (%).
```blocks3
set size to [10%] ::looks
```
+ Next we need to let the player know how to play the game! The instructions currently say "Keep still to grow the tree. Top tip - it helps to lean on your hands." That's a bit dull, eh? Can you jazz up the instructions a bit?

```blocks3
say [Keep still to grow the tree. Top tip - it helps to lean on your hands.] for (2) seconds ::looks
```
Run the program to check your modifications.
--- /task ---

## Build the camera detector
Currently the camera is set to pick up any motion on the stage. The forever block wraps around the rest of the script to ensure that it constantly runs - forever - until the game ends. See the forever block below - it has been highlighted with a black outline.

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
Inside the forever block are two conditional statements. Conditional statements are great for creating games that involve user interaction.

Let's address the first conditional statement; if then, else.
if then, else checks whether a condition has been met. If it has, then it allows the stated action to go ahead, else it allows another stated action to go ahead. 

It's even simpler to say:
if a condition is met -> then action
                      -> else other action

In the Grow a tree program:
if the player moves less than 10 -> then the action is change the size (value) of Tree sprite by 1.
                                 -> else the action is to shrink the size (value) of Tree sprite by -1! 

```blocks3
	if <(video [motion v] on [stage v] ::video) < (10)> then ::control 
		change size by (1) ::looks
	else 
		change size by (-1) ::looks ::control
	end
```
Shrinking the tree by -1 is the player's punishment for moving too much!.

--- task ---
+ Test the game for future players by changing the Tree sprite's size (value).
```blocks3
change size by (-1) ::looks
```
Run the program to check your modifications.
--- /task ---
Do you think the game feels more reactive when you increase and/or decrease the Tree sprite's size (value)?

## Stop the tree from getting too big!
There's one more conditional statment; if then. It's a little simpler:

if the Tree sprite touches the edge of the stage -> then the action is say "You did it! Stand on one leg to make it harder and click the green flag to play again." 
```blocks3
if (touching [edge v] ? ::sensing) then ::control
			say [You did it! Stand on one leg to make it harder and click the green flag to play again.] for (2) seconds ::looks
			stop [this script v]
```
Also included in the action is 'stop this script' - this stops the whole program!

Importantly 'stop this script' stops the tree from growing. If the tree grew too big it would fill the screen and the game would never end!

'stop this script' also stops the forever block from checking running. The forever block can now relax.

--- task ---
+ Test the if, then conditional statement by dragging it away from the main scripts. Below highlights which blocks to drag away. Run the program again.
```blocks3
when flag clicked
move to (0) (-160) ::motion
set size to [10%] ::looks
say [Keep still to grow the tree. Top tip - it helps to lean on your hands.] for (2) seconds ::looks
forever
	if <(video [motion v] on [stage v] ::video) < (10)> then ::control 
		change size by (1) ::looks
	else 
		change size by (-1) ::looks ::control
	end
end


if (touching [edge v] ? ::sensing) then ::control
			say [You did it! Stand on one leg to make it harder and click the green flag to play again.] for (2) seconds ::looks
			stop [this script v]
      
 ```
+ Does that tree just keep on growing? Hmmm, nice but remember we do need to end this game sometime soon!

+ Drag the blocks back in to script again and re-run the program. Finger's crossed no blocks have gone astray. 

+ Run the program to check.

```blocks3
if (touching [edge v] ? ::sensing) then ::control
say [You did it! Stand on one leg to make it harder and click the green flag to play again.] for (2) seconds ::looks
stop [this script v]
```
--- /task ---
