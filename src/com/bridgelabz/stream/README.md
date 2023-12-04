## Stream and Filter Operation

### Stream
A Stream in Java represents a sequence of elements and supports various operations to perform computations on those elements. It is not a data structure; instead, it processes elements from a source (like a collection) in a functional style.

### Filter Operation
The filter operation is an intermediate operation in the Stream API. It's used to create a new stream by selecting elements from the original stream that satisfy a given predicate. The predicate is a boolean-valued function that determines whether an element should be included in the resulting stream.

**Syntax:**
```
Stream<T> filter(Predicate<? super T> predicate)
```
**Example:**
```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class StreamFilterExample {
    public static void main(String[] args) {
        List<String> fruits = Arrays.asList("Apple", "Banana", "Orange", "Grapes", "Kiwi", "Mango");

        // Using filter to select only fruits with more than 5 characters
        List<String> longFruits = fruits.stream() // Creating a stream
                .filter(fruit -> fruit.length() > 5) // Filtering based on length
                .collect(Collectors.toList()); // Collecting the result into a list

        // Print the result
        System.out.println("Fruits with more than 5 characters: " + longFruits);
    }
}
```

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class BasicFilterExample {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // Using filter to select only even numbers
        List<Integer> evenNumbers = numbers.stream() // Creating a stream
                .filter(number -> number % 2 == 0) // Filtering based on remainder
                .collect(Collectors.toList()); // Collecting the result into a list

        // Print the result
        System.out.println("Even Numbers: " + evenNumbers);
    }
}
```

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }
}

public class ObjectFilterExample {
    public static void main(String[] args) {
        List<Person> people = Arrays.asList(
                new Person("Alice", 25),
                new Person("Bob", 30),
                new Person("Charlie", 18),
                new Person("David", 40)
        );

        // Using filter to select only adults (age >= 18)
        List<Person> adults = people.stream() 
                .filter(person -> person.getAge() >= 18) // Filtering based on age
                .collect(Collectors.toList());

        // Print the result
        System.out.println("Adults: " + adults.stream().map(Person::getName).collect(Collectors.toList()));
    }
}

```