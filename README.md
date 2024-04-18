# Regex-Tutorial

This regex tutorial will dive into quantifiers. Quantifiers are fundamental components of regular expressions (regex) that enable you to specify the number of occurrences of a character, group, or character class within a pattern. They provide a concise and flexible way to describe repetitive patterns in text data without having to explicitly list each repetition. They are indispensable tools for tasks such as data validation, text extraction, and pattern matching in various domains including text processing, data manipulation, and web development.

## Summary

Commonly used quantifiers:

- *: Matches zero or more occurrences of the preceding element.
- +: Matches one or more occurrences of the preceding element.
- ?: Matches zero or one occurrence of the preceding element (makes it optional).
- {n}: Matches exactly n occurrences of the preceding element.
- {n,}: Matches n or more occurrences of the preceding element.
- {n,m}: Matches between n and m occurrences of the preceding element (inclusive).

The following regex code-snippet matches a number between 1000 and 9999.

\b[1-9][0-9]{3}\b

## Table of Contents

- [Practical Examples](#Practical-Examples)
- [Laziness Instead of Greediness](#Laziness-Instead-of-Greediness)
- [Assigned User Story](#Assigned-User-Story)
- [Acceptance Criteria](#Acceptance-Criteria)
- [Author](#Author)
- [Credit/Sources](#Credit/Sources)

## Practical Examples

Quantifiers are extremely useful in scenarios where you need to match repetitive patterns in text data, such as:

- Matching email addresses with varying lengths of username and domain.
- Extracting phone numbers with different formats and lengths.
- Parsing log files for repeated patterns like timestamps or error codes.

## Laziness Instead of Greediness
The quick fix to this problem is to make the plus lazy instead of greedy. Lazy quantifiers are sometimes also called “ungreedy” or “reluctant”. You can do that by putting a question mark after the plus in the regex. You can do the same with the star, the curly braces and the question mark itself. So our example becomes <.+?>. Let’s have another look inside the regex engine.

Again, < matches the first < in the string. The next token is the dot, this time repeated by a lazy plus. This tells the regex engine to repeat the dot as few times as possible. The minimum is one. So the engine matches the dot with E. The requirement has been met, and the engine continues with > and M. This fails. Again, the engine will backtrack. But this time, the backtracking will force the lazy plus to expand rather than reduce its reach. So the match of .+ is expanded to EM, and the engine tries again to continue with >. Now, > is matched successfully. The last token in the regex has been matched. The engine reports that <EM> has been successfully matched. That’s more like it.

## Assigned User Story:

```
AS A web development student
I WANT a tutorial explaining a specific regex
SO THAT I can understand the search pattern the regex defines
```

## Acceptance Criteria:

```
GIVEN a regex tutorial
WHEN I open the tutorial
THEN I see a descriptive title and introductory paragraph explaining the purpose of the tutorial, a summary describing the regex featured in the tutorial, a table of contents linking to different sections that break down each component of the regex and explain what it does, and a section about the author with a link to the author’s GitHub profile
WHEN I click on the links in the table of contents
THEN I am taken to the corresponding sections of the tutorial
WHEN I read through each section of the tutorial
THEN I find a detailed explanation of what a specific component of the regex does
WHEN I reach the end of the tutorial
THEN I find a section about the author and a link to the author’s GitHub profile
```

## Author

My Github Account: https://github.com/anplace

Github Repo: https://github.com/anplace/Regex-Tutorial

## Credit/Sources

Regular-Expressions: https://www.regular-expressions.info/repeat.html
