# Reading about Regex

This tutorial on Regex, short for Regular Expression, is designed to help you understand and define the sequence of special characters to verify a search term. A regex is a series of characters that defines a specific pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace characters within a string. These are often used to validate input data.

## Summary

In this tutorial, we will take a look at a very common regex used in javascript and in modern computing. Here we will study how the regex work and the different parts of the make it function properly.

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

### Anchors

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

The first component that we will be breaking down are the anchors. As shown in the highlighted portion of our regular expression, the components that are highlighted are what we call anchors. Anchors are used at the start and end of a string or expression. In this case /^ and $/ signify the beginning or end of our expression.

### Quantifiers

Similar to the anchors and boundaries but used in a different way, quanitifiers allow the user to use quanitities as a way to find patterns. For example if one wants to have a certain character to string to appear in a certain pattern, quantifiers can be used. For more visual example:

`character\{m\}` = three characters get printed out
`character\{m,n\}` = the pattern starts at m and increases until it reaches n

There are many more types of quantifiers.

### Grouping Constructs

Grouping and capturing is done with ( ) in regex.

Anything within a set of parentheses is taken as a single group, which allows all the information inside to be treated as a single unit.

Look at this expression, paying special attention to the parentheses.

/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

Between /^ and $/, there are three distinct character groups, ([a-z0-9_.-]+), ([\da-z.-]+), and ([a-z.]{2,6}).

If we remove the internal logic, the regex can be expressed this way: (1)@(2).(3). This is much easier to read, and corresponds to what we know about email addresses, which always follow the (string)@(website).(com/edu/etc) template.

### Bracket Expressions

The final piece necessary to our Regex is bracket expressions. There are three within our code:

[a-z0-9_.-], [\da-z.-], and [a-z.]

A bracket expression represents a single character. The character can be anything specified within the brackets. So, for example, in [a-z0-9_.-], this character will be matched by any lowercase letters from a-z, any digit from 0-9, or a period.

Combined with the quantifier +, this piece of code means that any number of characters matching those specified within the brackets will match.

### Character Classes

Regex has special character classes that match types of characters.

In our expression, \d is used to match any digit character.

The backslash is necessary in order to differentiate the digit class from a plain letter d.

Although we only have one character class in the expression, the behavior-changing function of a backslash is helpful in understanding another frequently used part of the expression, ".".

Unlike the other character classes, \d, \w (matching a word character) and \s (matching a whitespace character), the character class ".", which matches any character, does not require a backslash.

Because of the unique behavior of ".", the backslash must be used to negate its use as a character class and interpret it as the character ".".

### The OR Operator

| and []

x(y|z) matches a string that has x followed by y or z; captures y and z, this will be explained later xy or xz but not xyz

x[yz] same as above but it does not capture y or z xy or xz but not xyz

### Flags

g m and i

Flags are added after the search pattern as been delimited by two slash characters / g - global

/xyz/g for example will continue to search after the first match, starting from the end of the previous match

m - multiline; is combined with ^ and & to match the start and end of a line respectively, not the whole string

i - insensitive; makes an expression case-insistive

/xyz/i would match XYZ where as /xyz/ would only match xyz

### Character Escapes

In Javascript and computation in general, an escape character is a character that invokes an alternative interpretation on the following characters in a character sequence. What  this means is a character that is attached to following sequence of characters, the sequence can be seen in a different way. An escape character is a particular case of metacharacters. Generally, the judgement of whether something is an escape character or not depends on the context of the code that follows it.

In regex, the "\" character is the expression that denotes a specific character is a escaped character. For example:

`\d` => matches any digit
`\D` => matches any non-digit
`\f` => matches a form feed


## Author

Kieran Flynn
[Github](https://github.com/kieranmichaelflynn)
