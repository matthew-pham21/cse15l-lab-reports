## **In this lab report, we are required to create a debugging scenario, which involves constructing an error-inducing function and bug, utilizing at least one bash script and one java script. We also create a conversation involving edStem, and making a post, while we have to respond as a TA with a leading question or a command. We must detail out every step of this process. Here is the conversation:

## **1) EdStem Post and Response**
**Student**:
Hello, I'm currently experiencing issues with my code, which is to add together integer lists using a **merge** method, into one larger list, where we compare two indexed integers, and add the smaller number to the new list first, then add the other integers in later. However, I keep running into the following bugs, and can't decipher how to fix them. Any advice would be helpful! I've included a screenshot below to showcase the bugs.
![image](ErrorInducingBugReport5.png)




**TA Response (me)**: Hi Y/N! A private post with code would greatly help me resolve your issue here. However with what is given in the error, we know that there is likely more than a singular error. We can peg down the following:
- **Think about how your indexes are changing in your code**: Why are your indices never properly incremented to match the supposed correct examples in your junit tests? Where in your function do you think you may have incremented incorrectly? Find that, and think about how you can change that portion to properly increment. It could possibly be in more than a single place.
Once you've done that, try running your code again, and see if your junit tests work afterwards.

Best, 
TA

**Student changing the issue**: 


![image](TerminalOutputAfterFixReport5.png)
**Student**:
Hi thank you so much for the suggestions. I found out what the issue was with my code: it was twofold. The first issue was that in one of my lines of code, for the if statement that determines which integer to add first, it made it such that the greater integer of the two being compared was the one being added first, the complete opposite of what the intention of the merge function was. That was part of the issue that created the bug of improper matching. However, the second issue was that I had a separate indexing error. In my else statement, rather than only incrementing one of the indexes, as only one integer would be added, it incremented both indexes, and so, that was what was causing the error with regards to why the actual length was different from the expected length, one array was shorter than the other. 


