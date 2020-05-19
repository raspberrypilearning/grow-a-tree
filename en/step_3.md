## Challenge: changing conditions

Currently, when the player stays still the tree grows.

--- task ---

+ Try adding a new block of code to make something additional happen when you stay still. 

+ What about some extra words of encouragement? Can you find the Say block in Looks? -  it's purple!

```blocks3
if <(video [motion v] on [stage v] ::video) < (10)> then ::control 
		change size by (1) ::looks
	else 
		change size by (-1) ::looks ::control
    say [You can do it!] for (0.5) seconds ::looks
	end
```
Run the program. Is it working well?
--- /task ---

Currently, when Tree sprite reaches the edge of the stage area is stops growing.

--- task ---

+ Add a new block of code to make something interesting happen.

+ How about Tree sprite produces an Apple costume when it grows big enough? Can you find the switch costume block in Looks? -  it's purple!

```blocks3
if (touching [edge v] ? ::sensing) then ::control
			say [Stay still!] for (2) seconds ::looks
      switch costume [Apple v] ::looks
			stop [this script v] 
	end
```
+ Run the program. Is it working ok?

+ In order for Tree sprite to show a tree at the start of the game you will need to create a seperate script in Tree sprite.

```blocks3
when flag clicked
switch costume [Tree v] ::looks
--- /task ---
	end
```
+ Run the program.

