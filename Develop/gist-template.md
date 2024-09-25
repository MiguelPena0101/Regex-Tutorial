# Character Classes Regex

character classes in regex allow you to define a set of characters that you want to match at a specific position in a string. by placing characters inside square brackets `[]`, the regex engine matches any one of those characters. this makes character classes useful for matching a specific range of letters, digits, or other symbols. they can also be used in combination with ranges (e.g., `[a-z]` for any lowercase letter) and predefined shorthand classes like `\d` for digits or `\w` for word characters. negating a character class with `^` allows you to match any character except those in the set.


## Summary

In this gist, we'll explore the concept of regex character classes, which allow you to match specific sets or ranges of characters within a string. we'll cover basic character classes, shorthand notations, negated classes, and the use of ranges. you'll also learn how to combine multiple classes and apply them to real-world examples like password validation. additionally, we'll explain the difference between greedy and lazy matching within character classes.

 example regex:
```
[a-zA-Z0-9]
```
## Table of Contents

- [character classes](#character-classes)
  - [basic syntax](#basic-syntax)
  - [ranges](#ranges)
  - [pre-defined character classes](#pre-defined-character-classes)
  - [usage examples](#usage-examples)
    - [example 1: matching vowels](#example-1-matching-vowels)
    - [example 2: matching a hexadecimal digit](#example-2-matching-a-hexadecimal-digit)
    - [example 3: matching any alphanumeric character](#example-3-matching-any-alphanumeric-character)
    - [example 4: matching any character except digits](#example-4-matching-any-character-except-digits)
    - [example 5: matching lowercase letters, digits, or underscores](#example-5-matching-lowercase-letters-digits-or-underscores)
  - [negated character classes](#negated-character-classes)
  - [combining character classes](#combining-character-classes)


# Character Classes
character classes in regular expressions allow you to specify a set of characters that should match at a specific position in the input string. when you define a character class, the regex engine looks for any one of the characters inside the square brackets `[]` at the given position. 

### basic syntax
```
- `[abc]` → matches any of the characters 'a', 'b', or 'c'.  
- `[0-9]` → matches any digit from '0' to '9'.  
- `[^abc]` → matches any character except 'a', 'b', or 'c' (negation).  
```
### ranges  
you can define ranges within a character class by using a hyphen `-`.  
```
- `[a-z]` → matches any lowercase letter from 'a' to 'z'.  
- `[A-Z]` → matches any uppercase letter from 'A' to 'Z'.  
- `[0-9]` → matches any digit from '0' to '9'.  
```
### pre-defined character classes  
there are also shorthand character classes that are commonly used:  
```
- `\d` → matches any digit (equivalent to `[0-9]`).  
- `\D` → matches any non-digit character (equivalent to `[^0-9]`).  
- `\w` → matches any "word" character, which includes letters, digits, and underscores (equivalent to `[a-zA-Z0-9_]`).  
- `\W` → matches any non-word character (equivalent to `[^a-zA-Z0-9_]`).  
- `\s` → matches any whitespace character (spaces, tabs, newlines).  
- `\S` → matches any non-whitespace character.  
```
### usage examples  

#### example 1: matching vowels  
``` 
[aeiou]  
```
this matches any vowel from the string.

matches:
```
"apple" → matches the 'a' and 'e'.
"orange" → matches the 'o', 'a', and 'e'.
```
non-matches:
```
"grape" → does not match the 'g', 'r', or 'p'.
```
#### example 2: matching a hexadecimal digit
```
[0-9A-Fa-f]  
```
this matches any valid hexadecimal digit (0-9, A-F, a-f).

matches:
```
"9"
"A"
"b"
```
non-matches:
```
"G" → not a valid hex digit.
"z" → not a valid hex digit.
```
#### example 3: matching any alphanumeric character
```
[0-9A-Za-z]  
```
this matches any uppercase letter, lowercase letter, or digit.

matches:
```
"A"
"5"
"z"
```
non-matches:
```
"&" → not alphanumeric.
"%" → not alphanumeric.
```
##### negated character classes
when you place a caret ^ at the beginning of a character class, it negates the set. this means it will match any character that is not in the class.

#### example 4: matching any character except digits
```
[^0-9]  
```
this matches any character except a digit.

matches:
```
"A"
"z"
"!"
```
non-matches:
```
"5" → it's a digit, so it won't match.
```
##### combining character classes
you can combine different character classes within the same set to create more flexible patterns.

#### example 5: matching lowercase letters, digits, or underscores
```
[a-z0-9_] 
````
this matches any lowercase letter, digit, or underscore.

matches:
```
"a"
"9"
"_"
```
non-matches:
```
"A" → it's uppercase, which isn't in the character class.
"%" → it's not alphanumeric or an underscore.
```


## Author

 [Miguel Peña](https://gist.github.com/MiguelPena0101), but friends call me **Miggy**. i'm currently a student at the EdX Columbia University Engineering Bootcamp, where i'm training to become a full-stack developer. based in new york city, i'm passionate about coding and eager to grow in the world of web development.

