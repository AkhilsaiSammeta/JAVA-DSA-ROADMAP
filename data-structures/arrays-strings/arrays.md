```markdown
# Arrays in Java

Arrays are fundamental data structures in Java (and many other programming languages). They are used to store a **fixed-size, sequential collection of elements of the same data type**.  Think of an array as a numbered list of boxes, where each box can hold one item, and you can quickly access any box by its number (index).

## Key Characteristics of Arrays in Java:

*   **Fixed Size:** Once an array is created, its size cannot be changed. You must specify the size at the time of declaration.
*   **Homogeneous Data Type:**  All elements in an array must be of the same data type (e.g., all integers, all strings, all objects of a certain class).
*   **Contiguous Memory Allocation:** Array elements are stored in contiguous (adjacent) memory locations. This is what allows for efficient access using indices.
*   **Indexed Access:** Elements are accessed using their index, which starts from **0** for the first element, 1 for the second, and so on.
*   **Primitive Data Type and Object Arrays:** Arrays can store primitive data types (like `int`, `char`, `boolean`, `double`, etc.) or references to objects.

## Declaring and Initializing Arrays in Java

### 1. Declaration:

You declare an array by specifying the data type of its elements followed by square brackets `[]` and the array name.

```java
dataType[] arrayName; // Declares an array variable
```

**Example:**

```java
int[] numbers;        // Declares an integer array named 'numbers'
String[] names;       // Declares a String array named 'names'
```

**Note:** At this point, you've only declared a *reference* to an array. No actual array is created in memory yet.

### 2. Initialization (Creating the Array):

To actually create the array in memory and allocate space for elements, you need to use the `new` keyword followed by the data type and the size of the array in square brackets.

```java
arrayName = new dataType[arraySize]; // Creates an array of specified size
```

**Example (Continuing from above):**

```java
numbers = new int[5];    // Creates an integer array of size 5
names = new String[3];   // Creates a String array of size 3
```

### 3. Declaration and Initialization in One Step:

You can combine declaration and initialization in a single line:

```java
dataType[] arrayName = new dataType[arraySize];
```

**Example:**

```java
int[] scores = new int[10];   // Declares and creates an integer array of size 10
```

### 4. Initializing with Values (Array Literals):

You can also initialize an array with specific values directly during declaration using array literals (curly braces `{}`):

```java
dataType[] arrayName = {value1, value2, value3, ...};
```

**Example:**

```java
int[] ages = {25, 30, 22, 28}; // Creates an integer array and initializes it with values
String[] daysOfWeek = {"Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"};
```

**Note:** When using array literals, you **don't** specify the size using `new dataType[size]`. The size is automatically determined by the number of values provided.

## Accessing Array Elements

You access individual elements of an array using their index within square brackets `[]`. Remember that indexing starts from 0.

```java
arrayName[index];
```

**Example:**

```java
int[] numbers = {10, 20, 30, 40, 50};

int firstElement = numbers[0]; // firstElement will be 10
int thirdElement = numbers[2]; // thirdElement will be 30

System.out.println("First element: " + firstElement); // Output: First element: 10
System.out.println("Third element: " + thirdElement); // Output: Third element: 30
```

**Important:** Trying to access an index that is out of bounds (less than 0 or greater than or equal to the array's length) will result in an `ArrayIndexOutOfBoundsException` at runtime.

## Iterating Through Arrays

You can use loops to iterate through all elements of an array. The most common loop for arrays is the `for` loop.

### 1. Using a `for` loop with index:

```java
int[] numbers = {1, 2, 3, 4, 5};

for (int i = 0; i < numbers.length; i++) {
    System.out.println("Element at index " + i + ": " + numbers[i]);
}
```

`numbers.length` gives you the size (number of elements) of the array.

### 2. Using an Enhanced `for` loop (for-each loop):

The enhanced `for` loop provides a more concise way to iterate through arrays (and collections).

```java
int[] numbers = {1, 2, 3, 4, 5};

