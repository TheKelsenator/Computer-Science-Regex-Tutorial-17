# Module 17 Challenge - Learn Github gist & Regex Tutorial

## Summary

  In this gist I will be describing the regex expression 'Matching an Email'. I will cover each component and what it does so we can understand the search pattern the regex defines. Below is the code snippet we will walk through: 

## Regex Components

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Boundaries](#boundaries)

### Anchors

  Anchors are regex tokens that don't match any characters, but that tell us something about the string or the matching process. The anchors in this component are the carrot ```^```, which signifies the beginning of the string (it is positioned before the first character in the string) and the dollar sign ```$``` which signifies the end of the string (it is positioned after the last character in the string). 
  <br>
  The email regex starts with ```/^``` and ends with ```$/``` 

### Quantifiers

  Quantifiers specify how many instances of a character, group, or character class must be present in the input string for a match to occur. The two types of quantifiers we will talk about for the purpose of this tutorial are greedy quantifiers and lazy quantifiers. 
  <br>
  * Greedy quantifiers are referred to as 'greedy' because they are repetitive and will attempt to much as many characters as possible. They are: ```*```, ```?```, ```+```, ```{ n }```, ```{ n, }```, and ```{ n, m }```
  <br>
  * Lazy quantifiers are referred to as 'lazy' because they match as little times as possible. They use all of the greedy quantifiers, but also include: ```*?```, ```+?```, ```??```, ```{ n }?```, ```{ n ,}?```, ```{ n, m }?```  
  <br>
  ```
  /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
  ```
  We can see the greedy quantifier ```+``` is used twice in the email regex. Just before the close of the first set of parenthesis, and just before the close of the second set of parenthesis. This indicated to match the preceding item 1 or more times. 
  <br>
  The greedy quantifier at the end uses ```{ n, m }```, this matches the previous element at least ```n``` times (in this case 2), but no more than ```m``` times (in this case 6).

### OR Operator

  The OR Operater allows you to create regular expression patterns to match any one out of a set of alternative choices \- it uses parenthesis to control the order of operations in a pattern.
  <br>
  For example: 
  <br>
  ```
  /^I like (dogs|penguins), but not (lions|tigers).$/
  ```
  Will match any of the following: 
  <br>
  ```
  I like dogs, but not lions.
  I like dogs, but not tigers.
  I like penguins, but not lions.
  I like penguins, but not tigers.
  ```

  (example source: https://www.ocpsoft.org/tutorials/regular-expressions/or-in-regex/)
 
### Character Classes

  Character classes distinguish different kinds of characters, for example letters and digits. 
  <br>
  ```
  . - matches any single character (except line terminators)
  \d - matches any digit
  \w - matches any alphanumeric character
  ```
  In the email regex we can see that ```\d``` is used to look for any digits.

### Grouping and Capturing

Capturing groups are a way to treat multiple characters as a single unit, they are created by placing hte characters to be grouped inside a set of parenthesis. 
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
In the email regex we can see three seperate groups: 
```
/^(email user name)@(email provider).(domain extension)$/
```

### Bracket Expressions

  Bracket expressions are a character or characters enclosed in brackets ```[]```.
  <br>
  ```
  [abcd] - Matches any character in the square brackets.
  [a-d] - Matches any character in the range of characters.
  ```
  In the email regex we can see this happens in each grouping:
  ```
  [a-z0-9_\.-]
  ```
  Searches all lower case characters from a-z
  <br>
  Searches all numeric characters 0-9
  ```
  [\da-z\.-]
  ```
  Searches any digit and all lowercase characters from a-z

### Boundaries

  Word boundaries are useful for finding whole or partial word searches in exactly the way you want to find them. They are identified with either ```\b``` or ```\B```

  ```
  |HELLO|, |WORLD|!
  ```
  The vertical lines in the example above are to demonstrate the beginning and end of set boundaries. The boundary distinguishes between two characters in the string, where one is a word character ( ```\w``` ) and the other is not. 

## Author

  Kelsey O'Kelley
  <br>
  University of Utah
  Full-Stack Web Development Coding Bootcamp
  -Fall 2022 - Spring 2023
  <br>
  Github [TheKelsenator]
  https://github.com/TheKelsenator
