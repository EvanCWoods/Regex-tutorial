# Regex Tutorial

This is a comprehensive guide for those looking to learn Regex, or have a cheat sheet that they can refer to when using it.

## Summary

A regular expression is a sequence of characters that specifies a search pattern in text. Usually such patterns are used by string-searching algorithms for "find" or "find and replace" operations on strings, or for input validation.

The following is an exasmple of a regular expression that mathces an HTML tag:
```
/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/
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
- [Author](#author)


### Anchors

In regular expressions, we use anchors to check if the matching symbol is the starting symbol or ending symbol of the input string. Anchors are of two types: The first type is the caret ^ that checks if the matching character is the first character of the input and the second type is the dollar sign $ which checks if a matching character is the last character of the input string.

In the example above, the string should start with < to signify the opening of an HTML tag, ```^<```.

The end of the example above is checked using the `$`, and checks that the preceding character is correct, `>$`


### Quantifiers

Quantifiers stipulates how many instances of a character, group, or character class must be present in the line for a match to be identified.

* At a default, regex is greedy. It will match as many instances in a line as possible and the greedy part is essential in the match.

* When lazy, regex will match as few instances as possible. This can be zero or more; for example if the next part of the current regex search matches, then the lazy part isn't essential.

* Possessive regex will take a character it matches, and the character cannot be matched in the next part of the search.

Generally speaking, a quantifier tells the regex engine to match a specified quantity of the character, token or sub-expression immediately to its left. For instance:

* `[a-z]+` => the `+` applies to the character selected in the `[]`
* `[.*]` => the `*` applies to the `.`
* given the statement `test?` => the `?` applies to `t`, or the last character.


### Grouping Constructs

By placing part of a regular expression inside round brackets or parentheses, you can group that part of the regular expression together. This allows you to apply a quantifier to the entire group or to restrict alternation to part of the regex.

An example of grouping in the above regex is `([a-z]+)` which specifies that a character of a through z should be selected and concatenated with the rest of the Regex.


### Bracket Expressions

A bracket expression is either a matching list expression or a non-matching list expression. It consists of one or more expressions, and essentially checks if a given input is defined within the expressions parameters.

so, for example, if the expression was 
`(a{2,4})`, then it is expecting to get an input of at something containing at least 2 a's and no more than 4 a's.

### Character Classes

Similar to the above, a character class matches any one of the enclosed characters. You can specify a range of characters by using a hyphen, but if the hyphen appears as the first or last character enclosed in the square brackets it is taken as a literal hyphen to be included in the character class as a normal character.

In our example, the character class is 
```
[a-z]
```

which selects any character between a and z.

### The OR Operator

Similar to OR operators in other languages the OR operator in regex works by selecting either one value or another. For example:

```
[C|F]+ar 
```

will match to either Car or Far.

In our example, the or operator is: 

```
(?:>(.*)<\/\1>|\s+\/>)
```

which searches for either: 
```
?:>(.*)<\/\1>
``` 
OR 
```
\s+\/>
```


### flags

Flags are also called modifiers because they modify the output of a regular expression. These flags can be used in any order or combination, and are an integral part of the RegExp.

* `i` => case insensitive
* `g` => Global search (match all instances)
* `m` => Multiline (anchor meta characters work on each line)


### author
My name is Evan Woods, and have been programming for over 2 years. I am currently in the final stages of completing the "Full Stack Flex" voding bootcamp from The University of Sydney, and upon completion will be starting my new role as a software engineer at Insight Enterprises Australia.

To learn more about me check out my [GitHub](https://github.com/EvanCWoods) or [Portflio](https://evan-woods-updated-portfolio.herokuapp.com/):