for (int number : numbers) {
    System.out.println("Element: " + number);
}
```

The enhanced `for` loop iterates through each element in the array directly, without needing to use indices explicitly.

## Time and Space Complexity of Array Operations

*   **Accessing an element by index:** **O(1)** - Constant time.  Arrays provide direct access to elements because of contiguous memory allocation and indexing.
*   **Insertion at the end (if there is space):** **O(1)** - Constant time on average. In Java, standard arrays are fixed size. If you're using something like `ArrayList` (which is dynamically resizable), appending to the end is often O(1) on average, but can be O(n) in the worst case if resizing is needed. For fixed-size arrays, you can't truly "insert" if full.
*   **Insertion at the beginning or middle:** **O(n)** - Linear time in the worst case. You would need to shift existing elements to make space for the new element. This is generally not efficient for standard Java arrays.
*   **Deletion at the end:**  **O(1)** - Constant time (conceptually, you just "forget" about the last element, or if you were managing a "logical size" you'd decrement it).  Again, for fixed-size arrays, you can't truly "delete" in the sense of resizing.
*   **Deletion at the beginning or middle:** **O(n)** - Linear time in the worst case. You would need to shift elements to fill the gap left by the deleted element.
*   **Searching (linear search):** **O(n)** - Linear time in the worst case. You might need to examine every element to find the target.
*   **Space Complexity:** **O(n)** - Linear space. The space required to store an array is proportional to the number of elements it holds.

## Use Cases for Arrays

Arrays are suitable when:

*   You need to store a collection of elements of the same type.
*   The size of the collection is known and fixed in advance.
*   You require fast access to elements by index (O(1) access time).
*   You need to implement other data structures like stacks, queues, or hash tables.
*   You are working with algorithms that require sequential data storage (e.g., some sorting algorithms).

## Advantages of Arrays

*   **Simple and Efficient:** Arrays are conceptually simple and provide efficient random access.
*   **Fast Element Access:** O(1) access time by index is very fast.
*   **Memory Efficiency:** Contiguous memory allocation can be more memory-efficient than some other data structures (especially for primitive types).

## Disadvantages of Arrays

*   **Fixed Size:** The fixed size is a major limitation. You cannot easily add or remove elements once the array is created without creating a new array and copying elements.
*   **Insertion and Deletion Inefficiency:** Inserting or deleting elements in the middle of an array is inefficient due to the need to shift elements.
*   **Homogeneous Data Type:** Arrays can only store elements of the same data type.

## Conclusion

Arrays are a fundamental building block in programming. While they have limitations due to their fixed size and insertion/deletion costs, their simplicity and fast indexed access make them essential for many programming tasks and as a foundation for more complex data structures.  For situations where you need a dynamically resizable collection, consider using `ArrayList` or other Java Collection Framework classes.

---

**Next Steps:**

*   Practice creating and manipulating arrays in Java.
*   Try solving some basic array-based problems.
*   Explore multi-dimensional arrays in Java.
*   Compare arrays to other data structures like `ArrayList` when you learn about them.

```
```markdown
## Multi-Dimensional Arrays (2D Arrays - Matrices)

Java supports multi-dimensional arrays, which are essentially arrays of arrays. The most common type is the **2D array**, often visualized as a **matrix** or a table with rows and columns.

### Declaring and Initializing 2D Arrays

#### 1. Declaration:

```java
dataType[][] arrayName; // Declares a 2D array variable
```

**Example:**

```java
int[][] matrix;       // Declares a 2D integer array named 'matrix'
```

#### 2. Initialization:

```java
arrayName = new dataType[numRows][numColumns]; // Creates a 2D array with specified rows and columns
```

**Example:**

```java
matrix = new int[3][4];  // Creates a 2D integer array with 3 rows and 4 columns
```

#### 3. Declaration and Initialization in One Step:

```java
dataType[][] arrayName = new dataType[numRows][numColumns];
```

**Example:**

```java
int[][] board = new int[8][8]; // Creates an 8x8 integer matrix (like a chessboard)
```

#### 4. Initializing with Values (2D Array Literals):

You can initialize a 2D array with values using nested curly braces:

```java
dataType[][] arrayName = {
    {value1_row1_col1, value2_row1_col2, ...}, // Row 1
    {value1_row2_col1, value2_row2_col2, ...}, // Row 2
    ...
};
```

**Example:**

```java
int[][] matrixValues = {
    {1, 2, 3},      // Row 0
    {4, 5, 6},      // Row 1
    {7, 8, 9}       // Row 2
};
```

### Accessing Elements in 2D Arrays

You access elements in a 2D array using **two indices**: one for the row and one for the column, both starting from 0.

```java
arrayName[rowIndex][columnIndex];
```

**Example:**

```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

