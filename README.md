# Arrays lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.

## Question 1

Create an array of strings called `colors` that contain "orange", "red", "yellow", "turquoise", and "lavender".

Then, using array subscripting and string interpolation, print out the String `"orange, yellow, and lavender are some of my favorite colors"`.

```swift
var colorsArray = ["orange", "red", "yellow", "turquoise", "lavender"]

print(" \(colorsArray[0].lowercased().capitalized), \(colorsArray[2]), and \(colorsArray.last!) are some of my favorite colors!")
```


## Question 2

Remove "Illinois" and "Kansas" from the array below.

`var westernStates = ["California", "Oregon", "Washington", "Idaho", "Illinois", "Kansas"]`

```swift

var removeStates = ["Illinois", "Kansas"]
//westernStates.dropLast(2)
//print(westernStates)

for state in westernStates {
    for remove in removeStates where state == remove  {
        let indexOfState = westernStates.firstIndex(of: state)!
        westernStates.remove(at: indexOfState)
    }
}
print(westernStates)
```


## Question 3

Iterate through the array below. For each state, print out the name of the state, a colon, and whether it is or is not **in the continental United States.**

`let moreStates = ["Hawaii", "New Mexico", "Alaska", "Montana", "Texas", "New York", "Florida"]`

```swift
let moreStates = ["Hawaii", "New Mexico", "Alaska", "Montana", "Texas", "New York", "Florida"]
let notContinentalUS = "Hawaii"


for state in moreStates {
    if(state != notContinentalUS) {
        print("\(state) is in the continental US.")
    } else {
        print("\(state) is NOT in the continental US.")
    }
}
```


## Question 4

Print out how many non-whitespace characters are in `myString`:

`let myString = "This is good practice with Strings!"`

```swift 
let myString = "This is good practice with Strings!"
var counter = 0
for c in myString {
    if String(c) != " " {
        counter += 1
    }
}
print(counter)
```

Iterate through the array below. For each sentence, print out how many non-whitespace characters are in it.

`let myFavoriteQuotes = ["To be or not to be, that is the question.", "The only source of knowledge is experience.", "Mr. Gorbachev, tear down this wall!", "Four score and twenty years ago..."]`

```swift
let myFavoriteQuotes = ["To be or not to be, that is the question.", "The only source of knowledge is experience.", "Mr. Gorbachev, tear down this wall!", "Four score and twenty years ago..."]
var counter = 0

for quote in myFavoriteQuotes {
    for c in quote {
        if String(c) != " " {
            counter += 1
        }
}
print("\"\(quote)\" has \(counter) non-whitespace characters.")
counter = 0
}
```


## Question 5

Iterate through `garden` and place any 🌷 that you find into the `basket`. Replace any 🌷 that you pick up with `"dirt"`. Then print how many 🌷 are in your `basket`.

```swift
var garden = ["dirt","🌷","dirt","🌷","dirt","dirt","🌷","dirt","🌷","dirt"]
var basket = [String]()

for (i, g) in garden.enumerated() {
if g == "🌷" {
    basket.append(g)
    garden[i] = "dirt"
    }
}
print(basket)
print(garden)
```

## Question 6

The below array represents an unfinished batting lineup for a baseball team. **You, the coach,** need to make some last minute changes:

- Add "Suzuki" to the end of your lineup.
- Change "Jeter" to "Tejada".
- Change "Thomas" for "Guerrero"
- Put "Reyes" to bat 8th instead.

`var battingLineup = ["Reyes", "Jeter", "Ramirez", "Pujols","Griffey","Thomas","Jones", "Rodriguez"]`

```swift
var battingLineup = ["Reyes", "Jeter", "Ramirez", "Pujols","Griffey","Thomas","Jones", "Rodriguez"]

battingLineup.append("Suzuki")

battingLineup[1] = "Tejada"

battingLineup[5] = "Guerrero"

var helper = battingLineup[7]
battingLineup[7] = battingLineup[0]
battingLineup[0] = helper

print(battingLineup)
```


## Question 7

Given an array of Ints, find out if it contains a target number.  

