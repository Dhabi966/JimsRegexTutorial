# JimsRegexTutorial

# [Gist](https://gist.github.com/Dhabi966/e43f0e3b8c72625258e44fe1c385a693)


## Summary

A RegEx (or, regular expression) is a sequence of characters that defines a search pattern that helps users match, locate, or manage text. Common use cases include matching strings of text, finding and replacing operations, and input validation. For example, with regex you can easily check a user's input for common misspellings of a particular word. The regex pattern consists of one or more character literals and/or "meta" characters, which are stand-ins to represent possible text combinations.

The RegEx we will be breaking down searches for an email address pattern within a string. Please review the following code snippet:

```

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

```

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

The RegEx we are breaking down today has three elements that we will talk about

Complete Regex for Reference: ```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/```


Element 1: Username

```([a-z0-9_\.-]+)```

* This element will check to match the username portion of the email address. It may contain any letters, any numbers, periods, underscores, or dashes.

* Example: ```mp[um@r12``` would fail due to the special characters, however```mplumer12``` would match.

  

Element 2: Domain

```([\da-z\.-]+)```

* This element will check to match the domain portion of the email address. It may contain letters, numbers and dashes.

* Example: ```domain_name``` would fail due to the underscore, however ```domain-name``` would match.

  

Element 3: Suffix

```([a-z\.]{2,6})```

* this element checks the suffix of the email address. Think ".com"/".edu". It may contain only letters, and they must be between 2 and 6 characters long.

* Example: ```.company``` would fail due to the character count, however ```.com``` would match.

For additional breakdowns of how each element in this RegEx works, please see more details explanations below.

### Anchors

Anchors encapsulate regex components to define what search pattern to find.

* Example: ``` ^xyz$ ``` where the ```^``` character indicates the start of a string, and the ```$``` character indicates the end of a string

In our example, we use two anchors. One at the beginning, and one at the end; to match the string (email address) we are searching for.


### Quantifiers

```+``` = Repeats the previous item one or more times (Greedy Match)

* Example: ```a+``` would return a positive match for all items where the ```a``` character occurs one or more times.



### OR Operator

```{a,b}``` = defines a minimum ```a``` and a maximum ```b``` number of characters.

* Example: ```{2,6}``` would return a positive match for items containing between 2 and 6 characters



### Character Classes

```.``` = Any character except newline

* When combined with the ```\``` anchor, ```\.```

```[a-z]``` = Accepts any letter between ```a``` and ```z```

```[0-9]``` = Accepts any digit between ```0``` and ```9```


### Grouping and Capturing

* Example: ```([a-z0-9_\.-]+)``` where the () group together the ```[a-z0-9_\.-]``` bracket expression with the ```+``` quantifier.

* This RegEx matches any letter or number a-z or 0 to 9, accepts underscores, periods and dashes. Then the quantifier matches one or more of the previous tokens.

  

### Bracket Expressions

Bracket expressions are the syntax theory on combining character classes. Multiple character classes may be combined in a single bracket expression.

  

* Example: [a-z0-9] where the regex would match any letter or number.

  

### Greedy and Lazy Match

```{a, }``` = Lazy match, searches number ```a``` or more

```{a,b}``` = greedy match, search BETWEEN numbers ```a``` and ```b```


## Author

If you have any questions, please reach out to me on [GitHub](https://github.com/Dhabi966)