int element = matrix[1][2]; // element will be 6 (row index 1, column index 2)
System.out.println("Element at [1][2]: " + element); // Output: Element at [1][2]: 6
```

### Iterating Through 2D Arrays

You typically use nested loops to iterate through 2D arrays.

#### 1. Nested `for` loops with indices:

```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

for (int i = 0; i < matrix.length; i++) { // Iterate through rows
    for (int j = 0; j < matrix[i].length; j++) { // Iterate through columns in each row
        System.out.print(matrix[i][j] + " ");
    }
    System.out.println(); // Move to the next line after each row
}
```

`matrix.length` gives the number of rows. `matrix[i].length` gives the number of columns in the i-th row.

#### 2. Enhanced nested `for` loops:

```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

for (int[] row : matrix) { // Iterate through each row (which is itself an array)
    for (int element : row) { // Iterate through elements in the current row
        System.out.print(element + " ");
    }
    System.out.println();
}
```

## Arrays and Methods in Java

### Passing Arrays to Methods

When you pass an array to a method in Java, you are actually passing a **reference** to the array. This means that if the method modifies the array elements, those changes will be reflected in the original array outside the method. Arrays in Java are passed **by reference**.

**Example:**

```java
public class ArrayMethods {

    public static void modifyArray(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            arr[i] = arr[i] * 2; // Modifying array elements inside the method
        }
    }

    public static void printArray(int[] arr) {
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        int[] myArray = {1, 2, 3, 4, 5};
        System.out.print("Original array: ");
        printArray(myArray); // Output: Original array: 1 2 3 4 5

        modifyArray(myArray); // Passing the array to the method

        System.out.print("Modified array: ");
        printArray(myArray); // Output: Modified array: 2 4 6 8 10 (Changes are reflected!)
    }
}
```

### Returning Arrays from Methods

Methods can also return arrays. The return type of the method should be declared as an array type.

**Example:**

```java
public class ArrayMethods {

    public static int[] createSquaredArray(int size) {
        int[] squaredArray = new int[size];
        for (int i = 0; i < size; i++) {
            squaredArray[i] = (i + 1) * (i + 1); // Square numbers from 1 to size
        }
        return squaredArray; // Returning the created array
    }

    public static void printArray(int[] arr) {
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        int[] squares = createSquaredArray(5); // Calling the method to get an array
        System.out.print("Squared array: ");
        printArray(squares); // Output: Squared array: 1 4 9 16 25
    }
}
```

## Common Array Operations (Examples)

Let's look at some common operations you might perform on arrays.

### 1. Finding the Minimum and Maximum Element

```java
public class ArrayOperations {

    public static int findMinimum(int[] arr) {
        if (arr == null || arr.length == 0) {
            throw new IllegalArgumentException("Array cannot be null or empty");
        }
        int min = arr[0]; // Assume the first element is the minimum initially
        for (int i = 1; i < arr.length; i++) {
            if (arr[i] < min) {
                min = arr[i]; // Update min if a smaller element is found
            }
        }
        return min;
    }

    public static int findMaximum(int[] arr) {
        if (arr == null || arr.length == 0) {
            throw new IllegalArgumentException("Array cannot be null or empty");
        }
        int max = arr[0]; // Assume the first element is the maximum initially
        for (int i = 1; i < arr.length; i++) {
            if (arr[i] > max) {
                max = arr[i]; // Update max if a larger element is found
            }
        }
        return max;
    }

