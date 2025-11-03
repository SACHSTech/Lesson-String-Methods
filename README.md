# Lesson: String Methods in Java

So far, we’ve worked mainly with numbers, booleans, and control flow (`if`, `for`, `while`).  
But many real-world programs work with text, or as we know it in Java, **strings**:

- Names
- Usernames and passwords
- Messages and chat logs
- File names
- Search queries
- Menu options

In Java, text is stored using the `String` type. Recall that a `String` is a sequence of characters stored in order, like:

```
"JAVA IS COOL"
```

Unlike primitive types (e.g., `int`, `double`, `char`), `String` has **built-in methods** that allow us to inspect and manipulate the text stored within.

We will learn the most commonly used methods:

- `length()`
- `indexOf(String)`
- `indexOf(String, int)`
- `substring(int)`
- `substring(int, int)`
- `equals(String)`
- `compareTo(String)`


<br>

## How Strings Store Characters

Each character in a String has a numbered **index**, starting at **0**.

```
String phrase = "JAVA IS COOL";
```

| Character | J | A | V | A | _ | I | S | _ | C | O | O | L |
|:---------:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| Index     | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10| 11|


<br>

## `.length()`

Returns the **number of characters** in the string.

```java
String name = readLine("Enter your name: ");
int count = name.length();
System.out.println("Your name has " + count + " characters.");
```

<br>

## `.indexOf()` – Searching Within a String

### Version 1: `indexOf(String)`

Finds the first occurrence of the target text.

```java
String word = "TESTING";
System.out.println(word.indexOf("S"));    // 2
System.out.println(word.indexOf("TIN"));  // 3
System.out.println(word.indexOf("T"));    // 0
System.out.println(word.indexOf("Q"));    // -1 (not found)
```

### Version 2: `indexOf(String, int)`

Searches **starting from a given index**.

```java
String word = "TESTING";
System.out.println(word.indexOf("T", 1)); // 3 (first T after index 1)
System.out.println(word.indexOf("E", 2)); // -1 (no E after index 2)
System.out.println(word.indexOf("N", 3)); // 5
```

<br>

## `.substring()` – Extracting Part of a String

### Version 1: `substring(start)`

Gets everything from the **start index** to the **end**.

```java
String phrase = "substring method";
System.out.println(phrase.substring(10));  // "method"
System.out.println(phrase.substring(3));   // "string method"
```

### Version 2: `substring(start, end)`

Gets characters from **start index** up to **(end index - 1)**.

The second number is **one past** where you want to stop.

```java
String phrase = "substring method";
System.out.println(phrase.substring(0, 3));   // "sub"
System.out.println(phrase.substring(3, 9));   // "string"
System.out.println(phrase.substring(10, 16)); // "method"
```

<br>

## `.equals()` – Correct Way to Compare Strings

Hold up! **Do not** use `==` to compare Strings. The comparison operator `==` is used to check memory locations. For Strings, we use `.equals()` to check *String content*.

```java
String a = "hello";
String b = "jello";

if (a.equals(b)) {
    System.out.println("Same word");
} else {
    System.out.println("Different words");
}
```

<br>

## `.compareTo()` – Alphabetical Order

Returns:

| Result                          | Meaning |
|---------------------------------|---------|
| Negative number                 | first < second |
| 0                               | first == second |
| Positive number                 | first > second |

```java
String first = "apple";
String second = "banana";

System.out.println(first.compareTo(second)); // negative value
```

This is often used for sorting words alphabetically.

<br>

# Practice Problems
Complete each program using string methods and show the expected output.

### 1. Word Length
Ask the user for a word and print how many characters it has.

**Example:**
```
Enter a word: pancake
Characters: 7
```

<br>

### 2. First Occurrence
Ask the user for a sentence and a letter. Print the index of the letter.

**Example:**
```
Enter a sentence: The sky is blue
Enter a letter: s
Index: 4
```

<br>

### 3. Find the Space
Given a first and last name, print the index of the space.

```
Enter full name: Ada Lovelace
Space at index: 3
```

<br>

### 4. Extract Family Name
Assume the name is written in East Asian order:
Family-name followed by given-name.

```
Enter your full name: Chow Yun-Fat
Family name: Chow
```

<br>

### 5. Extract Given Name
Same input as above, but print the given name.

```
Enter your full name: Chow Yun-Fat
Given name: Yun-Fat
```

<br>

### 6. Last Character
Print the last character of a word using `.length()`.

```
Enter a word: piano
Last character: o
```

<br>

### 7. Remove All Spaces
Ask the user for a sentence and print the same sentence without any spaces.

```
Enter text: I love bubble tea
Output: Ilovebubbletea
```

<br>

### 8. Count Vowels
Count how many vowels (`a`, `e`, `i`, `o`, `u`) are in a word, uppercase or lowercase.

```
Enter a word: EDUCATION
Vowel count: 5
```

<br>

### 9. Every Second Character
Print a new word made of every second character (index 0, 2, 4, ...).

```
Enter a word: strawberry
Output: srwry
```

<br>

### 10. Censored Word Filter (Challenge)
Replace each character of a banned word with the character `*` if it appears in the sentence.

```
Enter text: I really like blue cheese.
Enter banned word: blue
Output: I really like **** cheese.
```
