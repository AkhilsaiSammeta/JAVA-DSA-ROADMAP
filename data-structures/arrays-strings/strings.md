
# Strings in Java

Strings are fundamental in programming for representing and manipulating text. In Java, strings are **objects** of the `String` class.  A key characteristic of Java Strings is that they are **immutable**, meaning once a String object is created, its value cannot be changed.

## Key Characteristics of Strings in Java:

*   **Immutable:**  Once a String object is created, its content cannot be modified. Any operation that appears to modify a string actually creates a new String object.
*   **Objects of the `String` Class:** Strings in Java are not primitive data types; they are objects of the `java.lang.String` class.
*   **Sequence of Characters:** Internally, a String is represented as a sequence of `char` values.
*   **String Literals and String Objects:** Strings can be created using string literals (double quotes) or by explicitly creating `String` objects using the `new` keyword.
*   **String Pool:** Java maintains a "string pool" to efficiently store and reuse string literals.

## Creating Strings in Java

### 1. String Literals:

The most common way to create strings is using string literals, enclosed in double quotes `""`.

```java
String message = "Hello, World!";
String name = "Akhil";
String emptyString = "";


When you create a string literal, Java first checks if a string with the same value already exists in the string pool.

If it exists: The existing string from the pool is reused, and the reference is assigned to the variable.

If it doesn't exist: A new String object is created in the string pool, and its reference is assigned to the variable.

This string pool mechanism is a key optimization for string literals in Java, saving memory and improving performance.

2. Using the String Constructor (new String()):

You can explicitly create a String object using the String class constructor.

String greeting = new String("Welcome");
String anotherGreeting = new String("Welcome");
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Java
IGNORE_WHEN_COPYING_END

When you use new String(), a new String object is always created in the heap memory, even if a string with the same value already exists in the string pool. Using new String() is generally less efficient than using string literals.

Example illustrating String Pool vs. new String():

String str1 = "hello";
String str2 = "hello";
String str3 = new String("hello");
String str4 = new String("hello");

System.out.println(str1 == str2); // Output: true (both refer to the same object in the string pool)
System.out.println(str1 == str3); // Output: false (str1 is from pool, str3 is a new object)
System.out.println(str3 == str4); // Output: false (str3 and str4 are distinct new objects)
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Java
IGNORE_WHEN_COPYING_END

To compare the content of strings, always use the equals() method (or equalsIgnoreCase() for case-insensitive comparison), not ==.

Essential String Methods

The String class in Java provides a rich set of methods for manipulating strings. Here are some of the most commonly used ones:

1. length():

Returns the length of the string (number of characters).

String text = "Java String";
int length = text.length(); // length will be 11
System.out.println("Length: " + length); // Output: Length: 11
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Java
IGNORE_WHEN_COPYING_END
2. charAt(int index):

Returns the character at the specified index (0-based).

String word = "Example";
char firstChar = word.charAt(0);  // firstChar will be 'E'
char thirdChar = word.charAt(2);  // thirdChar will be 'a'
System.out.println("First char: " + firstChar); // Output: First char: E
System.out.println("Third char: " + thirdChar); // Output: Third char: a
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Java
IGNORE_WHEN_COPYING_END
3. substring(int beginIndex) and substring(int beginIndex, int endIndex):

Extracts a substring from the string.

substring(int beginIndex): Returns the substring starting from beginIndex to the end of the string.

substring(int beginIndex, int endIndex): Returns the substring starting from beginIndex (inclusive) to endIndex (exclusive).

String message = "Welcome to Java";
String sub1 = message.substring(8);       // sub1 will be "to Java"
String sub2 = message.substring(0, 7);    // sub2 will be "Welcome"
System.out.println("Substring 1: " + sub1); // Output: Substring 1: to Java
System.out.println("Substring 2: " + sub2); // Output: Substring 2: Welcome
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Java
IGNORE_WHEN_COPYING_END
4. indexOf(String str) and lastIndexOf(String str):

Finds the index of the first or last occurrence of a substring within the string. Returns -1 if the substring is not found.

String sentence = "This is a test string";
int firstIndex = sentence.indexOf("is");     // firstIndex will be 2
int lastIndex = sentence.lastIndexOf("is");   // lastIndex will be 5
int notFoundIndex = sentence.indexOf("xyz"); // notFoundIndex will be -1

System.out.println("First 'is' index: " + firstIndex);   // Output: First 'is' index: 2
System.out.println("Last 'is' index: " + lastIndex);     // Output: Last 'is' index: 5
System.out.println("Index of 'xyz': " + notFoundIndex); // Output: Index of 'xyz': -1
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Java
IGNORE_WHEN_COPYING_END
5. equals(Object obj) and equalsIgnoreCase(String anotherString):

Compares the content of two strings.

equals(Object obj): Performs a case-sensitive comparison.

equalsIgnoreCase(String anotherString): Performs a case-insensitive comparison.

Always use equals() (or equalsIgnoreCase()) to compare string content, not == (which compares references).

String s1 = "Java";
String s2 = "java";
String s3 = new String("Java");

System.out.println(s1.equals(s2));         // Output: false (case-sensitive)
System.out.println(s1.equalsIgnoreCase(s2)); // Output: true (case-insensitive)
System.out.println(s1.equals(s3));         // Output: true (content comparison)
System.out.println(s1 == s3);             // Output: false (reference comparison - different objects)
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Java
IGNORE_WHEN_COPYING_END
6. compareTo(String anotherString):

Compares two strings lexicographically (dictionary order). Returns:

0 if the strings are equal.

A negative value if the current string is lexicographically less than anotherString.

A positive value if the current string is lexicographically greater than anotherString.

String apple = "apple";
String banana = "banana";
String apple2 = "apple";

System.out.println(apple.compareTo(banana));  // Output: negative (apple comes before banana)
System.out.println(banana.compareTo(apple));  // Output: positive (banana comes after apple)
System.out.println(apple.compareTo(apple2)); // Output: 0 (strings are equal)
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Java
IGNORE_WHEN_COPYING_END
7. toLowerCase() and toUpperCase():

Converts the string to lowercase or uppercase, respectively.

String mixedCase = "HeLlO wOrLd";
String lowerCase = mixedCase.toLowerCase(); // lowerCase will be "hello world"
String upperCase = mixedCase.toUpperCase(); // upperCase will be "HELLO WORLD"

System.out.println("Lowercase: " + lowerCase); // Output: Lowercase: hello world
System.out.println("Uppercase: " + upperCase); // Output: Uppercase: HELLO WORLD
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Java
IGNORE_WHEN_COPYING_END
8. trim():

Removes leading and trailing whitespace from the string.

String spacedString = "   Hello   World!  ";
String trimmedString = spacedString.trim(); // trimmedString will be "Hello   World!" (only leading/trailing spaces removed)

System.out.println("Trimmed string: \"" + trimmedString + "\""); // Output: Trimmed string: "Hello   World!"
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Java
IGNORE_WHEN_COPYING_END
9. replace(char oldChar, char newChar) and replace(CharSequence target, CharSequence replacement):

Replaces characters or substrings within the string.

replace(char oldChar, char newChar): Replaces all occurrences of a character with another character.

replace(CharSequence target, CharSequence replacement): Replaces all occurrences of a substring with another substring.

String sentence = "Replace spaces with underscores";
String replacedChars = sentence.replace(' ', '_'); // Replaces spaces with underscores
String replacedWords = sentence.replace("spaces", "blanks"); // Replaces "spaces" with "blanks"

System.out.println("Character replaced: " + replacedChars); // Output: Character replaced: Replace_spaces_with_underscores
System.out.println("Word replaced: " + replacedWords);    // Output: Word replaced: Replace blanks with underscores
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Java
IGNORE_WHEN_COPYING_END
10. split(String regex):

Splits the string into an array of substrings based on a delimiter (regular expression).

String csvData = "apple,banana,orange,grape";
String[] fruits = csvData.split(","); // Split by comma

for (String fruit : fruits) {
    System.out.println(fruit);
}
// Output:
// apple
// banana
// orange
// grape
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Java
IGNORE_WHEN_COPYING_END
11. concat(String str) or + operator (String concatenation):

Concatenates (joins) strings together.

concat(String str): Method to concatenate.

+ operator: Overloaded for string concatenation (more commonly used for simplicity).

Important Note about String Concatenation and Immutability: Repeatedly concatenating strings using the + operator can be inefficient because it creates a new String object in each concatenation step due to immutability. For efficient string building, especially in loops, use StringBuilder or StringBuffer.

String firstName = "John";
String lastName = "Doe";

String fullName1 = firstName.concat(" ").concat(lastName); // Using concat() method
String fullName2 = firstName + " " + lastName;             // Using + operator (more common)

System.out.println("Full name 1: " + fullName1); // Output: Full name 1: John Doe
System.out.println("Full name 2: " + fullName2); // Output: Full name 2: John Doe
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Java
IGNORE_WHEN_COPYING_END
String Immutability in Detail

Why are Strings Immutable in Java?

String immutability in Java is a design decision that offers several important advantages:

Security: Immutable strings prevent malicious code from changing string values in sensitive contexts (e.g., passwords, filenames).

Thread Safety: Immutable objects are inherently thread-safe. Multiple threads can access and share String objects without the risk of data corruption because their state cannot be changed after creation.

String Pool Efficiency: Immutability is crucial for the string pool to work effectively. Since strings in the pool are immutable, it's safe to share references to them. If strings were mutable, modifying a string in the pool would affect all references to it.

Caching and Performance: Immutability allows for caching hash codes and other properties of strings, improving performance.

Use as Keys in HashMaps: Immutable strings are safe to use as keys in HashMaps and other hash-based data structures because their hash code will not change after creation.

Consequences of Immutability:

Performance Overhead for Modifications: Operations that seem to modify strings (like concatenation, replacement) actually create new String objects. For frequent string modifications, this can lead to performance overhead and garbage collection pressure. This is where StringBuilder and StringBuffer become important.

StringBuilder and StringBuffer (Mutable String Builders)

Java provides StringBuilder and StringBuffer classes for situations where you need to perform frequent modifications to strings. These classes create mutable string sequences.

StringBuilder: Not thread-safe, generally faster than StringBuffer in single-threaded environments. Preferred for most common use cases.

StringBuffer: Thread-safe, slower than StringBuilder due to synchronization overhead. Used in multi-threaded environments where thread safety is required.

Example using StringBuilder:

StringBuilder sb = new StringBuilder("Java");
sb.append(" is ");
sb.append("powerful");
sb.append("!");

String finalString = sb.toString(); // Convert StringBuilder back to String
System.out.println(finalString); // Output: Java is powerful!
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Java
IGNORE_WHEN_COPYING_END

Key Methods of StringBuilder and StringBuffer:

append(String str): Appends a string to the end.

insert(int offset, String str): Inserts a string at a specified position.

delete(int start, int end): Deletes a range of characters.

replace(int start, int end, String str): Replaces a range of characters with another string.

reverse(): Reverses the character sequence.

toString(): Converts the StringBuilder/StringBuffer to an immutable String object.

When to Use StringBuilder vs. StringBuffer:

StringBuilder: Use in most cases where you need mutable strings, especially in single-threaded applications or when thread safety is not a concern for string manipulation.

StringBuffer: Use in multi-threaded applications where multiple threads might be modifying the string concurrently and you need thread safety.

Time and Space Complexity of String Operations

String Operations (Immutable):

length(), charAt(index), substring(), indexOf(), lastIndexOf(), equals(), equalsIgnoreCase(), compareTo(), toLowerCase(), toUpperCase(), trim(): Generally O(1) or O(n), where n is the length of the string. substring() can sometimes be considered O(n) in terms of creating a new string.

replace(), split(): Can be O(n) or worse depending on the complexity of the replacement/regex and the number of replacements/splits.

String Concatenation (+ operator repeatedly): O(n^2) in the worst case if done repeatedly in a loop because of new String object creation in each step.

StringBuilder/StringBuffer Operations (Mutable):

append(), insert(), delete(), replace(), reverse(): Generally O(1) on average or O(n) in the worst case (e.g., insert() at the beginning might require shifting characters). Appending to the end is usually amortized O(1).

toString(): O(n) to create the final String object.

Space Complexity:

String: O(n) to store the characters of the string.

StringBuilder/StringBuffer: O(n) to store the mutable character sequence.

Use Cases for Strings

Strings are used extensively in programming for:

Representing text data (names, addresses, messages, documents).

Input and output operations.

Data parsing and manipulation.

Web development (HTML, XML, JSON).

File processing.

Communication protocols.

And countless other applications.

Advantages of Java Strings

Simplicity and Ease of Use: String literals and the String class provide a straightforward way to work with text.

Rich Functionality: The String class offers a wide range of built-in methods for string manipulation.

Immutability (for many scenarios): Provides security, thread safety, and efficiency through the string pool.

Disadvantages of Java Strings

Immutability (for modifications): Can lead to performance overhead when frequent string modifications are needed. Requires using StringBuilder/StringBuffer in such cases.

Object Overhead: Strings are objects, which can have slightly more overhead compared to primitive types (though this is usually negligible in most applications).

Conclusion

Strings are a fundamental and ubiquitous data type in Java. Understanding their immutability, key methods, and the use of StringBuilder/StringBuffer is crucial for efficient and effective string manipulation in Java programming. Master string operations as they are frequently used in coding interviews and real-world applications.

Next Steps:

Practice using various String methods in Java.

Experiment with StringBuilder and StringBuffer for mutable string operations.

Solve string-based coding problems.

Learn about Regular Expressions in Java for advanced string pattern matching and manipulation.
