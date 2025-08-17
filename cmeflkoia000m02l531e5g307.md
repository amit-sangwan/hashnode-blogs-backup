---
title: "Java - Quick Refresher"
seoTitle: "Java Quick Reference Guide"
seoDescription: "Java guide with syntax and code for variables, data types, control structures, arrays, collections, and more"
datePublished: Sun Aug 17 2025 11:23:12 GMT+0000 (Coordinated Universal Time)
cuid: cmeflkoia000m02l531e5g307
slug: java-quick-refresher
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1755429628666/0d7a90f6-8201-4a58-8b32-c7c599195e62.jpeg
tags: java-programming-collections-sdet-dsa-refresher-notes

---

This blog is a **quick refresher guide** for Java concepts. It contains short, to-the-point notes and must-know syntax for **variables, data types, control statements, strings, arrays, collections, ArrayList, HashMap, StringBuilder, StringBuffer**, and more.

The goal is **speedy revision** – no long explanations, just **clean examples, important methods, and ready-to-use snippets**.

## **1\. Variables**

A **variable** is a named memory location that stores a value. Variables allow you to store and manipulate data in your program.

**Syntax:**

```http
dataType variableName = value;
```

### **Types of Variables**

1. **Local Variables**  
    Declared inside a method, constructor, or block. Scope limited to that block.
    

```http
void method() {
    int x = 10; // local
}
```

2. **Instance Variables**  
    Declared inside a class but outside any method. Belong to objects.
    

```http
class Test {
    int count; // instance variable
}
```

3. **Static (Class) Variables**  
    Declared with `static` keyword. Shared across all instances of a class.
    

```http
class Test {
    static int counter = 0;
}
```

---

## **2\. Data Types**

Java is **statically typed**, so every variable must have a type.

### **Primitive Data Types**

| Type | Size | Range | Default | Example |
| --- | --- | --- | --- | --- |
| byte | 1 byte | \-128 to 127 | 0 | byte b = 100; |
| short | 2 bytes | \-32,768 to 32,767 | 0 | short s = 1000; |
| int | 4 bytes | \-2³¹ to 2³¹-1 | 0 | int n = 100000; |
| long | 8 bytes | \-2⁶³ to 2⁶³-1 | 0L | long l = 100000L; |
| float | 4 bytes | ~6–7 decimal digits | 0.0f | float f = 3.14f; |
| double | 8 bytes | ~15–16 decimal digits | 0.0d | double d = 3.14159; |
| char | 2 bytes | Unicode 0–65,535 | '\\u0000' | char c = 'A'; |
| boolean | 1 bit | true/false | false | boolean flag = true; |

> **Notes:** Use `L` for long, `f` for float. `char` stores Unicode. `boolean` is strictly `true/false`.

### **Non-Primitive (Reference) Data Types**

* Objects, arrays, strings, wrapper classes.
    

```http
String str = "Hello";
int[] arr = {1,2,3};
Integer num = 10;
```

### **Type Casting**

* **Implicit (Widening)**: smaller → larger (safe)
    

```http
int a = 10;
double b = a; // int -> double
```

* **Explicit (Narrowing)**: larger → smaller (may lose data)
    

```http
double x = 10.5;
int y = (int) x; // double -> int
```

**Useful One-Liners**

```http
int a=5, b=10;
final int MAX = 100; // constant
```

---

## **3\. Control & Conditional Statements**

Control statements manage the **flow of execution**.

### **Decision-Making Statements**

**if**

```http
if (condition) { /* executes if true */ }
```

**if-else**

```http
if (condition) { /* true */ } else { /* false */ }
```

**if-else-if ladder**

```http
if (cond1) { } 
else if (cond2) { } 
else { }
```

**switch**

```http
switch(expression) {
    case value1: break;
    case value2: break;
    default: break;
}
```

---

## **4\. Loops**

Loops are used to **repeat code blocks**.

* **for loop**
    

```http
for (int i=0; i<5; i++) { System.out.println(i); }
```

* **while loop**
    

