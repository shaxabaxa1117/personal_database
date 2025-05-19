День : 2024-04-01 
Время : 16-19

Status : #Programming 


# Layout example




![[Pasted image 20240401162037.png | 500]]
**Widget**: Parent, what are my limitations?

**Parent**: You should be between 90 and 300 pixels wide and 30 to 85 pixels high.

**Widget**: Hmm, since I want to have 5 pixels of indentation, then my children can have no more than 290 pixels of width and 75 pixels of height.

**Widget**: The first child, you should be from 0 to 290 pixels wide and from 0 to 75 pixels high.

**First child**: OK, then I want to be 290 pixels wide and 20 pixels high.

**Widget**: Hmm, since I want to place my second child below the first one, this leaves only 55 pixels of height for my second child.

**Widget:** Hey, second child, you should be from 0 to 290 wide and from 0 to 55 high.

**Second child:** OK, I want to be 140 pixels wide and 30 pixels high.

**Widget**: Very good. I will place my first child at x:5 and y:5, and the second child at x:80 and y:25.

**Widget:** Parent, I have decided that my size will be 300 pixels wide and 60 pixels high.

---
# References
[[Flutter layout]]