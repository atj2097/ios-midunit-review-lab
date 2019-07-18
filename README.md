## Mid Unit-1 Review


//## Strings
//1. **Given a String, return a String with each letter uppercased**
```swift
let  helloPhrase = "Hello there"
print(helloPhrase.uppercased())
```

//2. **Given a String, return a String alternating between uppercase and lowercase letters**
```swift
var phrase = "Hello, there"
var phraseFix = [String]()
for (index, char) in phrase.enumerated() {
if index % 2 == 0 {
phraseFix += [char.uppercased()]
}else {
phraseFix += [char.lowercased()]
}
}

print(phraseFix.joined())
```

//3. **Given a String, return a String with all occurrences of a given letter removed**
//Input: `Hello, there`


//## Arrays
//1. **Given an array of type [Int], return the largest element**

var arrayOfNum = [1,5,2,4,1,4]
var largestNum = arrayOfNum.max()!

//2. **Given an array of type [Int], return the smallest element**

```swift
var lowestNum = arrayOfNum.min()!
```
//3. **Given an array of type [Int], return its sum**

```swift
var sumOfArray = arrayOfNum.reduce(0, +)
```

//4. **Given an array of type [Double], return its average**

```swift
var arrayOfDouble = [3,4.5,7.5,2,1]
var averageOfArray = Double()

for num in arrayOfDouble {
averageOfArray += num
}
print(averageOfArray / Double(arrayOfDouble.count))
```

//5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**
```swift
var result = Double()
var array1:[Double] = [3,4.5,7.5,2,1]

for num in array1 {
if num > 3 {
result += num
}
}
print(result)
```

//6. **Given an array of type [Double], return the product of all the elements**

```swift
var productResult:Double = 1
var doubleArray:[Double] = [3,4.5,7.5,2,1]

for i in doubleArray {
productResult *= i
}
print(productResult)
```

//7. **Given an array of type [Int], return the second smallest value in the array**

```swift
var arrayOfInt = [3,6,1,9,4,8]

var sortedarrayOfInt = arrayOfInt.sorted()
print(sortedarrayOfInt[1])
```

//## Optionals
//1. **Given an array of type [String?] return an array of [String] removing all nil values**
```swift
var optionStringArray = [nil, "We", "come", nil, "in", "peace"]

var nonNilValue = [String]()

for value in optionStringArray{
if let value1 = value {
nonNilValue += [value1]
}
}
print(nonNilValue)
```

//2. **Given an array of type [String?]? return an array of [String] removing all nil values**

```swift
var optionalArray :[String?]? = [nil]
var emptyArray = [String]()
if let array = optionalArray{
for i in array {
if let value = i {
emptyArray += [value]
}
}
}
print(emptyArray)
```

//3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

```swift
var sum = Int()
var inputArray = [4, nil, 9, 5, nil]

for input in inputArray {
guard let value = input else {
continue
}
sum += value
}
print(sum)
```


//4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

```swift
//Input: `nil`
var output = Int()
var inputArray2: [Int?]? = [nil]

if let array = inputArray2 {
for value in array {
guard let number = value else {
continue
}
output += number
}
}
print(output)
```


//5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

```swift
var inputtArray3 = [1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3]
var sum2 = Int()
for i in inputtArray3 {
if let value = i {
if value != 1{
sum2 += value
}
}
}
print(sum2)
```

//## Dictionaries
//1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

```swift
var outputDict = [String]()
var inputDict = ["apple", "apple", "banana", "banana", "banana", "cake", "cake"]

for value in inputDict where outputDict.contains(value) == false {
outputDict += [value]
}
print(outputDict)
```

//OR

```swift
var outputDict2 = Set(inputDict)
print(outputDict2)
```

//2. **Given a String, find the most frequently occurring letter**
//Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`
//Output: `t`

