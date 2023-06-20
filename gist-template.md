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

```
Regex: /^(https?://)?([\da-z.-]+).([a-z.]{2,6})([/\w .-])/?$/
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

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