```http
int i=0;
while(i<5) { System.out.println(i); i++; }
```

* **do-while loop**
    

```http
int i=0;
do { System.out.println(i); i++; } while(i<5);
```

* **Enhanced for loop**
    

```http
int[] arr = {10,20,30};
for (int n : arr) { System.out.println(n); }
```

---

## **5\. Jump Statements**

* `break` → exit loop/switch
    
* `continue` → skip current iteration
    
* `return` → exit method
    

---

## **6\. Strings**

Strings are **immutable objects** in Java (`java.lang.String`).

**String Creation**

```http
String s1 = "Hello";        // literal
String s2 = new String("Hello"); // heap
```

**Common Methods**

| Method | Description | Example |
| --- | --- | --- |
| length() | String length | "Hello".length() → 5 |
| charAt(i) | Char at index | "Java".charAt(2) → 'v' |
| substring(b,e) | Substring \[b,e) | "abcdef".substring(1,4) → "bcd" |
| contains(str) | Check substring | "Hello".contains("ell") → true |
| equals(str) | Compare content | "abc".equals("abc") → true |
| equalsIgnoreCase(str) | Case-insensitive | "Java".equalsIgnoreCase("java") → true |
| compareTo(str) | Lexicographic compare | "abc".compareTo("abd") → -1 |
| indexOf(ch) | First index | "banana".indexOf('a') → 1 |
| lastIndexOf(ch) | Last index | "banana".lastIndexOf('a') → 5 |
| toUpperCase() | Uppercase | "java".toUpperCase() → "JAVA" |
| toLowerCase() | Lowercase | "JAVA".toLowerCase() → "java" |
| trim() | Remove spaces | " hi ".trim() → "hi" |
| replace(old,new) | Replace char | "java".replace('a','o') → "jovo" |
| split(regex) | Split string | "a,b,c".split(",") → {"a","b","c"} |
| isEmpty() | Check empty | "".isEmpty() → true |

* ## StringBuilder vs StringBuffer
    
    Both are used for **mutable strings** (unlike `String`, which is immutable).
    
    ### StringBuilder (Not Thread-Safe, Faster)
    
    * Single-threaded use
        
    * Better performance
        
    
    ```http
    StringBuilder sb = new StringBuilder("Hello");
    sb.append(" World");
    sb.insert(5, " Java");
    sb.delete(5, 10);
    System.out.println(sb.toString()); // Hello
    ```
    
    ### StringBuffer (Thread-Safe, Slower)
    
    * Synchronized methods → safe in multi-threaded environments
        
    
    ```http
    StringBuffer sbf = new StringBuffer("Hi");
    sbf.append(" Amit");
    sbf.reverse();
    System.out.println(sbf.toString()); // timA iH
    ```
    
    ---
    
    ## When to Use
    
    * **String** → Immutable text (constants, messages, keys)
        
    * **StringBuilder** → Fast string manipulation in single-threaded apps
        
    * **StringBuffer** → Safe string manipulation in multi-threaded apps
        
    

---

## **7\. Arrays**

**Definition:** A Collection of elements of the same type. Fixed size. Index starts at 0.

**Declaration & Initialization**

```http
int[] arr = new int[5];
int[] nums = {1,2,3,4,5};
```

**Access & Traversal**

```http
System.out.println(nums[0]);
nums[2] = 10;

for (int i=0; i<nums.length; i++) System.out.print(nums[i]+" ");
for (int n : nums) System.out.print(n+" ");
```

**Multidimensional Arrays**

```http
int[][] matrix = {{1,2,3},{4,5,6},{7,8,9}};
System.out.println(matrix[1][2]); // 6
```

**Useful Arrays Class Methods**

```http
Arrays.sort(arr);
int idx = Arrays.binarySearch(arr, 3);
Arrays.fill(arr, 9);
boolean eq = Arrays.equals(arr1, arr2);
System.out.println(Arrays.toString(arr));
```

**Common Tricks**

* Reverse, find max/min, sum elements
    

