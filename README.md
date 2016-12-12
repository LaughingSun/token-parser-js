# token-parser-js
a configurable tokenizer and parser for generic purposes.  It was developed for use with the ECMAscript vatiant called UBUDscript.

Concepts:
+ terminal and non-terminal symbols - terminal symbols are those with a fixed pattern and length, non-terminal are otherwise.
+ symbol syntax group - symbols comprized of different character groups, which allow for word boundry determination
+ symbol syntax quantifier - symbol recognition using greedy, docile, lazy, helpful and possessive

type        | example     | description  |
----------- | ----------- | --- |
greedy      | 127000      | take as many group points as posible |
docile      |             | take  |
lazy        |             | take  |
helpful     |             | take  |
possessive  |             | take  |

+ word boundry types - whitespace seperated, group seperated, or both



