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

Unlike simple data types like `int` or `double`, a `String` comes with built-in abilities to work with text.  

We access these abilities using **methods**.

<br>

## How to Use a String Method

You’ve already seen something similar when using `Math.pow(...)` or `Math.round(...)`.

When we use a method on a string, the format looks like this:

```
variableName.methodName(...)
```

We read that as:

> “Take this string, and make it do something.”

For example:

```java
String name = "Alice";
System.out.println(name.length());
```

Here:
- `name` is the variable or string we are working with
- `.` means “use one of its built-in tools”
- `length()` is the tool we're using

Some methods need information **inside the parentheses** and some don’t. Some methods **give back a result** that we can use in a calculation or print.

You do not need to memorize anything about how this works behind the scenes yet. For now, just remember:

> String → dot → method → parentheses

<br>

## How Strings Store Characters

Each character in a string has a numbered **index**, starting at **0**.

```
String phrase = "JAVA IS COOL";
```

| Character | J | A | V | A | _ | I | S | _ | C | O | O | L |
|:---------:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| Index     | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10| 11|

<br>

## String Methods Refrence



### `.length()`

Tells you **how many characters** are in the string.

```java
String name = readLine("Enter your name: ");
int count = name.length();
System.out.println("Your name has " + count + " characters.");
```
<br>

### `.charAt()` – Getting a Single Character

Gets the character at a specific index.

```java
String word = "PIZZA";
System.out.println(word.charAt(0)); // P
System.out.println(word.charAt(4)); // A
```

To get the **last character**, combine with `.length()`:

```java
char last = word.charAt(word.length() - 1);
```

<br>

### `.indexOf()` – Finding Something Inside the String

#### Version 1: `indexOf("text")`

Finds the first place where the text appears.

```java
String word = "TESTING";
System.out.println(word.indexOf("S"));    // 2
System.out.println(word.indexOf("TIN"));  // 3
System.out.println(word.indexOf("Q"));    // -1 (not found)
```

Note that `.indexOf()` returns a special value of `-1` when the pattern is **not found** in the string.

#### Version 2: `indexOf("text", startingIndex)`

Starts searching **later in the string**.

```java
String word = "TESTING";
System.out.println(word.indexOf("T", 1)); // 3
```

<br>

### `.substring()` – Taking Part of a String

#### Version 1: `substring(startIndex)`

From the start index to the end.

```java
String phrase = "substring method";
System.out.println(phrase.substring(10));
// "method"
```

#### Version 2: `substring(startIndex, endIndex)`

From the start index **up to but not including** the end index.

```java
System.out.println(phrase.substring(0, 3));  // "sub"
```

<br>

## Comparing Entire Strings

### `.equals()` – Comparing Strings Properly

Do **not** use `==` to compare strings.

`==` checks memory.  
`.equals()` checks the actual text.

```java
String a = "hello";
String b = "jello";

if (a.equals(b)) {
    System.out.println("Same");
} else {
    System.out.println("Different");
}
```

<br>

### `.compareTo()` – Alphabetical Order

Tells us how two words compare alphabetically.

| Output | Meaning |
|--------|---------|
| Negative number | first word comes *before* second |
| 0 | same word |
| Positive number | first word comes *after* second |

```java
System.out.println("apple".compareTo("banana")); // negative
```

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

HINT: Remember that `.indexOf(searchPattern)` returns a value of `-1` when the `searchPattern` is not found in the string.

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
