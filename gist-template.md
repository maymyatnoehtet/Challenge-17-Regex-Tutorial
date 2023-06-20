# Regex: Matching a URL 

What is a Regex?

A regex, which is short for regular expression, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input.

For example, the following regular expression can be used to verify that user input is a valid email address:

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

Each component of this regex has a unique responsibility to make sure that a user enters an email address that begins with an unspecified number of characters preceding the @ symbol, followed by a domain.

## Summary

In this tutorial, we will explain each part of the regular expression that matches a URL. We will break down the regex components and provide examples to demonstrate their functionality.

#### Regex
```
/^(https?://)?([\da-z.-]+).([a-z.]{2,6})([/\w .-])/?$/
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

### Anchors

Anchors are used to match positions in the string. In our regex, the ^ at the beginning of the pattern specifies the start of the string, and the $ at the end specifies the end of the string. Together, they ensure that the entire string matches the pattern.

#### Example:
```
Input: "https://www.example.com"
Explanation: The regex anchors match the entire string "https://www.example.com" because it starts with "https://" and ends with ".com".
```

### Quantifiers

Quantifiers define the number of occurrences of the preceding element. In our regex, the "?" after "https:" specifies that the "s" is optional, allowing for both "http" and "https" protocols.

#### Example:
```
Input: "http://www.example.com"
Explanation: The "s" in "http" is optional, so the regex matches "http://www.example.com".
```

### OR Operator

The OR operator (|) allows for alternative matches. In our regex, it is used to match either a 6-character hex value or a 3-character hex value after the "#" symbol.

#### Example:
```
Input: "#ABC123"
Explanation: The regex matches the hex value "#ABC123" because it satisfies the condition of having either 6 or 3 characters after the "#".
```

### Character Classes

Character classes allow matching a specific set of characters. In our regex, the character classes [\da-z.-] match any alphanumeric character, period (.), or hyphen (-).

#### Example:
```
Input: "example.com"
Explanation: The regex matches "example.com" because it consists of alphanumeric characters and a period, which matches the character class [\da-z.-].
```

### Flags

Flags modify the behavior of the regex matching. In this regex, However, in our regex, there are no flags specified.

### Grouping and Capturing

Parentheses are used for grouping and capturing portions of the regex. In our regex, there are three groups defined:

#### Example:
```
    Group 1: ([a-z0-9_.-]+) matches one or more alphanumeric characters, underscore (_), period (.), or hyphen (-) before the @ symbol.

    Group 2: ([\da-z.-]+) matches one or more alphanumeric characters, period (.), or hyphen (-) in the domain name.

    Group 3: ([a-z.]{2,6}) matches a domain extension consisting of 2 to 6 lowercase letters or periods.
```
### Bracket Expressions

Bracket expressions specify a range of characters that can match at a particular position. In our regex, bracket expressions are not explicitly used.

### Greedy and Lazy Match

Greedy and lazy quantifiers control the matching behavior by specifying whether the match should be as long as possible (greedy) or as short as possible (lazy). In our regex, the default greedy behavior is used.

### Boundaries

Boundaries assert the position of the match at word boundaries. In our regex, boundaries are not explicitly used.

### Back-references

Back-references allow us to refer to previously captured groups. In our regex, back-references are not used.

### Look-ahead and Look-behind

Look-ahead and look-behind assertions match a pattern without including it in the overall match. In our regex, look-ahead and look-behind are not used.

## Author

May Myat Noe Htet
