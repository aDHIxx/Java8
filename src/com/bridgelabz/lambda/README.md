# Lambda Expressions in Java 8

Lambda expressions in Java 8 provide a concise way to write anonymous methods, making code more expressive and readable. They are particularly useful for passing functionality as arguments to methods or expressing single-method interfaces more compactly.

## Basic Syntax

The basic syntax of a lambda expression is:

```
(parameters) -> expression
```

```
(parameters) -> { statements; }
```
*Example 1: Simple Addition*

```java
// normal approach without lambda
interface Addition {
    int add(int a, int b);
}

Addition addition1 = new Addition() {
    @Override
    public int add(int a, int b) {
        return a + b;
    }
};

Addition addition2 = (a, b) -> a + b;

```
*Example 2: Runnable Interface*

```
// normal approach without lambda
Runnable runnable1 = new Runnable() {
    @Override
    public void run() {
        System.out.println("Hello from normal method!");
    }
};

// Lambda expression for the same functionality
Runnable runnable2 = () -> {
    System.out.println("Hello from lambda expression!");
};

```