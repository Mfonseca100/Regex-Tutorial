# Regex Tutorial for Matching a Hex Value

Regular Expression or "Regex" for short are universal expressions that uses a series of special characters that defines a specific search pattern.

Hex Values is a numerical representation of value in the haxadecimal numbering system. Typically, using 16 unique symbols, including digits from 0-9 and letters A-F or (a-f) to represent the values 10 to 15. Commonly used to specify colors by representing the intensity of red, green, and blue components. 

## Summary

In this tuturial we will be breaking down the preceding "Matching a Hex Value" regex in order to provide an explanation for each part, clarifying its purpose and functionality.

```
/^#?([a-fA-F0-9]{3}){1,2}$/
```
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
Definition: Special characters that indicate where in a string the search should begin. 

The caret (^) anchor - asserts the beggining of the regex. When placed at the beggining it ensures the pattern must match at the start of the line. 

The dollar sign ($) anchor - asserts the end of the regex. When placed at the end it ensures the pattern must match at the end of the line.

In our expression, /^#?([a-fA-F0-9]{3}){1,2}$/, you can see the caret and the dollar sign being used; this is helpful when trying to find a specfic string in a larger body of text. 

### Quantifiers
Definition: a feature of regular expressions that specifies the number or range of repetitions of the chacter, character class, metacharacter, or subexpression directly preceding it. 

In our expression the quantifier is represented by the curly braces '{1,2}'. The quantifier is located after the group '([([a-fA-F0-9]{3})'. This indicates the group can occur 1 or 2 times. 

(#RGB) - red, green, blue.  

This allows for matching both three-chatacter groups (#RGB) and two consecutive three-character groups (#RRGGBB) in the hex color value. 


### Grouping Constructs
Definition: A way of marking a part of a regular expression pattern that can be matched, repeated, or accessed seperately. Usually written in parentheses around the subexpression that it contains. 

In our expression the grouping construct '( )' is used to group the expression '[([a-fA-F0-9]{3}' together. Allowing the quantifier '{1, 2}' to apply to the expression inside the parenthesis instead of just a single character. 

### Bracket Expressions
Definition: Brackets are special regex metacharacters, or characters which have a special meaning. Brackets tell the regex engine to look for classes of chracters contained inside of it. 

In our expression, the bracket expression '[a-fA-F0-9]'represents a character range that matches any characteristics that is either lowercase letter 'a-f', and uppercase letter 'A-F', or a digit '0-9'. 

### Character Classes
Definition: A basic regex concept that allows you to match one small sequence of characters to a larger set of characters. 

For example, in our expression '[a-fA-F0-9]' represents a set of special characters that can be matched. Including hexadecimal digits, the lowercase letters 'a-f', the uppercase letters 'A-F', and the digits '0-9'. This guarantees only hexadecimal characters are matched for the three-character group '([([a-fA-F0-9]{3})'. 

### The OR Operator
Definition: Indiciated by the vertical bar '|', speficifies alternative options for matching. It matches either the expression on the left side, or the right. 

In our expression, we do not have an OR Operator but listed an example below for better understanding. 

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

The "|" defines the string can either be [a-f0-9]{6} or [a-f0-9]{3}. 

### Flags
Definition: An optional parameter to a regex tha modifies its behavior of searching. 

In our expression, there is '?' flag after the #.(#?)

This flag states that the '#' character is optional. 


### Character Escapes
Definition: Allows you to match a specific character that has a special meaning in the regular expression syntax. such as \w for a word character or \s for space. 

## Author

Marissa Edith, student at Rice Univeristy Coding Bootcamp Program. 