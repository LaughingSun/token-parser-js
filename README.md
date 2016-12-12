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
greedy,docile     |                 | A{m}    | m times, as many as possible (greedy), backtrack if needed (docile)
greedy,docile     |                 | A{m,}   | m to n, as many as possible (greedy), backtrack if needed (docile)
greedy,docile     |                 | A{m,n}  | m to n, as many as possible (greedy), backtrack if needed (docile)
greedy,docile     |                 | A{,n}   | 0 to n, as many as possible (greedy), backtrack if needed (docile)
greedy,possessive |                 | A++     | 1 or more, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A\*+    | 0 or more, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A?+     | 0 or 1, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A{m}+   | m times, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A{m,}+  | m or more, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A{m,n}+ | m to n, as many as possible (greedy), block backtracking (possessive)
greedy,possessive |                 | A{,n}+  | 0 to n, as many as possible (greedy), block backtracking (possessive)
lazy              |                 | A+?     | 1 or more, as few as needed (lazy) 
lazy              |                 | A\*?    | 0 or more, as few as needed (lazy) 
lazy              |                 | A??     | 0 or 1, as few as needed (lazy) 
lazy              |                 | A{m}?   | m times, as few as needed (lazy) 
lazy              |                 | A{m,}?  | m or more, as few as needed (lazy) 
lazy              |                 | A{m,n}? | m to n, as few as needed (lazy) 
lazy              |                 | A{,n}?  | 0 to n, as few as needed (lazy) 
lazy,helpful      |                 | A+?     | 1 or more, as few as needed (lazy), backtrack if needed (helpful) 
lazy,helpful      |                 | A\*?    | 0 or more, as few as needed (lazy), backtrack if needed (helpful) 
lazy,helpful      |                 | A??     | 0 or 1, as few as needed (lazy), backtrack if needed (helpful) 
lazy,helpful      |                 | A{m}?   | m times, as few as needed (lazy), backtrack if needed (helpful) 
lazy,helpful      |                 | A{m,}?  | m or more, as few as needed (lazy), backtrack if needed (helpful) 
lazy,helpful      |                 | A{m,n}? | m to n, as few as needed (lazy), backtrack if needed (helpful) 
lazy,helpful      |                 | A{,n}?  | 0 to n, as few as needed (lazy), backtrack if needed (helpful) 

+ boundry types - (whitespace seperated) and (word or group boundry)



