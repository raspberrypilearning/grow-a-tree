## How still can you be?

If you have a Scratch account you can make a copy by clicking **Remix**.

You should see you! And a teeny tiny tree in the bottom centre of the screen. Remember, stay as still as possible and the tree will grow.

Click the green flag to play and follow the instructions embedded in the game.

<div>
<iframe src="https://scratch.mit.edu/projects/396479175/embed" allowtransparency="true" width="485" height="402" frameborder="0" scrolling="no" allowfullscreen></iframe>
</div>

## Set the screen

First we have to set the scene by choosing the background and the tree. We then have to 'plant' the tree (i.e. choose where it goes on the stage) and then we have to steer the player with opening instructions.

--- task ---

+ Open the code editor. The tree is currently planted at x: 0 and y: -160. Feel free to plant it in a different position. 
```blocks3
```
+ The tree is scaled to 10% of the size of the original tree image. You can alter % for a bigger or smaller starting size.

```blocks3
```
+ Next we need to let the player know how to play the game! The instructions currently day "Keep still to grow the tree. Top tip - it helps to lean on your hands." That's a bit dull, eh? - can you jazz up the instructions a bit?

```blocks3
```
--- /task ---

## Build the camera detector

Currently the camera is set to pick up any motion on the stage.

We have a conditional statement; if then, else.
if a condition is met do the stated action, else do the other stated action.

It's even simpler to say:
if a condition is met > then action
else other action

In the program the conditional statement is:
if (the player) moves less than 10 > then change the image size of the tree by 1.
else the tree shrinks by -1! (that's the player's punishment for moving too much!).

--- task ---
+ Have a go at changing the values for the player's movement.
```blocks3
```
+ Now have a go at changing the images value (size) for then and else.
```blocks3
```
--- /task ---

Does it feel that the game more reactive if the tree's values are greater?

Once last thing, both conditional statements have to sit  within a Control Block, forever which ensures that the conditions are checked...forever during the game.

## Stop the tree from getting too big!
There's one more simpler conditional statment; if then. 

if the tree touches the edge of the stage > then say "You did it! Stand on one leg to make it harder and click the green flag to play again." 

Included in the action is 'stop this script' which stops eveything!

Importantly 'stop this script' stops the tree from growing. If the tree grew too big it would fill the screen and the game would never end. And we all need to go home sometime today!

'stop this script' also stops the forever block from checking those conditions. It can now relax.

--- task ---
+ Test the conditional statement; if then by dragging the set of blocks away from the main scripts. Run the program again. 

+ Does that tree just keep on growing? Hmmm, nice but remember we need to go home!

+ Put the blocks back again and re-run the program. Finger's crossed no blocks have gone astray. It should look like this:
```blocks3
```
--- /task ---