    public static void main(String[] args) {
        int[] numbers = {5, 2, 8, 1, 9, 4};
        System.out.println("Minimum element: " + findMinimum(numbers)); // Output: Minimum element: 1
        System.out.println("Maximum element: " + findMaximum(numbers)); // Output: Maximum element: 9
    }
}
```

### 2. Summing Array Elements

```java
public class ArrayOperations {

    public static int sumArray(int[] arr) {
        int sum = 0;
        for (int num : arr) {
            sum += num; // Add each element to the sum
        }
        return sum;
    }

    public static void main(String[] args) {
        int[] values = {10, 20, 30, 40, 50};
        System.out.println("Sum of elements: " + sumArray(values)); // Output: Sum of elements: 150
    }
}
```

### 3. Reversing an Array (In-place)

```java
public class ArrayOperations {

    public static void reverseArray(int[] arr) {
        int start = 0;
        int end = arr.length - 1;
        while (start < end) {
            // Swap elements at start and end indices
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;
            start++;
            end--;
        }
    }

    public static void printArray(int[] arr) {
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        int[] data = {1, 2, 3, 4, 5};
        System.out.print("Original array: ");
        printArray(data); // Output: Original array: 1 2 3 4 5

        reverseArray(data);
        System.out.print("Reversed array: ");
        printArray(data); // Output: Reversed array: 5 4 3 2 1
    }
}
```

### 4. Copying an Array (Shallow Copy for Primitive Arrays)

For arrays of primitive types, a simple assignment using `Arrays.copyOf()` or `System.arraycopy()` performs a **shallow copy**, which is sufficient.  For arrays of objects, you need to be aware of shallow vs. deep copy (which is a more advanced topic).

```java
import java.util.Arrays;

public class ArrayOperations {

    public static void main(String[] args) {
        int[] originalArray = {1, 2, 3, 4, 5};

        // Using Arrays.copyOf()
        int[] copiedArray1 = Arrays.copyOf(originalArray, originalArray.length);

        // Using System.arraycopy()
        int[] copiedArray2 = new int[originalArray.length];
        System.arraycopy(originalArray, 0, copiedArray2, 0, originalArray.length);

        // Verify copies
        System.out.print("Original array: ");
        printArray(originalArray); // Output: Original array: 1 2 3 4 5
        System.out.print("Copied array 1: ");
        printArray(copiedArray1); // Output: Copied array 1: 1 2 3 4 5
        System.out.print("Copied array 2: ");
        printArray(copiedArray2); // Output: Copied array 2: 1 2 3 4 5

        // Modify original array - copies are independent (for primitive arrays)
        originalArray[0] = 100;
        System.out.print("Original array (modified): ");
        printArray(originalArray); // Output: Original array (modified): 100 2 3 4 5
        System.out.print("Copied array 1 (after original modified): ");
        printArray(copiedArray1); // Output: Copied array 1 (after original modified): 1 2 3 4 5 (Unchanged)
    }

    public static void printArray(int[] arr) {
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println();
    }
}
```

## Arrays vs. ArrayList (Brief Introduction)

As mentioned earlier, a major limitation of arrays is their **fixed size**.  If you need a dynamic array (a collection that can grow or shrink in size as needed), Java provides the `ArrayList` class (part of the Java Collections Framework).

**Key differences in brief:**

| Feature          | Array                                  | `ArrayList`                               |
| ---------------- | -------------------------------------- | ------------------------------------------- |
| Size             | Fixed size after creation              | Dynamically resizable (grows/shrinks)       |
| Data Type        | Homogeneous (primitive or objects)      | Objects only (internally uses Object array) |
| Functionality    | Basic, built-in language feature        | Rich set of methods (add, remove, etc.)    |
| Part of          | Core language                          | Java Collections Framework                  |
| Performance      | Generally faster for basic operations   | Slightly slower due to overhead of dynamic resizing and object wrapping (for primitives before autoboxing improvements) |
| Usage Scenarios | Fixed-size collections, performance-critical code, when type safety is paramount and known at compile time for primitives | Dynamic collections, flexibility in size, when you need collection framework methods |

You will learn more about `ArrayList` in a later section on the Java Collections Framework. For now, understand that `ArrayList` is a powerful alternative when you need a dynamic array in Java.

---
