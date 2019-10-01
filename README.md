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

```
Question # 1 Answer

var numString = ""

for i in 1...10{
 numString += string(i)
}

print(numString)
```

***
## Question 2

Write code that prints out all the even numbers from 5 to 51 as a single string.

```
Question # 2 Answer

var numberString = ""

for i in 5...51{
    if( i % 2 == 0){
        numberString += String(i)
        numberString += " "
    }
}

print(numberString)
```

***
## Question 3

Write code that prints out every number ending in 4 between 1 and 60 as a single string.

```
Question # 3 Answer

var numberString = ""

for i in 1...60{
    if( i % 10 == 4){
        numberString += String(i)
        numberString += " "
    }
}

print(numberString)
```

***
## Question 4

Print each character in the string `"Hello world!"`

```
Question # 4 Answer

var numberString = "Hello World!"

for char in numberString{
    print(char)
}

```


***
## Question 5

Print out the last character in the string below.  You cannot use the Character literal "!" (i.e you must access `myStringSeven`'s characters).

`let myStringSeven = "Hello world!"`

```
Question # 5 Answer

let myStringSeven = "Hello world!"

var lastLetter = myStringSeven.index(before: myStringSeven.endIndex)

print(myStringSeven[lastLetter])

```

***
## Question 6 // Start at index 1 or 2?

Write code that switches on a string, given the following conditions:
- If the string's length is even, print out every character.
- If the string's length is odd, print out every other character.

```
Question #6 Answer

var stringToSwitch = "Some string"
var strLength = stringToSwitch.count
var strEvenOrOdd = strLength % 2 == 0

switch strEvenOrOdd{

    case true:
    for char in stringToSwitch{
        print(char)
    }
    
    default:
    var printOrNotToPrint = true // Change to false if every other begins at second character
    for char in stringToSwitch{
    if printOrNotToPrint{
        print(char)
        printOrNotToPrint = false
    } else{
        printOrNotToPrint = true
      }
    }
}

```

***
## Question 7 

Initialize a String with a character. Show that it is a Character, and not another String, that you're using to initialize it.

```
Question #7 Answer

let characterVariable: Character = "a"
var stringVariable: String = String(characterVariable)
```

***
## Question 8

Build five pairs of **canonically equivalent** strings, the first of each being a pre-composed character and the second being one that uses combinable unicode scalars. Show that they are equivalent.

```
Question #8 Answer

var firstPairVarA = "\u{00F1}"
var firstPairVarB = "\u{006E}\u{0303}"

if(firstPairVarA == firstPairVarB){
    print("\(firstPairVarA) is canonically equivalent to \(firstPairVarB).")
}

var secondPairVarA = "\u{0100}"
var secondPairVarB = "\u{0041}\u{0304}"

if(secondPairVarA == secondPairVarB){
    print("\(secondPairVarA) is canonically equivalent to \(secondPairVarB).")
}
var thirdPairVarA = "\u{00E3}"
var thirdPairVarB = "\u{0061}\u{0303}"

if(thirdPairVarA == thirdPairVarB){
    print("\(thirdPairVarA) is canonically equivalent to \(thirdPairVarB).")
}
var fourthPairVarA = "\u{00D5}"
var fourthPairVarB = "\u{004F}\u{0303}"

if(fourthPairVarA == fourthPairVarB){
    print("\(fourthPairVarA) is canonically equivalent to \(fourthPairVarB).")
}
var fifthPairVarA = "\u{00FA}"
var fifthPairVarB = "\u{0075}\u{0301}"

if(fifthPairVarA == fifthPairVarB){
    print("\(fifthPairVarA) is canonically equivalent to \(fifthPairVarB).")
}
```

***
## Question 9

**Using only Unicode**, print out `"HELLO WORLD!"`

```
Question #9 Answer

let greeting = "\u{0048}\u{0045}\u{004C}\u{004C}\u{004F}\u{0020}\u{0057}\u{004F}\u{0052}\u{004C}\u{0044}\u{0021}"

print(greeting, terminator:"")

```

***
## Question 10

**Using only Unicode**, print out your name.

```
Question #10 Answer

var myName = "\u{0043}\u{0061}\u{006D}\u{0065}\u{0072}\u{006F}\u{006E}"

print("My name is: \(myName)", terminator: "")
```

***
## Question 11

**Using only Unicode**, print out `"HELLO WORLD!"` in another language.

```
Question #11 Answer

var japanglish = "\u{30D8}\u{30ED}\u{0020}\u{30EF}\u{30EB}\u{30C9}"

print("Hello world in Japanese is \(japanglish)", terminator: "")
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

```
Question #12 Answer

var flower = "\u{2698}"

print("Flower Box:")

for i in 1...9{
    switch i {
        case 1:
            for _ in 1...11{
                    print("-",terminator: " ")
            }
            print()
        case 2...8:
            for j in 1...11{
                if(j % 2 == 1){
                    print("|", terminator:" ")
                } else {
                    print(flower,terminator:" ")
                }
            }
            print()
        default:
            for _ in 1...11{
                    print("-",terminator: " ")
            }
            print()
    }
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

```
Question #13 Answer

let whiteKing = "\u{2654}"
let whiteQueen = "\u{2655}"
let whiteRook = "\u{2656}"
let whiteBishop = "\u{2657}"
let whiteKnight = "\u{2658}"
let whitePawn = "\u{2659}"

let blackKing = "\u{265A}"
let blackQueen = "\u{265B}"
let blackRook = "\u{265C}"
let blackBishop = "\u{265D}"
let blackKnight = "\u{265E}"
let blackPawn = "\u{265F}"

print("Chess Board:")

for i in 1...8{
    switch i{
        case 1:
            for j in 1...8{
                switch j {
                    case 1:
                    print(whiteRook,terminator:" ")
                    case 2:
                    print(whiteKnight,terminator:" ")
                    case 3:
                    print(whiteBishop,terminator:" ")
                    case 4:
                    print(whiteKing,terminator:" ")
                    case 5:
                    print(whiteQueen,terminator:" ")
                    case 6:
                    print(whiteBishop,terminator:" ")
                    case 7:
                    print(whiteKnight,terminator:" ")
                    default:
                    print(whiteRook,terminator:" ")
                }
            }
            print()
        case 2:
            for _ in 1...8{
                print(whitePawn, terminator:" ")
            }
            print()
        case 3...6:
            print()
        case 7:
            for _ in 1...8{
                print(blackPawn, terminator:" ")
            }
            print()
        default:
            for j in 1...8{
                switch j {
                case 1:
                    print(blackRook,terminator:" ")
                case 2:
                    print(blackKnight,terminator:" ")
                case 3:
                    print(blackBishop,terminator:" ")
                case 4:
                    print(blackKing,terminator:" ")
                case 5:
                    print(blackQueen,terminator:" ")
                case 6:
                    print(blackBishop,terminator:" ")
                case 7:
                    print(blackKnight,terminator:" ")
                default:
                    print(blackRook,terminator:" ")
                }
            }
            print()
    }
}

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

```
Question #14 Answer

var aString = "Replace the letter e with *"
var startingPoint = aString.startIndex
var endPoint = aString.index(before: aString.endIndex)
var currentIndex = startingPoint
var off = 0

while currentIndex < endPoint {
    
    currentIndex = aString.index(startingPoint, offsetBy: off)
    if(aString[currentIndex] == "\u{0065}"){
        aString.insert("\u{002A}",at: currentIndex)
        aString.remove(at:aString.index(after:currentIndex))
    }
    off += 1
}
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

```
Question #15 Answer

var stringToReverse = "This is the string to reverse"
var reverse = stringToReverse
let startPoint = stringToReverse.startIndex
let endPoint = stringToReverse.index(before: stringToReverse.endIndex)
var tempStart: Character
var tempEnd: Character
var fromEnd = -1
var fromBeginning = 1
var nextLeft = startPoint
var nextRight = endPoint

while(nextLeft <= nextRight){
   
    tempStart = stringToReverse[nextLeft]
    tempEnd = stringToReverse[nextRight]
    reverse.insert(tempEnd,at: nextLeft)
    reverse.remove(at:reverse.index(after:nextLeft))
    reverse.insert(tempStart, at: nextRight)
    reverse.remove(at:reverse.index(after:nextRight))
    nextLeft = reverse.index(startPoint, offsetBy: fromBeginning)
    nextRight = reverse.index(endPoint,offsetBy: fromEnd)
    fromEnd -= 1
    fromBeginning += 1
}

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
```
Question #16 Answer

var geographicLocation: String = "the moon"
var adjective1: String = "spicy"
var pluralNoun1: String = "oxen"
var adjective2: String = "melancholy"
var pluralNoun2: String = "humans"
var number1: Int = 502
var number2: Int = 9
var articleOfClothing: String = "hat"

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

***
## Question 4

Given a string in English, create a tuple containing the number of vowels and consonants.

```swift
let vowels = "aeiou"
let consonants = "bcdfghjklmnpqrstvwxyz"
let input = "Count how many vowels I have!"
```

***
## Question 5

Given a string of words separated by a `" "`. Write code that prints out the length of the last word.

If there is no last word print out `"No last word"`.

Example:
Input: `"How are you doing this Monday?"`

Output: `7`

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

***
## Question 7

Given a string `testString` create a new variable called `condensedString` that has any consecutive spaces in `testString` replaced with a single space.

```swift
let testString = "  How   about      thesespaces  ?  "
//condensedString = " How about thesespaces ? "
```

***
## Question 8

Given a string with multiple words. Reverse the string word by word.

Example:

Sample Input: `"Swift is the best language"`

Sample Output: `"language best the is Swift"`

***
## Question 9

Given a string with multiple words. Write code that prints how many of them are palindromes.

Example:

Sample Input: `"danaerys dad cat civic bottle"`

Sample Output: `2`

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

