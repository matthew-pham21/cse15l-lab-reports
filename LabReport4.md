## **In this Lab, we are tasked with repeating the process of our in-person Lab 7, which is to utilize the VIM editor to edit functions, while also learning different techniques to help edit more efficiently. Here's the results of one such trial:** 

## **#4) Logging into Ieng6**
[image](SSHLogIn.png)
**Keys Pressed**: ```ssh cs15lfa23gs@ieng6.ucsd.edu``` was accessed by typing in each individual key into this string, and then pressing the ```<enter>``` key to fully log in to the ieng6 account/computer. 

## **#5) Testing ListExamples.java without changes**
[image](TestFailuresPreChanges.png)
**Keys Pressed**: To get to this step, what I did was type in a combination of keys (in my keyboard) that create the line command ```bash test.sh```. Then I pressed the ```<enter>``` key to run the bash script, and the resulting screenshot is what was demonstrated (failure in one of the tests).

## **#6) Editing ListExamples.java using VIM**
[image](VIMEditListChangeDefinitive.png)
**Keys Pressed**: To get to this step, first, I typed in a combination of keys (in my keyboard) that create the line command ```vim ListExamples.java```. Then I pressed the ```<enter>``` key. Once I was in vim, immediately, I typed in the command line ```/index1```, which highlights and finds the patterns within the file. I then pressed ```<enter.``` in order to then be able to parse through. I parsed through each instance of ```index1``` using the following commands until I reached the final instance: ```<n>``` ```<n>``` ```<n>``` ```<n>``` ```<n>``` ```<n>```. This parses through the six instances of ```Index1``` until the final instance is reached. Then, the ```<l>``` key was pressed five times: ```<l>``` ```<l>``` ```<l>``` ```<l>``` ```<l>```. This landed us on the ```1``` in ```Index1````. I then pressed the ```<x>``` key in order to delete the instance of ```1```. Then, I pressed the ```<i>``` key in order to enter the insert mode. From there, I pressed the ```2``` key to insert ```2``` at the place where ```1``` was in the final instance of ```index1```. Then, to exit insert mode, I pressed the ```<esc>``` key, and then pressed ```<enter>```. Once back in normal mode in VIM, I then went and proceeded to save the file, utilizing the keys ```<:>```, combined with keys ```<w>``` , ```<q>```` , and ```<!>``` , to produce ```<:wq!>```. I then pressed ```<enter>``` such that everything saved, and we exited the vim editor. 


## **#7) Success Tests after changing ListExamples.java**
[image](BashRunTestsPostChanges.png)
**Keys Pressed**: To get to this step, what I did was similar to step 5: I typed in a combination of keys (in my keyboard) that create the line command ```bash test.sh```. Then I pressed the ```<enter>``` key to run the bash script, and the resulting screenshot is what was demonstrated (all the tests were ok).

## **#8) Git Commit of ListExamples.java**
[image](GitCommitUsing-am.png)
**Keys Pressed**: To get to this step, first I had to use ```git add ListExamples.java``` such that we knew what files we had to commit and push. Then I pressed the ```<enter>``` key to actually add the file. Secondly, I then typed in a combination of keys in order to get the following: ```git commit -am "Changed the final Index1 in order to be Index2, to properly fix the file."```, and I then pressed the ```<enter>``` key to commit the changes with the -am making the ammends and sending this commit message. 


## **#8) Git Push of ListExamples.java**
[image](GitPushFinal.png)
**Keys Pressed**: I typed in a combination of keys in order to get the following: ```git push```, which, once executed, pushed the changes I made to the file, to GitHub. and I then pressed the ```<enter>``` key to execute and push the changes to GitHub.
