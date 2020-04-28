# When present, recap will cover some of the takeaways I've gathered through the course of the day


## Code Notes:

  * [Reverse](https://gist.github.com/Daniel-N-Huss/0a92d7a825b95312f8a47f40c4b96777) - When iterating through arrays, a 
  `< .length` works because it will always implicitly accomodate the 0 index. Reverse loops must account for the 0 index with a `>= 0`, and `.length - 1 ` as on line 5.

  * [Lunch](https://gist.github.com/Daniel-N-Huss/51a7f9775732a23bbbdfb83fe4419fc2) - Recall Jeremy's coaching on `if (hungry) {` - My code originally tested with `=== true`; but we're being passed a boolean from the argument. Reduce reduce reduce - what is my code breaking down into when you consider the pieces used. 
    * Line 19 - `availableTime < 30` originally also included `&& > 20`; In this context unneeded because that's already tested on line 18. Again, breaking down into what is the code doing. 


`process.argv` is a thing. :)  
