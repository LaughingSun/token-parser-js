# token-parser-js
a configurable tokenizer and parser for generic purposes.  It was developed for use with the ECMAscript vatiant called UBUDscript.

Concepts:
+ terminal and non-terminal symbols - terminal symbols are those with a fixed pattern and length, non-terminal are otherwise.
+ symbol syntax group - symbols comprized of different character groups, which allow for word boundry determination
+ symbol syntax quantifiers - symbol recognition using greedy, docile, lazy and possessive

quantifier        | example input   | regex | description
----------------- | --------------- | ----- | -----
greedy,docile     |                 | A+    | 1 or more, as many as possible (greedy), backtrack if needed (docile)
lazy              |                 | A+?   | 1 or more, as few as needed to allow the overall pattern to match (lazy) 
greedy,possessive |                 | A++   | 1 or more, as many as possible (greedy), block backtracking (possessive)
----------------- | --------------- | ----- | -----
greedy,docile     |                 | A\*   | 0 or more, as many as possible (greedy), backtrack if needed (docile)
lazy              |                 | A\*?  | 0 or more, as few as needed to allow the overall pattern to match (lazy) 
greedy,possessive |                 | A\*+  | 0 or more, as many as possible (greedy), block backtracking (possessive)
----------------- | --------------- | ----- | -----
greedy,docile     |                 | A?   | 0 or 1, as many as possible (greedy), backtrack if needed (docile)
lazy              |                 | A??  | 0 or 1, as few as needed to allow the overall pattern to match (lazy) 
greedy,possessive |                 | A?+  | 0 or 1, as many as possible (greedy), block backtracking (possessive)
A*?	Zero or more As, as few as needed to allow the overall pattern to match (lazy)
A*+	Zero or more As, as many as possible (greedy), not giving up characters if the engine tries to backtrack (possessive)
?
zero times or once
A?	Zero or one A, one if possible (greedy), giving up the character if the engine needs to backtrack (docile)
A??	Zero or one A, zero if that still allows the overall pattern to match (lazy)
A?+	Zero or one A, one if possible (greedy), not giving the character if the engine tries to backtrack (possessive)
{x,y}
x times at least, y times at most
A{2,9}	Two to nine As, as many as possible (greedy), giving up characters if the engine needs to backtrack (docile)
A{2,9}?	Two to nine As, as few as needed to allow the overall pattern to match (lazy)
A{2,9}+	Two to nine As, as many as possible (greedy), not giving up characters if the engine tries to backtrack (possessive)
A{2,}
A{2,}?
A{2,}+	Two or more As, greedy and docile as above.
Two or more As, lazy as above.
Two or more As, possessive as above.
A{5}	Exactly five As. Fixed repetition: neither greedy nor lazy.

+ word boundry types - whitespace seperated, group seperated, or both



