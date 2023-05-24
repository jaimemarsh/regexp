# How to write a phone number in a regular expression
A regular expression works for all programming languages. It uses special code to detect patterns in strings of text according
to defined rules the coder sets for the user. This can be useful for emails, username, passwords, or what we will be going 
over today: a phone number.
Regular Expressions is similar to a keyword search. For example if you search "JavaScript", any string containing it will 
be returned. We want there to be a perfect match between us and the user, just like we want in a keyword search. If we search
JavaScript we don't want "Java" to return, because we know they are not the same thing. For an email to be a match we know we
need there to be letters, numbers, an @ symbol, ect. If those characters are not entered we do not want the form or login to
be sent through because it is not a match to what we need. That's where regular expressions can work for us. It will not let
the user move on until it is the correct expression. Right now we are going to go over regular expressions for a phone number.
There are many rules needed to know, but here is what it looks like: /^(\d\d\d)\d\d\d-\d\d\d\d$/.

## Summary
A phone number contains ten digits in a specific pattern. We can use regular expressions rules and special characters to write
this in a simple way. These rules will then only allow the phone number to go through from the user when it has the correct
pattern. We will go over Anchors, Character Classes, Grouping Constructs, and Quantifiers. They are the rules we can use to 
help us write an effective and efficient regular expression.

## Table of Contents

- [Anchors](#anchors)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Grouping Constructs](#grouping-constructs)
- [Quantifiers](#quantifiers)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)


## Regex Components


### Anchors
/^(\d\d\d)\d\d\d-\d\d\d\d$/
An anchor, just like anchor tags in html, are used at the beginning or end of the expression. A caret, or ^, is an anchor used
to indicate the beginning of a string. A $ is used to mark the end. If I were to use ^JavaScript it would match "JavaScript is
awesome!" but not "What is javaScript?". This is because ^JavaScript will only return a match if it is at the beginning of 
the string. If I were to use JavaScript$ it would match "What is Javascript?" but not "JavaScript is awesome". This is 
because JavaScript$ will only return a match if it is at the end of a string. If you say ^JavaScript$ it's only match can be
"JavaScript" since it is the beginning and end of the string. This is really helpful to control what the user sends to us.
We will use this at the beginning and end of our regular expression /^(\d\d\d)\d\d\d-\d\d\d\d$/ to make sure that can be the
only thing entered.


### Bracket Expressions
/^(\d\d\d)\d\d\d-\d\d\d\d$/
Bracket expressions are enclosed with square brackets []. They allow you to specify a set of characters at once. Character 
Classes is an example of this feature.

### Character Classes
/^(\d\d\d)\d\d\d-\d\d\d\d$/
Character classes are used to define a set or range of characters that can match a single character. For instance, "\d" 
corresponds to "any digit", this can also be written as [0-9] (a bracket expression). This is because of ranges. You can 
specify a range of characters using a hyphen between the starting and ending characters with numbers and letters. If you were
to do "\D" it would mean anything but a digit, this can also be written as [^0-9]. The caret in this example means the invert
of the phrase. Similar to [a-z] being all lowercase letters, [^a-z] means anything except lowercase letters. It's like a ! in
regular expressions, but only when it is inside the square brackets, otherwise it is an anchor as gone over above. You can 
combine character sets within the brackets, for example "[A-Za-z0-9]" matches any uppercase, lowercase, or digit. For the 
phone number, we only need to use the "\d".
This is what the regular expression would look like /^(\d\d\d)\d\d\d-\d\d\d\d$/ for the phone number formatted (XXX)XXX-XXXX.


### Character Escapes
Character escapes are our "/d". It is used to represent the particular character class [0-9]. The "/d", a character escape,
is simply the way to write it, while character classes is what it represents. There are many more character escapes to 
represent these classes to make it simpler to represent many ranges of characters.

### Grouping Constructs
/^(\d\d\d)\d\d\d-\d\d\d\d$/
Parentheses are used as grouping constructs. They are used to treat the grouped elements as a single unit separately from the
other characters. At the start of the regular expression we specify three digits in the (), then three again in the middle, a
hyphen, and then four digits. This is to represent a phone number pattern that is separated as we normally see it.

### Quantifiers
/^(\d\d\d)\d\d\d-\d\d\d\d$/
A different way to write the phone number would be /^\(\d{3})\d{3}-\d{4}$/. The curly braces in this regular expressions are
called quantifiers. Quantifiers have you specify how many times a particular character should appear in the expression for a 
match to occur. In our expression we say "d{3}" which means it must be three digits in a row. If you were to put a specific 
number, such as "1{3}" it would only match with three occurrences of the number 1.


### The OR Operator
/^(\d\d\d)\d\d\d-\d\d\d\d$/
For a phone number regular expression we will not be using the OR operator, but it is a helpful tool. The OR operator is the
pipe character "|". It will match this OR that (this|that). When used in a regular expression you can say 123|456, and one or
the other pattern will be taken as a match. Cat|dog, left|right, up|down, it will not exepct both. We do not need this in our
phone number as digits are the only characters we want matched.


### Flags
/^(\d\d\d)\d\d\d-\d\d\d\d$/
Flags are added parameters that add more detail to what match you are looking for. We do not need to add any flags to our 
phone number regular expression, but an example of a Flag is case insensitive, or i. In use we could do "/javascript/i" and 
it would match "javaScript", "JavaScript", "JAVAscript" and so on. No flags are needed for our expression 
/^(\d\d\d)\d\d\d-\d\d\d\d$/.


## Author
If you have any questions you can open an issue or contact me directly at jaimemarsh19@gmail.com. You can find more of my 
work at my https://github.com/jaimemarsh