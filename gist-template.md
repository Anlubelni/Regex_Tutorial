# Regex Tutorial on ^...$

Regex refers to Regular expressions, which are extremely useful in extracting specific information from text such as the code we use, log files, documents, or even spreadsheets. The first thing you notice when using regular expressions is that everything is essentially a character, and we are creating patterns to match sequences of specific characters (strings). The following lesson and example will explore the more practical use of one regular expression so that you can start using them as quickly as possible.

## Summary

For today's tutorial we will be looking at the starting ending regex of ^...$. It is best practice to write as specific regular expressions as possible to make sure that we avoid getting false positives when matching real world text.

One way to tighten these patterns is to define what describes both the start and the end of the line we are looking for using the special hat (^) and dollar sign ($) metacharacters. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

000000000000000000000000 repeat on anchors 000000000000000


Rather than match a character, the hat and dollar sign match a position before, after, or between characters. They can be used to “anchor” the regular expression to match at a certain position. 

Let's use the first letters of the alphabet as a simple example, abc.
^a and c$

The hat (^) matches the position right before the first character in a string. Therefore applying ^a to abc will match a. ^b does not match abc at all, because the b cannot be matched right after the start of the string. 

Similarly the dollar sign ($) matches right after the last character in the string. c$ matches c in abc, while a$ does not match at all.

### Anchors
Anchors are zero-length. They do not match any characters, but rather a position. There are anchors to match at the start and end of the subject string, and anchors to match at the start and end of each line.

 Hat sign "^" and dollar sign "$"

 Rather than match a character, the hat and dollar sign match a position before, after, or between characters. They can be used to “anchor” the regular expression to match at a certain position. 


### Quantifiers
Three styles of operators, the star, the plus, and curly braces, allow you to repeat an item zero or more times, once or more, or an arbitrary number of times. It is important to understand that these quantifiers are “greedy” by default, unless you explicitly make them “lazy”.

Quantifiers are meant to indicate numbers of characters or expressions to match, so in the case of ^...$ the characters are not really being used to match as much as to identify the specific value within the ^...$.

But in a different example the characters *, +, ?, {x,}, {,y}, {x,y} are all examples that match their preceding items that may or may not be repeated.

### Grouping Constructs



0000000000000000000000000000000000000000

By placing parentheses around part of the regex, you tell the engine to treat that part as a single item when applying quantifiers or to group alternatives together. Parentheses also create capturing groups allow you to reuse the text matched by part of the regex.


By placing part of a regular expression inside round brackets or parentheses, you can group that part of the regular expression together. This allows you to apply a quantifier to the entire group or to restrict alternation to part of the regex.

Only parentheses can be used for grouping. Square brackets define a character class, and curly braces are used by a quantifier with specific limits.

### Bracket Expressions

0000000000000000000000000000000000000000000000000

Bracket expressions can be used to match a single character or collating element.

[abc], [a-c], [^abc] or [^a-c], [.abc.] [=a=]

Note the following points:
The caret character (^) only has a special meaning when included as the first character after the open bracket ([). Otherwise, it is treated as a normal character.
The hyphen character (-) is treated as a normal character only under either of the following conditions:
The hyphen character is the first or last character within the square brackets, for example, [ab-] or [-xy].
The hyphen character is the only (both first and last) character; that is, [-].
To match a closing square bracket within a bracketed expression, the closing bracket must be the first character within the enclosing brackets; for example, [][xy] matches ], [, x, and y.
Other metacharacters are treated as normal characters within square brackets, and do not need to be escaped; for example, [ca$] will match c, a, or $.
### Character Classes

000000000000000000000000000000000000000000000000

A character class or character set matches a single character out of several possible characters, consisting of individual characters and/or ranges of characters. A negated character class matches a single character not in the character class.


With a “character class”, also called “character set”, you can tell the regex engine to match only one out of several characters. Simply place the characters you want to match between square brackets. If you want to match an a or an e, use [ae]. You could use this in gr[ae]y to match either gray or grey. Very useful if you do not know whether the document you are searching through is written in American or British English.

A character class matches only a single character. gr[ae]y does not match graay, graey or any such thing. The order of the characters inside a character class does not matter. The results are identical.

You can use a hyphen inside a character class to specify a range of characters. [0-9] matches a single digit between 0 and 9. You can use more than one range. [0-9a-fA-F] matches a single hexadecimal digit, case insensitively. You can combine ranges and single characters. [0-9a-fxA-FX] matches a hexadecimal digit or the letter X. Again, the order of the characters and the ranges does not matter.

Character classes are one of the most commonly used features of regular expressions. You can find a word, even if it is misspelled, such as sep[ae]r[ae]te or li[cs]en[cs]e. You can find an identifier in a programming language with [A-Za-z_][A-Za-z_0-9]*. You can find a C-style hexadecimal number with 0[xX][A-Fa-f0-9]+.
### The OR Operator

0000000000000000000000000000000000000000

Grouping and alternation are core features of every modern regular expression library. You can provide as many terms as desired, as long as they are separated with the pipe character: |. This character separates terms contained within each (...) group. 

### Flags
Regular expressions have optional flags that allow for functionality like global searching and case-insensitive searching. These flags can be used separately or together in any order, and are included as part of the regular expression.

Global pattern flags 

g modifier: global. All matches (don't return after first match)
m modifier: multi line. Causes ^ and $ to match the begin/end of each line (not only begin/end of string)


### Character Escapes

0000000000000000000000000000000000000000000000

https://blog.robertelder.org/regular-expression-character-escaping/



## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
