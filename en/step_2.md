## How still can you be?

If you have a Scratch account you can make a copy by clicking **Remix**.

You should see you! And a teeny tiny tree in the bottom centre of the screen. Remember, stay as still as possible and the tree will grow.

Click the green flag to play and follow the instructions embedded in the game.

<div>
<iframe src="https://scratch.mit.edu/projects/396479175/embed" allowtransparency="true" width="485" height="402" frameborder="0" scrolling="no" allowfullscreen></iframe>
</div>

## Set the screen

First we have to set the scene by choosing the Forest backdrop and Tree sprite. We then have to 'plant' Tree (i.e. choose where the sprite is within the stage) and then we have to steer the player with opening instructions. There's a lot to do!

--- task ---

+ Open the code editor. Tree sprite is currently planted at x: 0 and y: -160. Feel free to plant it in a different position. 
```blocks3
when flag clicked
move to (0) (-160) ::motion
```
+ Tree sprite is scaled to 10% of the size of the original tree image. You can alter its size by changing the percentage (%).

```blocks3
set size to [10%] ::looks
```
+ Next we need to let the player know how to play the game! The instructions currently day "Keep still to grow the tree. Top tip - it helps to lean on your hands." That's a bit dull, eh? Can you jazz up the instructions a bit?

```blocks3
say [Keep still to grow the tree. Top tip - it helps to lean on your hands.] for (2) seconds ::looks
```
--- /task ---

## Build the camera detector

Currently the camera is set to pick up any motion on the stage.

There's a conditional statement; if then, else.
This basically means if the condition is met do the stated action, else do the other stated action.

It's even simpler to say:
if a condition is met > then action
else other action

In the Grow a tree program:
if (the player) moves less than 10 > then the action is to change the image value (size) of Tree sprite by 1.
```blocks3
if (video [motion v] on [stage v] ::video) < (10) then ::control
change size by (1) ::looks
```
else the action is to shrink Tree sprite by -1! 
```blocks3
change size by (-1) ::looks
```
(Shrinking the tree is the player's punishment for moving too much!).

--- task ---
+ You're testing the game for other players. Do you think the game feels more reactive when you increase or decrease the image value?

+ Have a go at changing the images value (size) for then.
```blocks3
```
+ Now have a go at changing the images value (size) for else.
```blocks3
```
--- /task ---

Once last thing, note both conditional statements sit within a forever block. This block ensures that all conditions are checked - forever - throughout the game.

## Stop the tree from getting too big!
There's one more conditional statment; if then. It's a little simpler:

if the Tree sprite touches the edge of the stage > then the action is say "You did it! Stand on one leg to make it harder and click the green flag to play again." 
```blocks3
if (touching [edge v] ? ::sensing) then ::control
say [You did it! Stand on one leg to make it harder and click the green flag to play again.] for (2) seconds ::looks
```
Included in the action is 'stop this script' which stops the whole program!
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
