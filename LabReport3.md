## **In this Lab Report, we are tasked with two individual assignments. The first will be to demonstrate bugs, symptoms, junit testing input, showing the bug beforehand, as well as how to fix such a bug. The second section revolves around researching different commands such as less, find, grep, etc. Here is the exploration of the bug I chose from Week 4 Lab, as well as the results I found from researching various commands.**

## **1) Bugs Examination: ArrayReversedInPlace**

**1a) A failure-inducing input for ArrayReversedInPlace**
- One Such failure-inducing input for ```ArrayReversedInPlace``` would be the following:

```
@Test
  public void testReverseInPlace2() {
    int[] input2 = { 3, 6, 5, 2 };
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[] { 2, 5, 6, 3 }, input2);
  }
```
- This is a Junit test, which tests the functionality of ```testReverseInPlace2``` which would cause an error output when using the junit compiling commands, and here is what the error specific to ```ArrayReversedInPlace``` would be:

```
1) testReverseInPlace2(ArrayTests)
arrays first differed at element [2]; expected:<6> but was:<5>
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
        at org.junit.Assert.internalArrayEquals(Assert.java:534)
        at org.junit.Assert.assertArrayEquals(Assert.java:418)
        at org.junit.Assert.assertArrayEquals(Assert.java:429)
        at ArrayTests.testReverseInPlace2(ArrayTests.java:16)
        ... 32 trimmed
Caused by: java.lang.AssertionError: expected:<6> but was:<5>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
        ... 38 more
```
- The error is that the ``` assertArrayEquals(new int[] { 2, 5, 6, 3 }, input2);``` call turned out to be false, likely because the two inputs were not equal, as indicated that these arrays differed at element of index 2, where we expected ```6``` for both, but the ```ReversedInPlace``` ended up causing the wrong outputs.

**1b) Non-failure inducing Input for ArrayReversedInPlace**
- One such non-failure inducing output for ```ArrayReversedInPlace``` would be the following:

```
  @Test
  public void testReverseInPlace3() {
    int[] input2 = { 4 };
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[] { 4 }, input2);
  }
```

**1c) What are the symptoms for ArrayReversedInPlace?**

- For the failure-inducing input, the symptoms were as follows:
  ![image](ArrayReversedInPlaceFailureInduce.png)

- The symptom is that the ``` assertArrayEquals(new int[] { 2, 5, 6, 3 }, input2);``` call turned out to be false, likely because the two inputs were not equal, as indicated that these arrays differed at element of index 2, where we expected ```6``` for both, but the ```ReversedInPlace``` ended up causing the wrong outputs.
 
- For the successful output, the symtpom was as follows (although it's not particularly a bad symptom):
 ![image](ArrayReversedInPlaceSuccess.png)

- The symptom demonstrates that all tests run okay, and that the ```assertArrayEquals``` junit test passes, and works.

**1d) What is the bug? Demonstrate the before and after.**

- The bug of the function (beforehand) which results in the symptoms and failures is as such:

  ```
  for (int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  ```

  - The reason for this bug is mainly due to the idea of swapping finitely, such that if you have any amount of unique elements in an array, then eventually, at the halfway point, both sides of the array will be consisting of the same values, and so swapping is futile, since the original values of the first half have been overriden already. Thus, to fix this, I would argue to use a temp variable named ```temp``` or something of the like. Then you would set ```temp``` to the corresponding beginning of the array, make sure that the array only runs until halfway such that both sides stop once everything is properly reversed, and swap accordingly, such that the code after fixing the bug looks like such:

 ```
static void reverseInPlace(int[] arr) {
    int temp = 0;
    for (int i = 0; i < arr.length / 2; i += 1) {
      temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length-i-1] = temp;
    }
```
- After this, everything gets swapped accordingly, the assertArrayEquals should be able to work.
- The fix addresses the issue, because now, for each corresponding element in the first half of the array, we store it in a ```temp``` variable, such that when that element gets changed to the same value as the last element, we still have stored that original first element somewhere. Then we can set that last element in the back half to the temp, so that these elements are properly reversed. We are only doing this up until the halfpoint of the array, if only because, at the halfway point, we have reversed every element. 



## **2) Command Line Investigation: ```Grep``` and its Command Line Options**

**Preknowledge**: 
- The ```grep``` command essentially takes the form of the following: ```grep <<string>> <<files>>```. Essentially it searches through files (or multiple) until it finds the string specified in the command line. It then prints the lines which contain those exact strings. The files can be written as absolute paths as well. 

**2a) ```Grep``` with command line option ```-i```**
- The input I used with ```Grep -i``` was as follows:

```
grep -i "Approaches" /Users/matthewpham/Documents/GitHub/docsearch/technical/biomed/gb-2002-3-12-research0088.txt
```
-This printed out the following: 

```
 Approaches using DNA microarrays have been successful in
          approaches based on pattern-recognition algorithms,
          computational approaches impracticable at present.
          data and other data-mining approaches will establish sets
```
