# Regex - Matching a URL

This gist will be explaining in detail how a the regular expression of "Matching a URL" is used.

## Summary

We will be evaluating the following regular expressions used to match a URL:

```/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/```


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping and Capturing](#grouping-and-capturing)
- [Character Classes](#character-classes)
- [Bracket Expressions](#bracket-expressions)

## Regex Components

### Anchors

```Anchors belong to the family of regex tokens that don't match any characters, but that assert something about the string or the matching process. Anchors assert that the engine's current position in the string matches a well-determined location: for instance, the beginning of the string, or the end of a line.```

In this regex example : 
`^` is the front anchor which appears in the code snippet `/^`
`$` is the back anchor which appears in the code snippet `$/`

### Quantifiers

```Quantifiers match a number of instances of a character, group, or character class in a string.```

Our regex has **FOUR** types of Quantifiers:

`{n, m}` matches a character or character class from n to m times.
{2,6} in our regex is allowing `[a-z\.]` to have 2 to 6 characters in length.

`+` is basically {1, }. It will search from the first index to last inside its capture.
`+` in our regex allowing `[\da-z\.-]` to have any amount of characters from 1 to unlimited.

`?` means zero or one. It is the same as {0,1}.
`https?`, `(https?:\/\/)?`, and `/?` our regex is using the ? quantifier to allow the text match zero or one time. (text will either be there or not be there)

`*` means zero or more. It is the same as {0, }.  
`[\/\w \.-]* and ([\/\w \.-]*)*` our regex is using the `*` quantifier to allow the text to match zero or more times. (zero to unlimited)

### Grouping and Capturing

A regex may have multiple capture groups. Capturing groups are a way to treat multiple characters as a single unit. They are created by placing the characters to be grouped inside a set of parentheses.

Our regex has FOUR capture groups:  
- (https?:\/\/)  
- ([\da-z\.-]+)  
- ([a-z\.]{2,6})  
- ([\/\w \.-]*)

### Character Classes

With a “character class”, also called “character set”, you can tell the regex engine to match only one out of several characters. Simply place the characters you want to match between square brackets.

Our regex has **THREE** of these:  
`\d` matches any digit thats quivalent to [0-9]. (Phone numbers especially use these)  
`\da-z\` in our regex is allowing the input to match any character from a-z AND using the `\d` Character Class to match any numerical digit 0-9.

`\w` matches any alphanumeric character from the alphabet as well as underscores
`\w` in our regex is using a character class to match any characters in the alphabet that follow after the webistes domain.

The `.` can match any single character except line terminators like: `\n`, `\r`  
Inside a character class, the dot loses its special meaning and matches a actual dot.
In our regex  `[\da-z\.-]` and `[\/\w \.-]` are matching any characters inside its scope.
In our regex `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`, the `.` in `\.` is being used as a actual dot.

### Bracket Expressions

A bracket expression (an expression enclosed in square brackets, "[ ]" ) is an RE that shall match a specific set of single characters, and may match a specific set of multi-character collating elements, based on the non-empty set of list expressions contained in the bracket expression.

Our regex expression has **THREE** bracket expressions:  
 `[\da-z\.-]`, `[a-z\.]` and `[\/\w \.-]` all indicating a set of characters to match.

## Author
Hello my name [Ian Gurgoze](https://github.com/igurgoze), I am an up and coming Web Developer at the University of Arizona Coding Bootcamp. This is my first gist and regex  tutorial, hope it was helpful!