```swift
var sentence = "Never trust a computer you can't throw out a window ~ Steve Wozniak"
var setSentence = Set(sentence)
var alphabets = "abcdefghijklmnopqrstuvwxyz"
var counter1 = 0
var senteceDict = [Character:Int]()



for value in setSentence where alphabets.contains(value){
for letter in sentence where alphabets.contains(letter){
if value == letter{
counter1 += 1
senteceDict[value] = counter1
}
}
counter1 = 0
}
for i in senteceDict where i.value == senteceDict.values.max()!{
print(i.key)
}
```


//3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice**
```swift

var inputArray4 = [1,1,2,3,3,3,4,5,6,6,7]
var setCompare = Set(inputArray4)
var counter = 0
var dictionary = [Int:Int]()
var valueMoreThan2 = [Int]()

for uniqueValue in setCompare {
for value in inputArray4 {
if value == uniqueValue{
counter += 1
dictionary[uniqueValue] = counter
}
}
counter = 0
}

for dict in dictionary{
if dict.value >= 2 {
valueMoreThan2 += [dict.key]
}
}
print(valueMoreThan2)
```

//4. **Given a String, find the second most frequently occurring letter in a string**

// `Never trust a computer you can't throw out a window ~ Steve Wozniak

//4. **Given a String, find the second most frequently occurring letter in a string**
```swift

var string4 = "Never trust a computer you can’t throw out a window ~ Steve Wozniak"
var alphabet2 = "abcdefghijklmnopqrstuvwxyz"
var setCompare2 = Set(string4)
//print(setCompare)
//var newnums = [String]()
var counter2 = 0
var dictionary1 = [Character:Int]()
for letter in setCompare2 where alphabet2.contains(letter){
for char in string4 where alphabet2.contains(char) {
if letter == char {
counter2 += 1
dictionary1[letter] = counter2
}
}
counter2 = 0
}
var maxKey = dictionary1.values.sorted().reversed()[1]
for i in dictionary1 where i.value == maxKey {
print(i.key)
}
```

//## Closures
//1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**


```swift
var closureString = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]
var sortedWithCapitalLetter = closureString.sorted()
print(sortedWithCapitalLetter)
```
//2. **Given an array of type [String], return an array that contains the Strings sorted by length**

```swift
var arrayOfStrings = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]
var arrayOfStringsSorted = arrayOfStrings.sorted(by: {$0.count < $1.count})
print(arrayOfStringsSorted)
```


//3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

```swift

var arrayOfStrings1 = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]
var arrayOfStrings4CharLong = arrayOfStrings1.filter({$0.count >= 4})
print(arrayOfStrings4CharLong)
```

//4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

```swift
var arrayOfStrings2 = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]
var arrayOfStringsjoined = String()

for i in arrayOfStrings2 {
arrayOfStringsjoined += "\(i) "
}
print(arrayOfStringsjoined)
var arrayOfStringsjoined1 = arrayOfStrings2.joined(separator: " ")
print(arrayOfStringsjoined1)
```

//## Enums
//1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**

```swift
var arrayOfIntegers =  [1,2,3,4,5,6]
enum NumberType {
case even
case odd

func allOddNumbers(arr:[Int]) -> [Int]{
var values = [Int]()
switch self {
case .even:
for i in arr where i % 2 == 0 {
values += [i]

}
case .odd:
for i in arr where i % 2 == 1 {
values += [i]
}
}
return values
}
}
print(NumberType.odd.allOddNumbers(arr: arrayOfIntegers))
```


//2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

```swift

var sentence1 = "Design is not just what it looks like and feels like. Design is how it works"

enum StringType {
case lowercase
case uppercase

func uppercaseOrLowercase(sentence:String){

switch self {
case .lowercase:
print(sentence1.lowercased())
case .uppercase:
print(sentence1.uppercased())
}
}
}

StringType.uppercase.uppercaseOrLowercase(sentence: sentence1)
```

//3. **Given an array of type [FileStatus] (defined below) and an Int, return an array containing only files that were saved more than that many times**

`
```
enum FileStatus: CustomStringConvertible {
case unsaved
case saved(numberOfVersions: Int)
var description: String {
switch self {
case .unsaved: return "Unsaved File"
case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
}
}
}


var arrayOfEnums = [FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)]
```

