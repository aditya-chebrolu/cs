# Java and Swift String Methods Cheat Sheet

## Creating Strings

**Java**
```java
// Using string literal
String str1 = "Hello";
// Using new keyword
String str2 = new String("Hello");
// From a char array
char[] chars = {'H', 'e', 'l', 'l', 'o'};
String str3 = new new String(chars);
// From byte array
byte[] bytes = {72, 101, 108, 108, 111};
String str4 = new String(bytes);
```

**Swift**
```swift
// Using string literal
let str1 = "Hello"
// From a character array
let chars: [Character] = ["H", "e", "l", "l", "o"]
let str2 = String(chars)
// From byte array
let bytes: [UInt8] = [72, 101, 108, 108, 111]
let str3 = String(bytes: bytes, encoding: .utf8)!
```

## Length and Character Access

**Java**
```java
int length = str1.length(); // Returns the length of the string
char ch = str1.charAt(0); // Returns the character at the specified index
```

**Swift**
```swift
let length = str1.count // Returns the length of the string
let ch = str1[str1.startIndex] // Returns the character at the specified index
```

## Substring

**Java**
```java
String sub1 = str1.substring(2); // Returns a substring starting from the specified index
String sub2 = str1.substring(1, 4); // Returns a substring from beginIndex to endIndex - 1
```

**Swift**
```swift
let startIndex = str1.index(str1.startIndex, offsetBy: 2)
let sub1 = String(str1[startIndex...]) // Returns a substring starting from the specified index
let endIndex = str1.index(str1.startIndex, offsetBy: 4)
let sub2 = String(str1[str1.index(str1.startIndex, offsetBy: 1)..<endIndex]) // Returns a substring from beginIndex to endIndex - 1
```

## Concatenation

**Java**
```java
String newStr = str1.concat(" World"); // Concatenates the specified string to the end of this string
```

**Swift**
```swift
let newStr = str1 + " World" // Concatenates the specified string to the end of this string
```

## Contains

**Java**
```java
boolean contains = str1.contains("ell"); // Returns true if the string contains the specified sequence of char values
```

**Swift**
```swift
let contains = str1.contains("ell") // Returns true if the string contains the specified sequence of char values
```

## Equality Check

**Java**
```java
boolean isEqual = str1.equals("Hello"); // Compares this string to the specified object
boolean isEqualIgnoreCase = str1.equalsIgnoreCase("hello"); // Compares this string to another string, ignoring case considerations
```

**Swift**
```swift
let isEqual = str1 == "Hello" // Compares this string to the specified object
let isEqualIgnoreCase = str1.lowercased() == "hello".lowercased() // Compares this string to another string, ignoring case considerations
```

## Starts and Ends With

**Java**
```java
boolean starts = str1.startsWith("He"); // Tests if this string starts with the specified prefix
boolean ends = str1.endsWith("lo"); // Tests if this string ends with the specified suffix
```

**Swift**
```swift
let starts = str1.hasPrefix("He") // Tests if this string starts with the specified prefix
let ends = str1.hasSuffix("lo") // Tests if this string ends with the specified suffix
```

## Index of Characters and Substrings

**Java**
```java
int index1 = str1.indexOf('e'); // Returns the index within this string of the first occurrence of the specified character
int index2 = str1.indexOf("ll"); // Returns the index within this string of the first occurrence of the specified substring
int lastIndex1 = str1.lastIndexOf('l'); // Returns the index within this string of the last occurrence of the specified character
int lastIndex2 = str1.lastIndexOf("l"); // Returns the index within this string of the last occurrence of the specified substring
```

**Swift**
```swift
let index1 = str1.firstIndex(of: "e")?.utf16Offset(in: str1) // Returns the index within this string of the first occurrence of the specified character
let index2 = str1.range(of: "ll")?.lowerBound.utf16Offset(in: str1) // Returns the index within this string of the first occurrence of the specified substring
let lastIndex1 = str1.lastIndex(of: "l")?.utf16Offset(in: str1) // Returns the index within this string of the last occurrence of the specified character
let lastIndex2 = str1.range(of: "l", options: .backwards)?.lowerBound.utf16Offset(in: str1) // Returns the index within this string of the last occurrence of the specified substring
```

## Case Conversion

**Java**
```java
String lower = str1.toLowerCase(); // Converts all characters in the string to lowercase
String upper = str1.toUpperCase(); // Converts all characters in the string to uppercase
```

**Swift**
```swift
let lower = str1.lowercased() // Converts all characters in the string to lowercase
let upper = str1.uppercased() // Converts all characters in the string to uppercase
```

## Trimming and Replacing

**Java**
```java
String trimmed = str1.trim(); // Removes leading and trailing whitespace from the string
String replaced1 = str1.replace('l', 'p'); // Replaces all occurrences of a specified character with a new character
String replaced2 = str1.replace("ll", "yy"); // Replaces each substring of this string that matches the literal target sequence with the specified literal replacement sequence
```

**Swift**
```swift
let trimmed = str1.trimmingCharacters(in: .whitespacesAndNewlines) // Removes leading and trailing whitespace from the string
let replaced1 = str1.replacingOccurrences(of: "l", with: "p") // Replaces all occurrences of a specified character with a new character
let replaced2 = str1.replacingOccurrences(of: "ll", with: "yy") // Replaces each substring of this string that matches the literal target sequence with the specified literal replacement sequence
```

## Splitting and Conversion to Array

**Java**
```java
String[] parts = str1.split(" "); // Splits this string around matches of the given regular expression
char[] charArray = str1.toCharArray(); // Converts this string to a new character array
```

**Swift**
```swift
let parts = str1.split(separator: " ") // Splits this string around matches of the given regular expression
let charArray = Array(str1) // Converts this string to a new character array
```

## Converting Strings

**Java**
```java
char[] chars = str1.toCharArray(); // To char array
byte[] bytes = str1.getBytes(); // To byte array
String strFromChars = new String(chars); // From char array
String strFromBytes = new String(bytes); // From byte array
```

**Swift**
```swift
let chars = Array(str1) // To char array
let bytes = [UInt8](str1.utf8) // To byte array
let strFromChars = String(chars) // From char array
let strFromBytes = String(bytes) // From byte array
```

## Mutating Strings

Since strings are immutable in both Java and Swift, mutating a string involves creating a new string with the desired changes.

**Java**
```java
String newStr1 = str1.replace('l', 'p'); // Replacing characters
String newStr2 = str1.concat(" World"); // Appending strings
String newStr3 = str1.substring(1, 4); // Substrings
StringBuilder sb = new StringBuilder(str1);
sb.insert(2, 'X'); // Inserting characters (using StringBuilder or StringBuffer)
String newStr4 = sb.toString();
```

**Swift**
```swift
let newStr1 = str1.replacingOccurrences(of: "l", with: "p") // Replacing characters
let newStr2 = str1 + " World" // Appending strings
let newStr3 = String(str1[str1.index(str1.startIndex, offsetBy: 1)..<str1.index(str1.startIndex, offsetBy: 4)]) // Substrings
var strBuilder = str1
strBuilder.insert("X", at: str1.index(str1.startIndex, offsetBy: 2)) // Inserting characters
let newStr4 = strBuilder
```
