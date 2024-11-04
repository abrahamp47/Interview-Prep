2024-09-10 16:13

Status:

Tags: [[Java]] [[Data Structures]]

# Java DSA Notes



![[data-structures-in-java.png]]


#### Array
Declaring an Array 

`int[] numbers = new int[5];`

#### Lists

##### Array Lists
```java
// Create an ArrayList of Strings 
ArrayList<String> fruits = new ArrayList<String>(); 

// Add items to the list
fruits.add("Apple"); 
fruits.add("Banana");
fruits.add("Cherry");

 // Print the list 
 System.out.println("Fruits: " + fruits);
 
 // Get an item (the second fruit) 
 System.out.println("Second fruit: " + fruits.get(1)); 
 
 // Change an item 
 fruits.set(0, "Apricot"); 
 
 // Remove an item 
 fruits.remove("Cherry");
```
##### Linked List

```java
// Create a LinkedList of Integers
LinkedList<Integer> numbers = new LinkedList<Integer>();

// Add items to the list
numbers.add(10);
numbers.add(20);
numbers.add(30);

// Print the list
System.out.println("Numbers: " + numbers);

// Add an item at the beginning
numbers.addFirst(5);

// Add an item at the end
numbers.addLast(40);

// Print the updated list
System.out.println("Updated numbers: " + numbers);

// Remove the first item
numbers.removeFirst();

```

#### Stack

```java
import java.util.ArrayList;

public class Stack<T> {
    private ArrayList<T> stack;

    public Stack() {
        stack = new ArrayList<T>();
    }

    // Add an item to the top of the stack
    public void push(T item) {
        stack.add(item);
    }

    // Remove and return the top item from the stack
    public T pop() {
        if (isEmpty()) {
            throw new IllegalStateException("Stack is empty");
        }
        return stack.remove(stack.size() - 1);
    }

    // Look at the top item without removing it
    public T peek() {
        if (isEmpty()) {
            throw new IllegalStateException("Stack is empty");
        }
        return stack.get(stack.size() - 1);
    }

    // Check if the stack is empty
    public boolean isEmpty() {
        return stack.isEmpty();
    }

    // Get the size of the stack
    public int size() {
        return stack.size();
    }
}
```


# References


