
# Matching an Email Address Using Regex

In this tutorial, we will explore how a regular expression (regex) is used to match and validate email addresses. A regex is a sequence of characters that defines a search pattern, often used for string validation, searching, or string replacement. The regex for email validation helps ensure that the input follows the correct format for a typical email address, including a username, domain, and domain extension.
Email Regex: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Summary

The regex we’ll cover is used to match an email address format. It checks that the email starts with alphanumeric characters (including dots, dashes, or underscores), followed by an @ symbol, a valid domain, and a domain extension of two to six characters. This regex ensures that the email address adheres to a widely accepted format: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

### Anchors

Explanation:
Anchors ensure that the match occurs at specific positions in the string.

	•	^ – Ensures the match starts at the beginning of the string.
	•	$ – Ensures the match ends at the end of the string.

Example:
For an email like example@email.com, the ^ and $ ensure that the entire string is evaluated from the beginning (example) to the end (com) with no extra characters before or after.

### Quantifiers

Explanation:
Quantifiers specify how many instances of a character or group are required.

	•	+ – Ensures that one or more of the preceding character/group is present.

In our email regex, the quantifiers are used in:

	•	[a-z0-9_\.-]+: The + ensures that there is at least one or more characters for the username part.
	•	[a-z\.]{2,6}: The {2,6} quantifier ensures that the domain extension has between 2 to 6 characters (like .com or .museum).

Example:
In the email example@email.com, the + quantifier ensures that the username (example) and the domain (email) have more than one character.

### Character Classes

Explanation:
Character classes match specific sets of characters. They are defined inside square brackets [].

	•	[a-z0-9_\.-]: This class allows lowercase letters (a-z), numbers (0-9), underscores (_), dots (.), and dashes (-) for the username and domain.
	•	[\da-z\.-]: This class matches digits (\d), lowercase letters (a-z), dots (.), and dashes (-) for the domain.

Example:
In example@email.com, the example part is matched by [a-z0-9_\.-]+ allowing characters, numbers, dots, and underscores.

### Grouping and Capturing

Explanation:
Grouping and capturing allows us to segment parts of the string and reuse them or apply operations to them.

	•	([a-z0-9_\.-]+): Captures the username part of the email.
	•	([\da-z\.-]+): Captures the domain part of the email.
	•	([a-z\.]{2,6}): Captures the domain extension.

Example:
In example@email.com, example, email, and com are all captured in different groups, which can be referenced if needed.

### Bracket Expressions

Explanation:
Bracket expressions are used to define a set of characters that can be matched.

	•	[a-z0-9_\.-]: Matches any single character that is a lowercase letter, digit, underscore, dot, or dash.
	•	[a-z\.]{2,6}: Matches lowercase letters and dots for the domain extension, with a length between 2 to 6 characters.

Example:
For the email example@email.com, the characters e, x, a, m, p, l, and e are matched by [a-z0-9_\.-].

### Greedy and Lazy Match

Explanation:
By default, regex quantifiers are greedy, meaning they match as much as possible. In this regex, the + and {2,6} are greedy quantifiers, meaning they will match as many characters as allowed within their scope.

Example:
For example@email.com, the greedy quantifiers ensure that the entire username (example) and domain extension (com) are matched.

## Author

I’m Jimi L., a passionate web development student currently learning Full Stack Coding at George Washington University. I enjoy tackling coding challenges and continuously expanding my knowledge, especially in areas like JavaScript, Node.js, and web application development. You can find more of my work and projects on my GitHub profile: @JimiL555 