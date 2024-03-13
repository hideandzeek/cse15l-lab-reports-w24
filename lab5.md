# lab report 5

Zeke Wang

### Part 1

1. Student's original post:

Hello everyone, I have an issue with my Java program. I'm trying to calculate the factorial of a number, but when I run my code, I get an infinite loop of error messages. Here's a screenshot of the error and my code:

code:
```
public class Factorial {
    public static void main(String[] args) {
        int n = 5;
        System.out.println("Factorial of " + n + " is: " + calculateFactorial(n));
    }

    public static int calculateFactorial(int num) {
        return num * calculateFactorial(num - 1);
    }
}
```

error: 

2. TA's response:
It looks like your program is encountering a ```StackOverflowError``` error due to infinite recursion in your calculateFactorial method. To debug, try running your program with a smaller input value. Use ```javac Factorial.java``` and ```java Factorial``` commands to compile and run your program with a smaller input value again. Also, take a look at your calculateFactorial method and ensure there's a base case to break out of the recursion.



### Part 2
