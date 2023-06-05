# Lab Report 5 -Debugging Scenario and Reflection 

## Part 1 - Debugging Scenario 

### Student Post
<br /> Title: Help with code 
<br /> Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.

<br /> Code: 

```
public class Bug {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};
        int sum = 0;
        
        for (int i = 0; i <= numbers.length; i++) {
            sum += numbers[i];
        }
        
        System.out.println("Sum: " + sum);
    }
}

```

<br /> Commmand ran: 

```

bash run.sh

```

<br /> Base run.sh excuting this command:

```
javac Bug.java
java Bug

```




<br /> Output in terminal : 

```
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 5 out of bounds for length 5
        at Bug.main(Bug.java:8)
```


<br /> Detail the failure-inducing input and context.

<br /> When I ran the commands `javac Bug.java`  `java Bug`  I expected the program to calculate the sum of the numbers in the array and display it as output. However it returned this output message instead. 

```
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 5 out of bounds for length 5
        at Bug.main(Bug.java:8)
```


### TA response: 
<br /> You should take a look at the for loop that you have created. What does each part of the for loop do/ mean? Once you undertand the role of each part
you should be able to see where you error lies. 
<br /> As a reminder this what makes up a for loop: 
```
for (initialization; condition; iteration) {
    // loop body
}

```
1. Initialization: This part is executed only once at the beginning of the loop. It is used to initialize the loop variable or variables and set their initial values.

2. Condition: The condition is evaluated before each iteration of the loop. If the condition is true, the loop body is executed; otherwise, the loop terminates. The condition is typically a Boolean expression or a comparison.

3. Iteration: After each iteration of the loop body, this part is executed. It is responsible for updating the loop variable or variables. Typically, it increments or decrements the loop variable, but it can perform any operation that modifies the loop variable(s).

### Student Second Reponse 

Thank you for the infomation. I realized where I have went wrong. The failure is caused by an off-by-one error in the for loop condition in the Java file. The condition i <= numbers.length should be i < numbers.length to prevent accessing an index outside the bounds of the array.

This is now my fixed code: 

```
public class Bug {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};
        int sum = 0;
        
        for (int i = 0; i < numbers.length; i++) {
            sum += numbers[i];
        }
        
        System.out.println("Sum: " + sum);
    }
}

```
### Information needed about the setup

File & Directory Structure:
```
- project/
  - Bug.java
   - run.sh
```

Contents of each file before fixing the bug:

<br /> Bug.java:
```
public class Bug {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};
        int sum = 0;
        
        for (int i = 0; i <= numbers.length; i++) {
            sum += numbers[i];
        }
        
        System.out.println("Sum: " + sum);
    }
}
```
<br /> run.sh:
```
#!/bin/bash

javac Bug.java
java Bug

```

Command line to trigger the bug:

```
bash run.sh

```

Description of what to edit to fix the bug:
<br /> In the Bug.java file, change the condition in the for loop from i <= numbers.length to i < numbers.length to ensure that the loop iterates within the bounds of the array.

<br /> Fixed Bug.java:
```
public class Bug {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};
        int sum = 0;
        
        for (int i = 0; i < numbers.length; i++) {
            sum += numbers[i];
        }
        
        System.out.println("Sum: " + sum);
    }
}
```

Decription: 
```
After making this change, the bug will be fixed, and the program will correctly calculate the sum of the numbers without throwing an ArrayIndexOutOfBoundsException.
```

## Reflection 

From lab,  I learned about the grep command and its usage in Linux systems. grep is used to search for specific text patterns within files or directories by providing it with a pattern to search for. The -i option enables case-insensitive searching, allowing matches regardless of letter case. The -v option inverts matches and displays lines that do not contain the specified pattern. The -n option displays line numbers along with the matched lines. The -r option enables recursive searching in directories and subdirectories. Overall, grep is a powerful command-line tool for efficient text pattern searching. I think I was able to really understand these commands because I was forced to write a whole lab report on it. 


