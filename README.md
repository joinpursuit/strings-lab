# Strings Lab 1

## Instructions for lab submission

1. Fork the assignment repo
1. Clone your Fork to your machine
1. Complete the lab
1. Push your changes to your Fork
1. Submit a Pull Request back to the assignment repo
1. Paste a link to of your Fork on Canvas and submit

## Question 1

Write code that prints out all the numbers from 1 to 10 as a single string.
(Hint: the `String()` function can convert an Int to a String)

answer below:

```swift
var numbers1to10 = ""

for num in 1...10 {
    numbers1to10 += String(num) + " "
}
print(numbers1to10)
```

***
## Question 2

Write code that prints out all the even numbers from 5 to 51 as a single string.

answer below:

```swift
var evenNumbers = String()

for num in 5...51 where num % 2 == 0 {
    evenNumbers += String(num) + " "
}
print(evenNumbers)
```
***
## Question 3

Write code that prints out every number ending in 4 between 1 and 60 as a single string.

answer below:

```swift
var four = ""

for num in 1...60 where num % 10 == 4 {
    four += String(num) + ", "
}
four.remove(at: four.index(four.endIndex, offsetBy: -2))
print(four)
```

***
## Question 4

Print each character in the string `"Hello world!"`

answer below:
```swift
var str = "Hello world!"

for character in str {
    print(character)
}
```
***
## Question 5

