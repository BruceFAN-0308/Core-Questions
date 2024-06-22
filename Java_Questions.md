### 1. Why is Java a platform independent language?

Java is a cross-platform language. The Java complier complies the code and make the code convert to platform-independent byte code. And the byte code runs in JVM. JVM can run in mutiple systems.



### 2. Why is Java not a pure object oriented language?

Because Java has primitive data type ( byte, boolean, char, short, int, float, long, and double )



### 3. Difference between Heap and Stack Memory in java. And how java utilizes this.

Heap: Heap is the place that store the instance. That means when we create a object, this object will store in heap . And heap is unique in JVM. So different thread can use the share object that stored in heap.

Stack: Every thread has an independent stack. Every thread controls its own stack. Stack is used to store the temporary data and the data.

Different:

1. Heap is unique in JVM. Stack is not. Every thread has a stack.
2. Heap stores instance. Stack store temporary data.



### 4. What do you understand by an instance variable and a local variable?

Instance variable can be used in every place in a class. Local variable can only be used in a function or an instruction, the other functions in class can not use this variable.



### 5. What are the default values assigned to variables and instances in java?

There is not default values in instances and variable. ( except the primitive data type ) We should instance the object and give the object values, otherwise the construction function has default value.



### 6. What do you mean by data encapsulation?

Make the data is private. We can only use the function to access the variable in object, such as get and set function.



### 7. What is different between equals() and '=='?

We use the '==' to compare the values. But OOP's everything is object. The value is inside of object. So we can not just compare two object by '==' even though their valuas are same. Because object is stored by different ways in memory. Objects' memory is different, '==' will return false. We should use equals() to compare the data inside of object. Equals() only compares the values.



### 8. What is different between overloading and overriding?

Overloading means a object can has many functions using the same name, but these function's input has to be different. Construction function is a sample.

Overriding means the son class or the implement class override a function. This function has to have same name, same input and same return. But we can change the function logic.



### 9. Explain the final keyword.

a variable with final can not be changed. a function with final can not be overridden. a class with final can not extend.



### 10. Can static function be overloaded or overridden?

static function can be overloaded. but can not be overridden.



### 11. Why String is final?

1. We can use String pool. If a string value is created. We can just use this string in string pool without creating.
2. Thread-safe.
3. String is always as key in HashMap or other hash collections. Immutable is good to calculate the hash value.



### 12. String, StringBuilder, StringBuffer

String is immutable. StringBuilder and StringBuffer are variable. StringBuffer is Thread-safe, StringBuilder is not.

If we want to change the string value, we should use StringBuilder and StringBuffer.



### 13. What is singleton? How to code a singleton class?

Singleton class means no matter how many times this class is created. This class will always return a same object, which means this object in unique in JVM. And Spring framework uses singleton by default.

Double  Checked Locking

```java
public class Singleton {
    private volatile static Singleton uniqueSingleton;

    private Singleton() {
    }

    public Singleton getInstance() {
        if (uniqueSingleton == null) {
            synchronized (Singleton.class) {
                if (null == uniqueSingleton) {
                    uniqueSingleton = new Singleton();   // error
                }
            }
        }
        return uniqueSingleton;
    }
}
```