---

## **8\. ArrayList & HashMap**

### ArrayList (java.util)

* **Resizable array** implementation (dynamic size, unlike arrays).
    
* **Duplicates allowed, maintains insertion order.**
    
* **Not synchronized** (use `Collections.synchronizedList()` if needed).
    

### Common Methods

```http
ArrayList<String> list = new ArrayList<>();

// Add
list.add("A");
list.add("B");
list.add(1, "X");  // insert at index

// Get
String val = list.get(0);

// Update
list.set(1, "Y");

// Remove
list.remove("A");   // by value
list.remove(0);     // by index

// Size
int size = list.size();

// Contains
boolean hasB = list.contains("B");

// Iterate
for (String s : list) System.out.println(s);
list.forEach(System.out::println);

// Convert to Array
String[] arr = list.toArray(new String[0]);

// Clear
list.clear();
```

### Example

```http
ArrayList<Integer> nums = new ArrayList<>(Arrays.asList(10, 20, 30));
nums.add(40);         // [10, 20, 30, 40]
nums.remove(1);       // [10, 30, 40]
System.out.println(nums.get(1));  // 30
```

---

## HashMap (java.util)

* **Key-Value pair** storage.
    
* **No duplicate keys, values can repeat.**
    
* **Null key (only 1 allowed), multiple null values allowed.**
    
* **Unordered (no guarantee of order).**
    

### Common Methods

```http
HashMap<Integer, String> map = new HashMap<>();

// Put
map.put(1, "A");
map.put(2, "B");
map.put(3, "C");

// Get
String val = map.get(2);   // "B"

// Update (overwrites if key exists)
map.put(2, "Z");           // {1=A, 2=Z, 3=C}

// Remove
map.remove(3);

// Contains
boolean hasKey = map.containsKey(1);
boolean hasVal = map.containsValue("A");

// Iterate
for (Map.Entry<Integer, String> e : map.entrySet())
    System.out.println(e.getKey() + " -> " + e.getValue());

map.forEach((k,v) -> System.out.println(k + ":" + v));

// Keys and Values
Set<Integer> keys = map.keySet();
Collection<String> vals = map.values();

// Size
int size = map.size();

// Clear
map.clear();
```

### Example

```http
HashMap<String, Integer> scores = new HashMap<>();
scores.put("Amit", 90);
scores.put("Ravi", 85);
scores.put("Neha", 95);

System.out.println(scores.get("Neha")); // 95
scores.put("Ravi", 88);                 // update value
System.out.println(scores.containsKey("Amit")); // true
```

---

---

## **9\. Java Collections Overview**

| Interface | Common Implementations | Underlying Structure | Initial Size | Increment / Load Factor |
| --- | --- | --- | --- | --- |
| List | ArrayList, LinkedList, Vector, Stack | Array / Linked List | 10 (ArrayList) | Doubles size |
| Set | HashSet, LinkedHashSet, TreeSet | Hash table / Red-Black Tree | 16 (HashSet) | 0.75 (load factor) |
| Queue | PriorityQueue, LinkedList | Heap / Linked List | N/A | N/A |
| Deque | ArrayDeque | Array | N/A | N/A |
| Map | HashMap, TreeMap, LinkedHashMap, Hashtable | Hash Table / Red-Black Tree | 16 (HashMap) | 0.75 |

**Common Collection Methods**

```http
add(), addAll(), remove(), removeAll(), clear(), size(), contains(), containsAll(), iterator(), forEach(), toArray(), equals(), hashCode(), toString()
```

---

### **ArrayList vs LinkedList**

* **ArrayList**: Fast retrieval, slow insertion/deletion in the middle
    
* **LinkedList**: Fast insertion/deletion, slow retrieval
    

**LinkedList Methods**

```http
addFirst(), addLast(), getFirst(), getLast(), removeFirst(), removeLast()
offer(), offerFirst(), offerLast()
poll(), pollFirst(), pollLast()
peek(), peekFirst(), peekLast()
descendingIterator()
```

---