Print out the last character in the string below.  You cannot use the Character literal "!" (i.e you must access `myStringSeven`'s characters).

`let myStringSeven = "Hello world!"`

answer below:

```swift
let myStringSeven = "Hello world!"

let endOfMyStringSeven = myStringSeven[myStringSeven.index(before: myStringSeven.endIndex)]
print(endOfMyStringSeven)
```

***
## Question 6

Write code that switches on a string, given the following conditions:
- If the string's length is even, print out every character.
- If the string's length is odd, print out every other character.

answer below:

```swift
let stringSwitch = "Water is good"
let lengthOfStringSwitch = stringSwitch.count % 2
var i = 0

switch lengthOfStringSwitch {
case 0:
    print (stringSwitch)
default:
    for character in stringSwitch {
        i += 1
        if i % 2 != 0 {
            print (character, terminator: " ")
        }
    }
}
```

***
## Question 7

Initialize a String with a character. Show that it is a Character, and not another String, that you're using to initialize it.

answer below:

```swift
var rooster = Character(" ")
```
this intializes the variable rooster as a character.  To further prove it is a character we can use the swift built in type(of: ) function:
```swift
print(type(of: rooster)) //prints out Character.
```

***
## Question 8

Build five pairs of **canonically equivalent** strings, the first of each being a pre-composed character and the second being one that uses combinable unicode scalars. Show that they are equivalent.

answer below:

```swift
let canon1A : Character = "\u{00C0}"
let canon1B : Character = "\u{0041}\u{0300}"
print(canon1A == canon1B)

let canon2A : Character = "\u{00D6}"
let canon2B : Character = "\u{004F}\u{0308}"
print(canon2A == canon2B)

let canon3A : Character = "\u{0137}"
let canon3B : Character = "\u{006B}\u{0327}"
print(canon3A == canon3B)

let canon4A : Character = "\u{017B}"
let canon4B : Character = "\u{005A}\u{0307}"
print(canon4A == canon4B)

let canon5A : Character = "\u{01B5}"
let canon5B : Character = "\u{005A}\u{0335}"
print(canon5A == canon5B)
```

***
## Question 9

**Using only Unicode**, print out `"HELLO WORLD!"`

answer below:

```swift
print("\u{0048}\u{0045}\u{004C}\u{004C}\u{004F}\u{0020}\u{0057}\u{004F}\u{0052}\u{004C}\u{0044}\u{0021}")
```

***
## Question 10

**Using only Unicode**, print out your name.

answer below:
```swift
print("\u{0041}\u{0068}\u{0061}\u{0064}")
```

***
## Question 11

**Using only Unicode**, print out `"HELLO WORLD!"` in another language.

answer below:
prints hello world in spanish
```swift
print("\u{00A1}\u{0048}\u{004F}\u{004C}\u{0041}\u{0020}\u{004D}\u{0055}\u{004E}\u{0044}\u{004F}\u{0021}")
```

***
## Question 12

Print the below flower box using the following information.

- The unicode number for ⚘ is U-2698
- The top and bottom of the box are represented by dashes and the rows are |
- Use the terminator argument in your print statements to print on the same line.
- Hint: It may be useful to try printing out a box of just one character to start then work your way from there.

```swift
Flower Box:
- - - - - - - - - - -
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
- - - - - - - - - - -
```
answer below:

```swift
for _ in 1...11 {
    print ("-" , terminator: " ")
}
print()
for _ in 1...7 {
    for _ in 1...5 {
        print("|", terminator: " \u{2698} ")
    }
    print("|")
    print()
}
for _ in 1...11 {
    print ("-" , terminator: " ")
}
```

***
## Question 13

Write a program that sets up a chess board using Unicode.

```swift
Chess Board:
♖ ♘ ♗ ♕ ♔ ♗ ♘ ♖
♙ ♙ ♙ ♙ ♙ ♙ ♙ ♙




♟ ♟ ♟ ♟ ♟ ♟ ♟ ♟
♜ ♞ ♝ ♛ ♚ ♝ ♞ ♜
```
answer below:
```swift
let whiteChessBoardOfPain = "\u{2656}\u{0020}\u{2658}\u{0020}\u{2657}\u{0020}\u{2655}\u{0020}\u{2654}\u{0020}\u{2657}\u{0020}\u{2658}\u{0020}\u{2656}"
print(whiteChessBoardOfPain)
for _ in 1...8 {
    print("\u{2659}", terminator: " ")
}
for _ in 1...4 {
    print()
}
for _ in 1...8 {
    print("\u{265F}", terminator: " ")
}
print()
let blackChessBoardOfPain = "\u{265C}\u{0020}\u{265E}\u{0020}\u{265D}\u{0020}\u{265B}\u{0020}\u{265A}\u{0020}\u{265D}\u{0020}\u{265E}\u{0020}\u{265C}"
print (blackChessBoardOfPain)
```
***
## Question 14

You are given a string stored in the variable `aString`. Create new string named `replacedString` that contains the characters of the original string with all the occurrences of the character `"e"` replaced by `"*"`.

```swift
var aString = "Replace the letter e with *"
// Your code here
 ```

Example:

Input:
`var aString = "Replace the letter e with *"`

Expected values:
`replacedString = "R*plac* th* l*tt*r * with *"`

answer below:

```swift
let aString = "The weather outside is beautiful today."
var replacedString = String()

str1 = str1.replacingOccurrences(of: "e", with: "*")
replacedString = aString.replacingOccurrences(of: "e", with: "*")
print (replacedString)
```

***
## Question 15

You are given a string stored in variable `aString`. Create a new string called `reverse` that contains the original string in reverse order. Print the reversed string.

```swift
var aString = "this string has 29 characters"
var reverse = ""

// Your code here
```

Example:
Input:
`var aString = "Hello"`

Output:
`"olleH"`

answer below:

```swift
var bString = "Hello"
let reversedbString = String(bString.reversed())
print (reversedbString)
```

## 16. Mad-Libs! Add a value to the declared variables below in playgrounds. Insert the variables (already in correct order) inside the stringmadLib and print. 

```swift


var geographicLocation: String
var adjective1: String
var pluralNoun1: String
var adjective2: String
var pluralNoun2: String
var number1: Int
var number2: Int
var articleOfClothing: String

var madLib = "Here is tomorrow's weather report for \()
and vicinity. Early tomorrow, a \()-front will
collide with a mass of hot \() moving from the
north. This means we can expect \() winds and
occasional \() by late afternoon. Wind velocity will
be \() miles an hour, and the high temperature should
be around \() degrees. So, if you're going out, you had
better plan on wearing your \()".
```
answer below:
```swift
var madLib = """
Here is tomorrow's weather report for \(geographicLocation)
and vicinity. Early tomorrow, a \(adjective1)-front will
collide with a mass of hot \(pluralNoun1) moving from the
north. This means we can expect \(adjective2) winds and
occasional \(pluralNoun2) by late afternoon. Wind velocity will
be \(number1) miles an hour, and the high temperature should
be around \(number2) degrees. So, if you're going out, you had
better plan on wearing your \(articleOfClothing).
"""
print(madLib)
```
***

# Bonus :)

***
## Question 1

You are given a string stored in variable `aString`. Print `true` if `aString` is a palindrome, and `false` otherwise. A **palindrome** is a string which reads the same backward or forward.

```swift
let aString = "anutforajaroftuna"

// Your code here
```
answer below:

```swift
let cString = "anutforajaroftuna"
var reversedCString = String(cString.reversed())
if reversedCString == cString {
    print("True")
} else {
    print("False")
}
```

Example 1:
Input:
`var aString = "anutforajaroftuna"`

Output:
`true`

Example 2:
Input:
`var aString = "Hello"`

Output:
`false`

***
## Question 2

You are given a string stored in variable `problem`. Write code so that you print each word of the string on a new line.

```swift
var problem = "split this string into words and print them on separate lines"
// Your code
```

Example:
Input:
`var problem ="split this string into words and print them on separate lines"`

Output:
```swift
split
this
string
into
words
and
print
them
on
separate
lines
```
answer below:

```swift
var problem = "split this string into words and print them on separate lines"
var splitProblem = problem.split(separator: " ")
//print(line.split(separator: " "))
for word in splitProblem {
    print(word)
}
print(splitProblem)
```

***
## Question 3

You are given a string stored in variable `problem`. Write code that prints the longest word in the string.

```swift
var problem = "find the longest word in the problem description"

// Your code here
```

Example:
Input:
`var problem = "find the longest word in the problem description"`

Output:
`description`

Hint: Keep track of the longest word you encounter and also keep track of its length.

answer below:
```swift
var problem2 = "find the longest word in the problem description."
var problem2Split = problem2.split(separator: " ")
var longestWord = ""

for i in problem2Split {
    if String(i).count >= longestWord.count {
        longestWord = String(i)
    }
}
print(longestWord)
```

***
## Question 4

Given a string in English, create a tuple containing the number of vowels and consonants.

```swift
let vowels = "aeiou"
let consonants = "bcdfghjklmnpqrstvwxyz"
let input = "Count how many vowels I have!"
```
answer below:

```swift
let input = "Count how many vowels I have!"
var tupleCount = (vowels: 0, consonants: 0)
for character in input {
    if character == "a" || character == "e" ||  character == "i" || character == "o" || character == "u" {
        tupleCount.vowels += 1
    } else if character != " " || character != "!" {
        tupleCount.consonants += 1
    }
}
print (tupleCount)
```


***
## Question 5

Given a string of words separated by a `" "`. Write code that prints out the length of the last word.

If there is no last word print out `"No last word"`.

Example:
Input: `"How are you doing this Monday?"`

Output: `7`

answer below:

```swift
var stringOfWords = "How are you doing this Monday?"
var stringOfWordsSplit = stringOfWords.split(separator: " ")
var lastStringOfWords = ""

for character in stringOfWordsSplit {
    lastStringOfWords = String(character)
}
print(lastStringOfWords.count)
```

***
## Question 6

You are given a string stored in variable `problem`. Write code so that you print each word of the string on a new line.

```swift
var problem = "split this string into words and print them on separate lines"

// Your code
```

Example

Input:
`var problem ="split this string into words and print them on separate lines"`

Output:
```swift
split
this
string
into
words
and
print
them
on
separate
lines
```
answer below:

```swift
var problem4 = "split this string into words and print them on separate lines"
var problem4Split = problem4.split(separator: " ")
for word in problem4Split {
    print(word)
}
```
***
## Question 7

Given a string `testString` create a new variable called `condensedString` that has any consecutive spaces in `testString` replaced with a single space.

```swift
let testString = "  How   about      thesespaces  ?  "
//condensedString = " How about thesespaces ? "
```
answer:

```swift
let testString = "  How   about      thesespaces  ?  "
var testStringArray = Array(testString)
var indexingTest = ""
var answerString = ""

for index in testStringArray {
    if String(index) != indexingTest {
        answerString += String(index)
    }
    indexingTest = String(index)
}
print(answerString)
```

***
## Question 8

Given a string with multiple words. Reverse the string word by word.

Example:

Sample Input: `"Swift is the best language"`

Sample Output: `"language best the is Swift"`

answer:
```swift
var input1 = "Swift is the best language"
var input1Split = input1.split(separator: " ")
for character in input1Split.reversed() {
    print (character, terminator: " ")
}
print()
```

***
## Question 9

Given a string with multiple words. Write code that prints how many of them are palindromes.

Example:

Sample Input: `"danaerys dad cat civic bottle"`

Sample Output: `2`

answer below:

```swift
var input2 = "danaerys dad cat civic bottle"
var input2Split = input2.split(separator: " ")
var palindromeCount : Int = 0
for character in input2Split {
    if String(character) == String(character.reversed()) {
        palindromeCount += 1
    }
}
print(palindromeCount)
```

***
## Question 10

You are given a string representing an **attendance record** for a student. The record only contains the following three characters:

`'A' : Absent.`

`'L' : Late.`

`'P' : Present.`

If a student has more than one 'A' or more than 2 continuous 'L's that student should not be rewarded. Print true if student is to be rewarded and False if they shouldn't.

Example:

Sample Input: `"PPALLP"`

Sample Output: `true`

***
## Question 11

Given a tuple with two strings. The first string is a **ransom note**, the second string being the characters from a magazine. Determine whether or not you can construct the ransom note using the characters from the magazine.

Each letter from the magazine can only be used once. You can assume all letters are lowercased.

Examples:

Sample Input1: `("a", "b")`

Sample Output1: `False`

Sample Input2: `("aa", "aab")`

Sample Output2: `True`

