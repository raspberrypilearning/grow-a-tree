## Challenge: changing conditions

Currently, when the player stays still the Tree sprite grows.

--- task ---

+ Try adding a single block of code to make something additional happen when the player stays still. 

+ What about some extra words of encouragement such as "You can do it!"? Go to `Looks`{:class="block3looks"} and find the `say`{:class="block3looks"} -  it's purple!

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

Currently, when the Tree sprite reaches the edge of the stage is stops growing.

--- task ---

+ Add a new block of code to make something interesting happen.

+ For instance, the Tree sprite could produce an Apple costume when it grows big enough. Can you find the `switch costume`{:class="block3looks"} block in Looks? Again, it's purple!

```blocks3
if (touching [edge v] ? ::sensing) then ::control
			say [Stay still!] for (2) seconds ::looks
+ switch costume [Apple v] ::looks
			stop [this script v] 
	end
```
+ Run the program. Is it working ok?

+ You will need to create a new separate script in the Tree sprite's code editor so the program `switch costume`{:class="block3looks"} back to the Tree sprite at the start of the game. 

+ Run the program.
```blocks3
when flag clicked
switch costume [Tree v] ::looks
```
--- /task ---



