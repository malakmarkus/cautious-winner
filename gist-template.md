# Match an Email - Regex Tutorial 

This tutorial is going to explain the use of regex to match emails using the expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`. This can be useful when validating emails using applications/technologies such as Node (Inqurier) or MongoDB.

## Summary

A regular expression is a sequence of characters that defines a search pattern. This is commonly used to find patterns within a string, find/replace characters within a string or validate input. This tutortial will go walk through the components of a regex and how it applies to matching an email. 

## Table of Contents

- [Match an Email - Regex Tutorial](#match-an-email---regex-tutorial)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
    - [Anchors](#anchors)
    - [Quantifiers](#quantifiers)
    - [Character Classes](#character-classes)
    - [Grouping and Capturing](#grouping-and-capturing)
    - [Bracket Expressions](#bracket-expressions)
    - [Greedy and Lazy Match](#greedy-and-lazy-match)
  - [Author](#author)

## Regex Components

### Anchors
The anchors used in this regex expression for matching an email are `^ `, which indicates the beginning of the string and `$`to indicate the ending of the string. `(m)`, or multiline is not enabled, so the regex will end at `$`.

### Quantifiers
Quantifiers are characters that specifies how often the characters before the quantifier can can occur. "?" the characters before this symbol can occur zero or one time. "*" the characters before this symbol can occur zero or more times. "+" the characters before this symbol can occur one or more times. "{min,max}" says that the characters before this symbol must occur a minimum number of times but not more than the max number of times. In the expression /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/, The "+" quantifier means that the characters before the "+" can be one and repeated more times. The {2,6} quantifier means that the items in the bracket must iterate at least twice to generate 2 characters and no more than 6 iterations to generate 6 characters.

### Character Classes
The character class in this expression is `\d`, which matches a single characters that is a digit from 0-9. It will only match a single digit such as "4", but not "44". 

### Grouping and Capturing
Capturing group #1 in this expression is `([a-z0-9_\.-]+)` that matches the user email name. The second capturing group is `([\da-z\.-]+)` which will match the email service. Then lastly, capture group #3 is `([a-z\.]{2,6})` to capture the `.com`.

### Bracket Expressions
There are three within our code:

[a-z0-9_.-], [\da-z.-], and [a-z.]

A bracket expression represents a single character. The character can be anything specified within the brackets. So, for example, in [a-z0-9_.-], this character will be matched by any lowercase letters from a-z, any digit from 0-9, or a period.

Combined with the quantifier +, this piece of code means that any number of characters matching those specified within the brackets will match.

### Greedy and Lazy Match
This regrex includes greedy matches. Since it includes the `+` Quantifier, it will match as many times as possible giving back as needed. Another greedy Quantifier used in this regex is `{}` when matching `{2,6} for the last capture group.

## Author
Malak Markus
