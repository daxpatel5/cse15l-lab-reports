# Lab Report 3
> Last Edited: 12 February, 2024
> Dax Patel

## Part 1  

## The bug from lab of Week 4:  
The `static int[] reversed(int[] arr)` method  

The method as written (buggy):  
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

The tests for the method:  
```
@Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```

It is important to note that `input1` here does NOT induce failure and if it were the only test in our tester file for this particular method, it would wrongfully pass!  
Screenshot testing for just `input1`:  

```
@Test
  public void testReversed() {
    int[] input2 = {1, 2};
    assertArrayEquals(new int[]{2, 1}, ArrayExamples.reversed(input2));
  }
```
Testing it with `input2` shows that the program is buggy and fails our JUnit tests, making it a failure-inducing input! In fact any non-null array of integers would cause our method as written to fail, with a similar symptom each time where the JUnit testing would show that the actual value of all the elements in our returned array is <0> when we would expect it to be our original contents but reversed.  

>Dax Patel

