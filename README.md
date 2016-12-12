# token-parser-js
a configurable tokenizer and parser for generic purposes.  It was developed for use with the ECMAscript vatiant called UBUDscript.

Concepts:
+ terminal and non-terminal symbols - terminal symbols are those with a fixed pattern and length, non-terminal are otherwise.
+ symbol syntax group - symbols comprized of different character groups, which allow for word boundry determination
+ symbol syntax quantifiers - symbol recognition using limits with greedy, docile, possessive, lazy and expective

quantifier        | example input   | regex    | description
----------------- | --------------- | -------- | -----------
greedy,docile     |                 | A+       | 1 or more, as many as possible (greedy), backtrack if needed (docile)
greedy,docile     |                 | A\*      | 0 or more, as many as possible (greedy), backtrack if needed (docile)
greedy,docile     |                 | A?       | 0 or 1, as many as possible (greedy), backtrack if needed (docile)
greedy,docile     |                 | A{m}     | m times, as many as possible (greedy), backtrack if needed (docile)
greedy,docile     |                 | A{m,}    | m to n, as many as possible (greedy), backtrack if needed (docile)
greedy,docile     |                 | A{m,n}   | m to n, as many as possible (greedy), backtrack if needed (docile)
greedy,docile     |                 | A{,n}    | 0 to n, as many as possible (greedy), backtrack if needed (docile)
greedy,possessive |                 | A++      | 1 or more, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A\*+     | 0 or more, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A?+      | 0 or 1, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A{m}+    | m times, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A{m,}+   | m or more, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A{m,n}+  | m to n, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A{,n}+   | 0 to n, as many as possible (greedy), block backtracking (possessive)
lazy              |                 | A+?      | 1 or more, as few as possible (lazy) 
lazy              |                 | A\*?     | 0 or more, as few as possible (lazy) 
lazy              |                 | A??      | 0 or 1, as few as possible (lazy) 
lazy              |                 | A{m}?    | m times, as few as possible (lazy) 
lazy              |                 | A{m,}?   | m or more, as few as possible (lazy) 
lazy              |                 | A{m,n}?  | m to n, as few as possible (lazy) 
lazy              |                 | A{,n}?   | 0 to n, as few as possible (lazy) 
lazy,expective    |                 | A+?B     | 1 or more, as few as needed (lazy), until B (expective) 
lazy,expective    |                 | A\*?B    | 0 or more, as few as needed (lazy), until B (expective) 
lazy,expective    |                 | A??B     | 0 or 1, as few as needed (lazy), until B (expective) 
lazy,expective    |                 | A{m}?B   | m times, as few as needed (lazy), until B (expective) 
lazy,expective    |                 | A{m,}?B  | m or more, as few as needed (lazy), until B (expective) 
lazy,expective    |                 | A{m,n}?B | m to n, as few as needed (lazy), until B (expective) 
lazy,expective    |                 | A{,n}?B  | 0 to n, as few as needed (lazy), until B (expective) 

+ boundry types - (whitespace seperated) and (word or group boundry)



