# token-parser-js
a configurable tokenizer and parser for generic purposes.  It was developed for use with the ECMAscript vatiant called UBUDscript.

Concepts:
+ terminal and non-terminal symbols - terminal symbols are those with a fixed pattern and length, non-terminal are otherwise.
+ captures and referencing
+ jump points, groups, look behinf and ahead, and alterations
+ symbol syntax group - symbols comprized of different character groups, which allow for word boundry determination

class             | example input   | regex                 | description
----------------- | --------------- | --------------------- | -----------
character class   |                 | [a-zA-Z0-9]           | any alphanumeric point
character class   |                 | [a-zA-Z0-9-]          | any alphanumeric or a dash point
character class   |                 | [\w-]                 | any alphanumeric or a dash point
character class   |                 | [[:alpha:]]           | any alpha point
character class   |                 | [[:alpha:][:digit:]-] | any alpha, numeric or a dash point
character class   |                 | [[:alnum:]]           | any alphanumeric point
character class   |                 | [^a-zA-Z0-9]          | any except alphanumeric point
character class   |                 | [^a-zA-Z0-9-]         | any except alphanumeric or a dash point
character class   |                 | [^\w-]                | any except alphanumeric or a dash point
character class   |                 | [^[:alpha:]]          | any except alpha point
character class   |                 | [^[:alnum:]]          | any except alphanumeric point
escaped character |                 | \\*non-escape*        | any literal character except escape, anchor, boundry or special character
escaped character |                 | \\n                   | linefeed point
escaped character |                 | \\r                   | return point
escaped character |                 | \\t                   | tab point
escaped character |                 | \\v                   | formfeed point
escape class      |                 | \\D                   | any non-digit point
escape class      |                 | \\N                   | any point except linefeed
escape class      |                 | \\R                   | any point except return
escape class      |                 | \\S                   | any non-whitespace point
escape class      |                 | \\T                   | any point except tab
escape class      |                 | \\V                   | any non-vertical whitespace point
escape class      |                 | \\W                   | any non-alphanumeric point
escape class      |                 | \\d                   | any digit point
escape class      |                 | \\s                   | any whitespace point
escape class      |                 | \\w                   | any alphanumeric point
special character |                 | .                     | any characher except new line and end of line characters

+ symbol syntax quantifiers - symbol recognition using limits with greedy, docile, possessive, lazy and expective

quantifier        | example input   | regex    | description
----------------- | --------------- | -------- | -----------
greedy            |                 | A+       | 1 or more, as many as possible (greedy)
greedy            |                 | A\*      | 0 or more, as many as possible (greedy)
greedy            |                 | A?       | 0 or 1, as many as possible (greedy)
greedy            |                 | A{m}     | m times, as many as possible (greedy)
greedy            |                 | A{m,}    | m to n, as many as possible (greedy)
greedy            |                 | A{m,n}   | m to n, as many as possible (greedy)
greedy            |                 | A{,n}    | 0 to n, as many as possible (greedy)
greedy,expective  |                 | A+B      | 1 or more, as many as possible (greedy), until B (expective) 
greedy,expective  |                 | A\*B     | 0 or more, as many as possible (greedy), until B (expective) 
greedy,expective  |                 | A?B      | 0 or 1, as many as possible (greedy), until B (expective) 
greedy,expective  |                 | A{m}B    | m times, as many as possible (greedy), until B (expective) 
greedy,expective  |                 | A{m,}B   | m to n, as many as possible (greedy), until B (expective) 
greedy,expective  |                 | A{m,n}B  | m to n, as many as possible (greedy), until B (expective) 
greedy,expective  |                 | A{,n}B   | 0 to n, as many as possible (greedy), until B (expective) 
greedy,possessive |                 | A++      | 1 or more, as many as possible (greedy), no backtracking (possessive)
greedy,possessive |                 | A\*+     | 0 or more, as few as possible (greedy), no backtracking (possessive)
greedy,possessive |                 | A?+      | 0 or 1, as many as possible (greedy), no backtracking (possessive)
greedy,possessive |                 | A{m}+    | m times, as many as possible (greedy), no backtracking (possessive)
greedy,possessive |                 | A{m,}+   | m or more, as many as possible (greedy), no backtracking (possessive)
greedy,possessive |                 | A{m,n}+  | m to n, as many as possible (greedy), no backtracking (possessive)
greedy,possessive |                 | A{,n}+   | 0 to n, as many as possible (greedy), no backtracking (possessive)
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

+ anchor and boundry types, and look ahead and behind - (whitespace seperated) and (word or group boundry)

type              | example input   | regex                 | description
----------------- | --------------- | --------------------- | -----------
anchor            |                 | ^                     | at the beginning of input
anchor            |                 | $                     | at the end of input
boundry           |                 | ^                     | [multiline] at the beginning of a line (\*index) 
boundry           |                 | $                     | [multiline] at the end of a line
boundry           |                 | \A                    | not at the beginning of input
boundry           |                 | \B                    | not at a word boundry
boundry           |                 | \G                    | not at the beginning or end of input
boundry           |                 | \Z                    | not at the end of input
boundry           |                 | \a                    | at the beginning of input
boundry           |                 | \b                    | at a word boundry
boundry           |                 | \g                    | at the beginning or end of input
boundry           |                 | \z                    | at the end of input
lookahead         |                 | (?=*expression*)      | has a *expression* ahead
lookahead,negate  |                 | (?!*expression*)      | doesn't have a *expression* ahead
lookbehind        |                 | (?<=*expression*)     | has a *expression* behind
lookbehind,negate |                 | (?<!*expression*)     | doesn't have a *expression* behind

