# Lab Report 3
> Last Edited: 13 February, 2024  
> Dax Patel

## Part 1 - Bugs  

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
<img width="754" alt="Screenshot 2024-02-13 at 12 18 53 PM" src="https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/9f16232e-437f-4127-8ae9-ccd339156841">  
Note that the other test in the screenshot refers to the test we wrote for another method in the same file.  

However, if we add a test for another input called `input2`, our resultant tester method becomes:  
```
  @Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));

    int[] input2 = {1, 2};
    assertArrayEquals(new int[]{2,1}, ArrayExamples.reversed(input2));
  }
```
Testing it with `input2` shows that the program is buggy and fails our JUnit tests, making it a failure-inducing input! In fact any non-null array of integers would cause our method as written to fail, with a similar symptom each time where the JUnit testing would show that the actual value of all the elements in our returned array is <0> when we would expect it to be our original contents but reversed.  

Screenshot testing for both `input1` and `input2`: 
<img width="782" alt="Screenshot 2024-02-13 at 11 55 58 AM" src="https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/6f19e46a-4b11-4d46-852e-742473975e35">

Looking at our original code, it becomes obvious where the bug stems from. While we indeed do create a new array `newArray` to store the reversed values and eventually return it, inside the for loop, instead of assigning the reversed values of `arr` to `newArray`, the opposite operation is done, which results in the argument array `arr` being assigned all zeros (the default value for the newly initialized `newArray`) and is eventually returned that way. After fixing this bug, our code should look like:  
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
The changes made to our original code are:
1. changed the assignment line within the for loop
2. returned the `newArray` instead of `arr`

For reference, our original code was:  
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

Screenshot for running our tester now:  
<img width="794" alt="Screenshot 2024-02-13 at 12 34 04 PM" src="https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/8aedd4a3-4831-4ace-bc97-71a267394f1d">  
The code now works because we have fixed both the underlying issues wiht the original implementation, namely the wrong assignment of array elements and the wrong return variable!  

## Part 2 - Researching Commands  

## Command of choice: `find`  

After researching a bit about the `find` command I found (pun intended!) that it is probably the best command to use in the specific use cases that might be useful in the future. There are 2 alternatives to the command itself:
1. `locate` which is a "simpler" command to run but only works on pre-installed databases and cannot peruse through file structures like we want.
   Source: [Source](https://unix.stackexchange.com/questions/13496/alternative-to-find)  
2.  `fd` which is a "more intuitive" alternative to `find` but it does require separate installation and cannot work on devices that do not have it installed.
   Source: [Source](https://opensource.com/article/18/6/friendly-alternative-find)

So for the purposes of this lab report, I will be exploring more interesting to use the same old `find` command!  

Usage 1: `find <dir> -type d`  
This command goes through the given directory and prints out all the directories contained within.  
Example 1:  
```
daxpatel@Daxs-MacBook-Pro cse15l-docsearch % pwd 
/Users/daxpatel/Documents/GitHub/cse15l-docsearch
daxpatel@Daxs-MacBook-Pro cse15l-docsearch % find /Users/daxpatel/Documents/GitHub/cse15l-docsearch -type d
/Users/daxpatel/Documents/GitHub/cse15l-docsearch
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/lib
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/objects
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/objects/pack
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/objects/info
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/info
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/logs
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/logs/refs
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/logs/refs/heads
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/logs/refs/remotes
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/logs/refs/remotes/origin
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/logs/refs/remotes/upstream
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/hooks
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/refs
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/refs/heads
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/refs/tags
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/refs/remotes
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/refs/remotes/origin
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/refs/remotes/upstream
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/.git/branches
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/government
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/government/About_LSC
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/government/Env_Prot_Agen
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/government/Alcohol_Problems
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/government/Gen_Account_Office
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/government/Post_Rate_Comm
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/government/Media
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/plos
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/biomed
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/911report
```
Example 2:  
```
daxpatel@Daxs-MacBook-Pro technical % pwd
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical
daxpatel@Daxs-MacBook-Pro technical % find /Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical -type d
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/government
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/government/About_LSC
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/government/Env_Prot_Agen
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/government/Alcohol_Problems
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/government/Gen_Account_Office
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/government/Post_Rate_Comm
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/government/Media
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/plos
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/biomed
/Users/daxpatel/Documents/GitHub/cse15l-docsearch/technical/911report
```
Source: [Source: RedHat](https://www.redhat.com/sysadmin/linux-find-command)  

Usage 2: `find`  
Example 1: ss goes here! 
Example 2: ss goes here!  
Source: [Link]()  

Usage 3: `find`  
Example 1: ss goes here! 
Example 2: ss goes here!  
Source: [Link]()  

Usage 4: `find`  
Example 1: ss goes here! 
Example 2: ss goes here!  
Source: [Link]()  




>Dax Patel | 13 Feb

