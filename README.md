# token-parser-js
a configurable tokenizer and parser for generic purposes.  It was developed for use with the ECMAscript vatiant called UBUDscript.

Concepts:
+ terminal and non-terminal symbols - terminal symbols are those with a fixed pattern and length, non-terminal are otherwise.
+ symbol syntax group - symbols comprized of different character groups, which allow for word boundry determination
+ symbol syntax quantifiers - symbol recognition using limits with greedy, docile, possessive, lazy and helpful

quantifier        | example input   | regex   | description
----------------- | --------------- | ------- | -----
greedy,docile     |                 | A+      | 1 or more, as many as possible (greedy), backtrack if needed (docile)
greedy,docile     |                 | A\*     | 0 or more, as many as possible (greedy), backtrack if needed (docile)
greedy,docile     |                 | A?      | 0 or 1, as many as possible (greedy), backtrack if needed (docile)
greedy,docile     |                 | A{x}    | x times, as many as possible (greedy), backtrack if needed (docile)
greedy,docile     |                 | A{x,}   | x to y, as many as possible (greedy), backtrack if needed (docile)
greedy,docile     |                 | A{x,y}  | x to y, as many as possible (greedy), backtrack if needed (docile)
greedy,docile     |                 | A{,y}   | 0 to y, as many as possible (greedy), backtrack if needed (docile)
greedy,possessive |                 | A++     | 1 or more, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A\*+    | 0 or more, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A?+     | 0 or 1, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A{x}+   | x times, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A{x,}+  | x or more, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A{x,y}+ | x to y, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A{,y}+  | 0 to y, as many as possible (greedy), block backtracking (possessive)
lazy              |                 | A+?     | 1 or more, as few as needed (lazy) 
lazy              |                 | A\*?    | 0 or more, as few as needed (lazy) 
lazy              |                 | A??     | 0 or 1, as few as needed (lazy) 
lazy              |                 | A{x}?   | x times, as few as needed (lazy) 
lazy              |                 | A{x,}?  | x or more, as few as needed (lazy) 
lazy              |                 | A{x,y}? | x to y, as few as needed (lazy) 
lazy              |                 | A{,y}?  | 0 to y, as few as needed (lazy) 
lazy,helpful      |                 | A+?     | 1 or more, as few as needed (lazy), backtrack if needed (helpful) 
lazy,helpful      |                 | A\*?    | 0 or more, as few as needed (lazy), backtrack if needed (helpful) 
lazy,helpful      |                 | A??     | 0 or 1, as few as needed (lazy), backtrack if needed (helpful) 
lazy,helpful      |                 | A{x}?   | x times, as few as needed (lazy), backtrack if needed (helpful) 
lazy,helpful      |                 | A{x,}?  | x or more, as few as needed (lazy), backtrack if needed (helpful) 
lazy,helpful      |                 | A{x,y}? | x to y, as few as needed (lazy), backtrack if needed (helpful) 
lazy,helpful      |                 | A{,y}?  | 0 to y, as few as needed (lazy), backtrack if needed (helpful) 

+ boundry types - (whitespace seperated) and (word or group boundry)



