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

Anchors are used to match positions in the string. In our regex, the ```^``` at the beginning of the pattern specifies the start of the string, and the ```$``` at the end specifies the end of the string. Together, they ensure that the entire string matches the pattern.

#### Example:
```
Regex: /^(https?://)?([\da-z.-]+).([a-z.]{2,6})([/\w .-])/?$/
Input: "https://www.example.com"
Explanation: The regex anchors match the entire string "https://www.example.com"
because it starts with "https://" and ends with ".com".
```

### Quantifiers

Quantifiers define the number of occurrences of the preceding element. In our regex, the ```?``` after "https:" specifies that the "s" is optional, allowing for both "http" and "https" protocols. The ```+``` after ```[\da-z.-]``` specifies that the aplhanumeric, period and hyphen can occur one or more times.

#### Example:
```
Regex: https?
Input: "http://www.example.com"
Explanation: The "s" in "http" is optional(zero or one), so the regex matches "http://www.example.com".

Regex: [\da-z.-]+
Example: www.
```

### OR Operator

The OR operator ```(|)``` allows for alternative matches. To illustrate an example of an ```or``` operator, we can modify the regex to match URLs that start with either "http://" or "ftp://" and to do that we can update the regex as follows:

#### Example:
```
Regex: /^(https?|ftp)://([\da-z.-]+).([a-z.]{2,6})([/\w .-])?$/
Explanation: (https?|ftp) the "|" in this regex allows us to match the URL that either starts with http or https or ftp.
```

### Character Classes

Character classes allow matching a specific set of characters. In our regex, the character classes ```[\da-z.-]``` match any alphanumeric character, period (.), or hyphen (-).

#### Example:
```
Input: "example.com"
Explanation: The regex matches "example.com" because it consists of alphanumeric characters
and a period, which matches the character class [\da-z.-].
```

### Flags

Flags modify the behavior of the regex matching. However, in our regex, there are no flags specified.

### Grouping and Capturing

Parentheses are used for grouping and capturing portions of the regex. In our regex, there are three groups defined:

#### Example:
```
    Group 1: ([a-z0-9_.-]+) matches one or more alphanumeric characters,
underscore (_), period (.), or hyphen (-) before the @ symbol.

    Group 2: ([\da-z.-]+) matches one or more alphanumeric characters,
period (.), or hyphen (-) in the domain name.

    Group 3: ([a-z.]{2,6}) matches a domain extension consisting of
2 to 6 lowercase letters or periods.
```

### Bracket Expressions

Bracket expressions specify a range of characters that can match at a particular position.

#### Example:
```
Regex: /[aeiou]/
Input: "Hello"
Match: "e"
```
In the example above, the regex ```/[aeiou]/``` matches the letter 'e' in the word "Hello" because 'e' is one of the characters specified in the bracket expression.

### Greedy and Lazy Match

Greedy and lazy quantifiers control the matching behavior by specifying whether the match should be as long as possible (greedy) or as short as possible (lazy). In our regex, the default greedy behavior is used.

The ```*``` quantifier is greedy by default. It matches zero or more occurrences of the preceding group, which in this case is ```([\/\w .-])```. The greedy behavior means it will match as many occurrences as possible while still allowing the overall pattern to match.

#### Example
```
Regex: /^(https?:\/\/)?([\da-z.-]+)\.([a-z.]{2,6})([\/\w .-])*?\/?$/
Input: "https://www.example.com/page1/page2"
Match: "https://www.example.com/page1/page2"
```

We can modify the regex to demonstrate the lazy matching behavior.

#### Example:
```
Regex: /^(https?:\/\/)?([\da-z.-]+)\.([a-z.]{2,6})([\/\w .-])*??\/?$/
Input: "https://www.example.com/page1/page2"
Match: "https://www.example.com/"
```

The *? quantifier after ([\/\w .-]) makes it lazy. It matches zero or more occurrences of the preceding group in a lazy manner. The lazy behavior means it will match as few occurrences as possible while still allowing the overall pattern to match.

### Boundaries

Boundaries assert the position of the match at word boundaries.

#### Example: 
```
Regex: /^http$/
Input: "http"
```

The ^ symbol at the beginning and the $ symbol at the end enforces that the entire string should match the pattern "http" exactly.

If the input is "http", the regex will provide a match because it exactly matches the pattern specified by the regex. The boundaries ensure that the pattern "http" is matched from the start to the end of the string.

### Back-references

Back-references allow us to refer to previously captured groups. In our regex, back-references are not used.

### Look-ahead and Look-behind

Look-ahead and look-behind assertions match a pattern without including it in the overall match. In our regex, look-ahead and look-behind are not used.

## Author

May Myat Noe Htet
https://github.com/maymyatnoehtet
