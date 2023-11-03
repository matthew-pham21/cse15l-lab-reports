## **In this Lab Report, we are tasked with two individual assignments. The first will be to demonstrate bugs, symptoms, junit testing input, showing the bug beforehand, as well as how to fix such a bug. The second section revolves around researching different commands such as less, find, grep, etc. Here is the exploration of the bug I chose from Week 4 Lab, as well as the results I found from researching various commands.**

## **1) Bugs Examination: ArrayReversedInPlace**

**1a) A failure-inducing input for ArrayReversedInPlace**
- One Such failure-inducing input for ArrayReversedInPlace would be the following:

```
@Test
  public void testReverseInPlace2() {
    int[] input2 = { 3, 6, 5, 2 };
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[] { 2, 5, 6, 3 }, input2);
  }
```
- which would cause an error output when using the junit compiling commands, and here is what the error specific to ArrayReversedInPlace would be:

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
