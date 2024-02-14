# lab report 3

Zeke Wang

## part 1 - bugs

1. A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)

```
@Test 
    public void testReversedFail() {
        int[] input1 = { 3, 4, 5 };
        assertArrayEquals(new int[]{ 5, 4, 3 }, ArrayExamples.reversed(input1));
    }
```
  
2. An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)

```
@Test 
    public void testReversedNofail() {
        int[] input1 = { 0,0,0 };
        assertArrayEquals(new int[]{ 0,0,0 }, ArrayExamples.reversed(input1));
    }
```

3. The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)

![Image](symptom.png)

4. The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)

code before: 
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
}
```
code after: 
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
        newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
}
```
Fix: The bug was in the `reversed()` method where the elements of the new array `newArray` were not correctly assigned. In the original code, the assignment was being done in the input array `arr`. The fix corrects this by assigning the reversed elements from the input array to the new array.

## part 2 - researching commands

command: `grep`

`-i` - 
![Image](symptom.png)

![Image](symptom.png)

`-c`
![Image](symptom.png)

![Image](symptom.png)

`-v`
![Image](symptom.png)

![Image](symptom.png)
`-l`
![Image](symptom.png)

![Image](symptom.png)



[website](https://man7.org/linux/man-pages/man1/grep.1.html)
