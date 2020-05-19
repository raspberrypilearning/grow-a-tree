## 'Challenge: if then'

Currently, when the player stays still the tree grows.
--- task ---
Try adding a new block of code to make something additional happens when you stay still. 

What about some words of encouragment?
```blocks3
+if <(video [motion v] on [stage v] ::video) < (10)> then ::control 
		change size by (1) ::looks
	else 
		change size by (-1) ::looks ::control
+say [Stay still!.] for (0.5) seconds ::looks
	end
```
--- /task ---

Currently, when the Tree sprite reaches the edge of the stage area is stops growing.

--- task ---
+ Add a new block of code to make something more interesting happen.

How about the tree produces an apple?
```blocks3
+if (touching [edge v] ? ::sensing) then ::control
			say [You did it! Stand on one leg to make it harder and click the green flag to play again.] for (2) seconds ::looks
+switch costume [Apple v] ::looks
			stop [this script v] 
	end
```
Can you find this Looks block -  it's purple!
--- /task ---


