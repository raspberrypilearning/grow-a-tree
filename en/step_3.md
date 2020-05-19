## Challenge: changing conditions

Currently, when the player stays still Tree sprite grows.

--- task ---

+ Try adding a single block of code to make something additional happen when the player stays still. 

+ What about some extra words of encouragement such as 'You can do it!'? Find the Say block in Looks -  it's purple!

```blocks3
if <(video [motion v] on [stage v] ::video) < (10)> then ::control 
		change size by (1) ::looks
	else 
		change size by (-1) ::looks ::control
+ say [You can do it!] for (0.5) seconds ::looks
	end
```
Run the program. Is it working well?
--- /task ---

Currently, when Tree sprite reaches the edge of the stage is stops growing.

--- task ---

+ Add a new block of code to make something interesting happen.

+ For instance, Tree sprite could produce an Apple costume when it grows big enough. Can you find the switch costume block in Looks? Again, it's purple!

```blocks3
if (touching [edge v] ? ::sensing) then ::control
			say [Stay still!] for (2) seconds ::looks
      +switch costume [Apple v] ::looks
			stop [this script v] 
	end
```
+ Run the program. Is it working ok?

+ In order for Tree sprite to show at the start of the game you will need to create a new seperate script in Tree sprite's code editor.

```blocks3
when flag clicked
switch costume [Tree v] ::looks
--- /task ---
	end
```
+ Run the program.

