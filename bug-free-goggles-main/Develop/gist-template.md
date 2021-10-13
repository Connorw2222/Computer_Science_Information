# What is Regular Expression or Regex

Regular expression, or Regex, is a sequence of characters that specifies a specific search pattern. It can be used to find specific information out of a data set even if it is done in different formats. For example, if there is an input field for phone numbers one person could input the data as 222-222-2222 and another person could input it as 2222222222 both are technically valid but finding the data could be challenge. Regex could find both with one expression that would only take up a few lines. Regex was created with the idea that language could be sorted in a few regular expressions that would make inputting data easier. 

## Summary

Regex can be incredibly useful and looks like a series of letters and symbols that specify specific search criteria. An example of a fairly simple regex expression looks like ^[a-z0-9_-]{3,16}$. This expression specifies a username with all lower case letters (the a-z), number (the 0-9), underscore or hyphen (the _-) and has to be between 3 and 16 characters ( the {3,16}). I will be going over Anchors, Quantifiers, OR Operator, Character Classes, Flags, Grouping and Capturing, Bracket Expressions, Greedy and Lazy Match, Boundaries, Back-references, and Look-ahead and Look-behind.

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
^123$ - the ^ starts while the $ ends the string

* ^ this symbole matches the begining of the string. It matches a postion and not a specific character.
* $ this symbole matches the end of a string. This agian only matches a position and not a character
* The expression ^123$ would match a 1 or 2 or 3 so long as they were on their own line
\b\B - word, not-word boundary
* \b This matches a word boundary postion between a word character and non-word character or position(start / end of string)
* \B This matches any postion that is not a word boundary 
### Quantifiers
Quantifers indidcate that a preceding pharse or token must match a cerian number of times, quantifiers can be either greedy or lazy. 
* 1*1+1? 
    * The * mathces 0 or more preceding tokens
    * The + matches 1 or more preceding tokens
    * The ? matches 0 or 1 of the preceding tokens
* 1{2}1{7,}
    * This phrase looks for the number 1 exactly 2 times (1{2})
    * This phrase also looks for the number 1 seven or more times (1{7,})
* {2,8}
    * This matches an input between 2 and 8 characters
* 1+?1{2,}
    * this pharse matches the number 1 as few times as possible
### OR Operator
The | acts as boolean operator OR. This will match a one pharse or another 
* 12|89
    * This will match the number 12 or the number 89
### Character Classes
Character classes match a character to a specfic set. There are frequently used character sets that are predfined but regex also gives the option to to create your own character sets!

* [abc] characters inside brakets will match any charcters in the set in this case its a lower abc.
* [^abc] This will match any character not defined by this set
* [a-z] The dash creates a range in this case it is all lower case letters
* . The period will match any character except line breaks
* \w this will match any character that is not a word so any alphanumeric and underscore
* \W matches any characterthat is not a word character 
* \d mathces any digits so any number
* \p matches a character is the spcifdied unicode category
### Flags
Flags are letters added to the end of expression that change how it is interpreted. They follow the end of the expression with a forward slash \ .
i 
* ingores a case
g
* does a golbal search and retains the index of the last match, This allows a search to continue from the end of the previous search. 
m
* does a multiple line search, it begins with the anchors ^ and $, it will match the start and end of a line. 
u
* unicode
y
* Only matches form its last index postion and ingores the global flag. 
s.
* will match any character, including a newline. 
### Grouping and Capturing
* (123) capturing groups of mutiple tokens togther and creates a capture group for extracting a substring or using a backreference
* (?< name >XYZ) named capturing group captures groups of specific name.
\1
* is a numeric reference
(?:XYZ) 
* groups multiple tokens together without creating a capture group
### Bracket Expressions
A bracket expressions surronded by square barakets is a regular expression that matches either a single character or multiple characters depending on the expression. If the intial character is has a ^, Then the expression is complemented.
### Greedy and Lazy Match
Greedy
* matches the longest possible string. It tells the engine to match as many instances as possible.
Lazy
* matches the shorest possible string. It tells the engine to match as few instances as possible.
### Boundaries
The metacharacter \b is an anchor like the caret and the dollar sign. It matches at a position that is called a “word boundary”. This match is zero-length.
Simply put: \b allows you to perform a “whole words only” search using a regular expression in the form of \bword\b. A “word character” is a character that can be used to form words. All characters that are not “word characters” are “non-word characters”.

Since digits are considered to be word characters, \b4\b can be used to match a 4 that is not part of a larger number. This regex does not match 44 sheets of a4. So saying “\b matches before and after an alphanumeric sequence” is more exact than saying “before and after a word”.

\B is the oppostie of \b. It matches at every postion where \b does not. 

### Back-references
Backreferences match the same text as previously matched by a capturing group. Suppose you want to match a pair of opening and closing HTML tags, and the text in between. By putting the opening tag into a backreference, we can reuse the name of the tag for the closing tag. Here’s how: <([A-Z][A-Z0-9]*)\b[^>]*>.*?</\1>. This regex contains only one pair of parentheses, which capture the string matched by [A-Z][A-Z0-9]*. This is the opening HTML tag. (Since HTML tags are case insensitive, this regex requires case insensitive matching.) The backreference \1 (backslash one) references the first capturing group. \1 matches the exact same text that was matched by the first capturing group. The / before it is a literal character. It is simply the forward slash in the closing HTML tag that we are trying to match.
### Look-ahead and Look-behind

* (?=XYZ) is a postive lookahead and it matches a group after the main expression without including it in the result.

* (?!XYZ) is a negitive lookahead and it specifies a group that can not match after the main expression (if it matches, the result is discarded)

* (?<=XYZ>) is a postive lookbehind and matches a group before the main expression without including it in the result.

* (?<!XYZ) is a negitive lookbehind and Specifies a group that can not match before the main expression (if it matches, the result is discarded).
## Author

My name is Connor Werth (GitHub: https://github.com/Connorw2222) as of fall 2021 I am a full-time college student on my last semester working on towards a Bachelor of Science in Business Administration – Finance as well as taking a coding bootcamp in full stacks web development. My passions are in all things finance and technology with the hopes of using my knowledge to help others with their own finances.
LinkedIn: https://www.linkedin.com/in/connor-werth-266777206?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3BRuCwkEwKQ5K9Eh2TJ1O5kQ%3D%3D