(The built-in `contains(_:)` function will do this, but you aren't allowed to use it for this exercise.)


```swift
var numbers: [Int]

let target: Int = 32
```

Ex.1

```swift
numbers = [4,2,6,73,32,4,2,1]

target = 32

//true
```

Ex. 2

```swift
numbers = [32459,2,4,5,1,4,2,1]

target = 3

//false
```
```swift
var exists = false
for n in numbers {
    if n == target {
        exists = true
        break
    }
}
print(exists)
```

## Question 8

Find the largest value in an array of Int.  Do not use the built-in `max()` method.

```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

//This creates an array of 100 numbers in between 0 and 200.  For now, you don't need to worry about how it does that.
```
```swift
var largest = 0

for n in arrayOfNumbers {
    if n > largest {
    largest = n

    }
}
print(largest)
```


## Question 9

Find the smallest value in an array of Int.  Do not use the built in min() method.

```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

//This creates an array of 100 numbers in between 0 and 200.  For now, you don't need to worry about how it does that.
```

```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

var smallest = arrayOfNumbers[0]

for n in arrayOfNumbers {
    if n < smallest {
    smallest = n
    }
}
print(smallest)
```


## Question 10

Iterate through `secondListOfNumbers`, and print out all the odd numbers.

`var secondListOfNumbers = [19,13,14,19,101,10000,141,404]`

```swift
var secondListOfNumbers = [19,13,14,19,101,10000,141,404]

var oddNumbers: [Int] = []

for n in secondListOfNumbers {
    if n % 2 != 0 {
    oddNumbers.append(n)
    }
}
print(oddNumbers)
```


## Question 11

Iterate through `thirdListOfNumbers`, and print out the sum.

`var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]`

```swift
var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]

var sumOfthirdListOfNumbers = 0

for n in thirdListOfNumbers {
    sumOfthirdListOfNumbers += n
}
print(sumOfthirdListOfNumbers)
```

## Question 12

Iterate through `thirdListOfNumbers`, and print out the sum of all the even numbers.

`var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]`

```swift
var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]

var sumOfEvenInthirdListOfNumbers = 0

for n in thirdListOfNumbers {
    if n % 2 == 0 {
        sumOfEvenInthirdListOfNumbers += n
    }
}
print(sumOfEvenInthirdListOfNumbers)
```


## Question 13

Append every Int that appears in both `listOne` and `listTwo` to the `sharedElements` array. Then print **how many Ints** are shared.

```swift
var listOne = [28, 64, 7, 96, 13, 32, 94, 11, 80, 68]
var listTwo = [18, 94, 48, 6, 42, 68, 79, 76, 13, 7]
var sharedElements = [Int]()

var sharedElements = [Int]()

for n in listOne {
    for m in listTwo {
        if n == m {
            sharedElements.append(n)

        }
    }
}
print(sharedElements)
```


## Question 14

Write code such that `noDupeList` has all the same Ints as `dupeFriendlyList`, but has no more than one of each Int.

```swift
var dupeFriendlyList = [4,2,6,2,2,6,4,9,2,1]
var noDupeList: [Int] = []

for n in dupeFriendlyList {
    if noDupeList.contains(n) {
        continue
    } else {
        noDupeList.append(n)
    }
}
print(noDupeList)

```

## Question 15

Find the second smallest number in an Array of Ints

`let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}`

```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}
var smallest = arrayOfNumbers[0]
var secondSmallest = arrayOfNumbers[0]

for n in arrayOfNumbers {
    if n < smallest {
        smallest = n
    } else if n < secondSmallest && n != smallest {
        secondSmallest = n
    }
}
print(smallest)
print(secondSmallest)
```


## Question 16

If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Find the sum of all the multiples of 3 or 5 below 1000.

```swift
var range = 1...1000
var multiplesOf3: [Int] = []
var multiplesOf5: [Int] = []
var sumOfMultiplesof3 = 0
var sumOfMultiplesof5 = 0

for n in range {
    let multiplication = n * 3
    multiplesOf3.append(multiplication)
}

for n in multiplesOf3 {
    let sum = n + sumOfMultiplesof3
    sumOfMultiplesof3 = sum
}

for n in range {
    let multiplication = n * 5
    multiplesOf5.append(multiplication)
}

for n in multiplesOf5 {
    let sum = n + sumOfMultiplesof5
    sumOfMultiplesof5 = sum
}
var sumOfMultiplesOf3and5 = sumOfMultiplesof3 + sumOfMultiplesof5
print(sumOfMultiplesOf3and5)
```


## Question 17

Make an array that contains all elements that appear **more than twice** in `someRepeatsAgain`.

```swift
var someRepeatsAgain = [25,11,30,31,50,28,4,37,13,20,24,38,28,14,44,33,7,43,39,35,36,42,1,40,7,14,23,46,21,39,11,42,12,38,41,48,20,23,29,24,50,41,38,23,11,30,50,13,13,16,10,8,3,43,10,20,28,39,24,36,21,13,40,25,37,39,31,4,46,20,38,2,7,11,11,41,45,9,49,31,38,23,41,16,49,29,14,6,6,11,5,39,13,17,43,1,1,15,25]

var freqDict = [Int: Int]()
for num in someRepeatsAgain {
    if freqDict.keys.contains(num) {
        freqDict[num] = freqDict[num]! + 1
    } else {
    freqDict[num] = 1
    }
}

var repeats: [Int] = []

for (key, value) in freqDict {
    if value > 2 {
        repeats.append(key)
    }
}
print(repeats)
```


## Question 18

Identify if there are 3 integers that sum to 10 in the following array. If so, print them as a triplet. If there are multiple triplets, print all possible triplets.

`var tripleSumArr = [-20,-14, -8,-5,-3,-2,1,2,3,4,9,15,20,30]`

```swift
var triplets: [[Int]] = []

for a in tripleSumArr {
    for b in tripleSumArr {
        for c in tripleSumArr {
            if a + b + c == 10 && !triplets.contains([a,b,c].sorted()) {
                triplets.append([a,b,c].sorted())
            }
        }
    }
}
print(triplets)
```


## Question 19

Given an array of Strings, find the the String with the most "a"s in it.

input: `["apes", "abba", "apple"]`

output: `"abba"`

```swift
var aCounter = 0
var largestCounter = 0
var largestWord = ""

for word in input {
    for c in word {
        if String(c) == "a" {
            aCounter += 1
        }
    }

    if aCounter > largestCounter {
        largestWord = word
        largestCounter = aCounter
    }
    aCounter = 0
}
print(largestWord)
```


## Question 20

Given an Array of Arrays of Ints, find the Array of Ints with the largest sum:

Input: `[[2,4,1],[3,0],[9,3]]`

Output: `[9,3]`

```swift
var largestSum = 0
var largest: [Int] = []

for n in input {
    let tempSum = n.0 + n.1
        if tempSum > largestSum {
        largest = [n.0, n.1]
        largestSum = tempSum
    }
}
print(largest)
```


## Question 21

Given an Array of Tuples of type `(Int, Int)`, create an array containing all the tuples where the first Int is equal to the second Int.

Input: `[(4,2), (-3,-3), (1,1), (3,9)]`

Output: `[(-3,-3), (1,1)]`

```swift
var equals: [(Int, Int)] = []
for n in input {
    if n.0 == n.1 {
        equals.append(n)
    }
}
print(equals)
```


## Question 22

Given an Array of Bools, make a variable called `allAreTrue` that is true if all of the Bools are true and false if any of them are false.

Input: `[true, false, true, true]`

Output: `false`

```swift
var allAreTrue = true

var input =  [true, false, true, true]
for i in input {
    if !i {  //note to self: same as 'i == false'
        allAreTrue = false
        break
    }
}
print(allAreTrue)
```


## Question 23

Given an Array of Ranges of Ints, create an array that has all the values from all the ranges in order from smallest to greatest with no duplicates.

Input: `[0..<3 , 2..<10, -4..<6, 13..<14]`

Output: `[-4,-3,-2,-1,0,1,2,3,4,5,6,7,8,9,10,13]`

```swift
var result: [Int] = []

for i in input {
    for j in i {
        if !result.contains(j) {
            result.append(j)
        }
    }
}
print(result.sorted())

//NOTE: 10 is included in the expected output however is NOT in the range as the second range goes from two to LESS than 10 '2..<10' NOT less or equal to 10.
//this prints: [-4, -3, -2, -1, 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 13]
```


## Question 24

Given an array of Characters, create a String ignoring and uppercase Characters and spaces.  Then uppercase every other character of the String.

Input: `let arr: [Character] = ["a", "p","P","l","E"," ","S","a","u","C,"e"]`

Output: `"ApLeAuE"`

```swift
var newString = ""
var auxiliaryIndex = 0

for c in arr where !c.isUppercase && c != " " {
    if auxiliaryIndex % 2 == 0{
        newString.append(c.uppercased())
    }else{
        newString.append(c.lowercased())
    }
    auxiliaryIndex += 1
}
print(newString)

// NOTE: 'e' shouldn't be included in expected output because 'E' is uppercased in the original array. Output after removing spaces and uppercased characters is 'aplaue' and after uppercasing every other character is 'ApLaUe.'
```

## Question 25

Print out each element in `myMatrix`

`var myMatrix = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]`

```swift
for n in myMatrix {
    for j in n {
        print(j, terminator: " ")
    }
}

// prints 10 14 12 91 1 9 31 3 21 
```


## Question 26

Print out the sum of the diagonals of `myMatrix`.

`var myMatrix = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]`

```swift
var principalDiagonal = 0
var secondaryDiagonal = 0
var matrixSize = myMatrix.count

for (i, n) in myMatrix.enumerated() { // i = outer index and n array of values in index
    for (j, m) in n.enumerated() { // j inner index and m is value of index
        if i == j{ // 0, 0 1, 1 and 2, 2 add to principal
            principalDiagonal += m
        }
        if (i+j) == (matrixSize-1) { //if outer index + inner index = matrix size - 1 (i.e. 2) add index value to secondaryDiagonal.
            secondaryDiagonal += m
            }
        }
}
print(principalDiagonal)
print(secondaryDiagonal)
```


## Question 27

Using for loops, rotate `matrixToRotate` 90 degrees.

var matrixToRotate = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

![Matrix Rotation](images/rotated_matrix.jpeg)

```swift
var matrixToRotate = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
var reversedMatrix = [[Int]](repeating: [Int](repeating: 0, count: 3), count: 3)

// 789 456 123 what i have
// 741 852 963 what i want

for (i, n) in matrixToRotate.reversed().enumerated() {
    for (j, m) in n.enumerated() {
        reversedMatrix[j][i] = m
    }
}
print(reversedMatrix)

//Note to self: with each iteration, indexes switch, i.e in first iteration, 0, 0 becomes 0, 0 , then 0, 1 becomes 1, 0 and so on.
```
