## **In this Lab Report, we are tasked with two individual assignments. The first will be to demonstrate bugs, symptoms, junit testing input, showing the bug beforehand, as well as how to fix such a bug. The second section revolves around researching different commands such as less, find, grep, etc. Here is the exploration of the bug I chose from Week 4 Lab, as well as the results I found from researching various commands.**

## **1) Bugs Examination: ArrayReversedInPlace**

**1a) A failure-inducing Output for ArrayReversedInPlace**
-One Such failure-inducing output for ArrayReversedInPlace would be the following:

``` @Test
  public void testReverseInPlace2() {
    int[] input2 = { 3, 6, 5, 2 };
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[] { 2, 5, 6, 3 }, input2);
  } ```
