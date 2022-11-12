# Regex-Tutorial

As a web development student, I created a tutorial explaining a specific regex to understand the search pattern the regex defines

## Summary

A regex, which is short for regular expression, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input.

For example, the following regular expression can be used to verify that user input is a valid email address:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

Anchors are symbols at the beginning and end of the string.
The opening anchor is the symbol ^.
The ending enchor is the symbol $.
^ is the anchor that matches the beginning.
$ matches the end.

### Quantifiers

Quantifiers tells the regex engine that it must match the character/expression.  
Examples of quantifiers: _ + ? and {}
abc_ matches a string that has ab followed by zero or more c -> Try it!
abc+ matches a string that has ab followed by one or more c
abc? matches a string that has ab followed by zero or one c
abc{2} matches a string that has ab followed by 2 c
abc{2,} matches a string that has ab followed by 2 or more c
abc{2,5} matches a string that has ab followed by 2 up to 5 c
a(bc)\* matches a string that has a followed by zero or more copies of the sequence bc
a(bc){2,5} matches a string that has a followed by 2 up to 5 copies of the sequence bc

### OR Operator

The symbol for OR is "|". For example:
a(b|c) matches a string that has a followed by b or c (and captures b or c)

### Character Classes

Character Classes match a sequence of characters to a set. For example:
[a-z] Matches lowercase alphabetic characters between a and z
\w Matches a word
\d Matches a single character that is a digit
. Matches any character

### Flags

A regex usually comes within this form /abc/, where the search pattern is delimited by two slash characters /. At the end we can specify a flag with these values (we can also combine them each other):
g (global) does not return after the first match, restarting the subsequent searches from the end of the previous match
m (multi-line) when enabled ^ and $ will match the start and end of a line, instead of the whole string
i (insensitive) makes the whole expression case-insensitive (for instance /aBc/i would match AbC)

### Grouping and Capturing

This extracts information from strings or data. Any multiple occurrences captured by several groups will be exposed in the form of a classical array and will access their values specifying using an index on the result of the match.
If we choose to put a name to the groups (using (?<foo>...)) we will be able to retrieve the group values using the match result like a dictionary where the keys will be the name of each group.

### Bracket Expressions

A bracket expression is located within []. For example:
[abc] matches a string that has either an a or a b or a c -> is the same as a|b|c
[a-c] same as previous
[a-fA-F0-9] a string that represents a single hexadecimal digit, case insensitively
[0-9]% a string that has a character from 0 to 9 before a % sign
[^a-za-z] a string that has not a letter from a to z or from A to Z. In this case the ^ is used as negation of the expression

### Greedy and Lazy Match

The quantifiers ( \* + {}) are greedy operators, so they expand the match as far as they can through the provided text.

### Boundaries

Boundaries establish matches at a position that is considered a "word boundary".
Boundaries are located before the first character in the string, if the first character is a word character.
After the last character in the string, if the last character is a word character.
Between two characters in the string, where one is a word character and the other is not a word character.
For example:
\babc\b performs a "whole words only" search.
\b represents an anchor like caret (it is similar to $ and ^) matching positions where one side is a word character (like \w) and the other side is not a word character (for instance it may be the beginning of the string or a space character).
It comes with its negation, \B. This matches all positions where \b doesn’t match and could be if we want to find a search pattern fully surrounded by word characters.

### Back-references

Backreferences will match the same text previously matched by a capturing group. If you wish to match a pair of opening and closing HTML tags and the text in between, you can introduce it as follows:
<([A-Z][a-z0-9]_)\b[^>]_>._?</\1>
This style of regex contains a pair of parentheses which captures the string matched by [A-Z][a-z0-9]_
The backreference \1 references the first capturing group. \1 matches the exact same text that was matched by the first capturing group. The / before it is a literal character. It is simply the forward slash in the closing HTML tag that we are trying to match.

### Look-ahead and Look-behind

This will match characters and return results: match or no match.
For example:
d(?=r) matches a d only if is followed by r, but r will not be part of the overall regex match
(?<=r)d matches a d only if is preceded by an r, but r will not be part of the overall regex match
d(?!r) matches a d only if is not followed by r, but r will not be part of the overall regex match
(?<!r)d matches a d only if is not preceded by an r, but r will not be part of the overall regex match

## Author

Madelane Sadia
My github: https://github.com/msadia27
