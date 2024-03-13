# Lab Report 5
> Last Edited: 12 March, 2024  
> Dax Patel  

## Part 1 - Debugging Scenario  
**The original post:**  
Hi,  
I was going through the steps for lab7 and thought I would do all of them on my own computer first locally and then do it in one go on the remote ieng6 server; everything works until step 8, which tells me that the tests are still failing after I have already fixed the problems in the code. Could someone please help me figure out why this is?  
For your reference, this is the result of running the test script before any changes:  
![before edit](https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/9f39b020-f951-4c74-8530-c933d10e0b9e)  
and this is the result after I edit the file in Vim editor and then run it again:  
![after edit](https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/c268e677-057f-4039-8ee3-48f9a44eef31)  
Any help would be much appreciated!  
-Student Dax  

**TA's reply:**  
Hi Student Dax,  
I see you are having problems fixing your java file. Could you run me through the process of you fixing the bugs?  
-TA Dax  

**Student's response:**  
So after I open the file in Vim editor, I click `i` to put the editor in insert mode and then go ahead and make changes to the file as mentioned in the comments and then quit the editor.  
Here is my code before I do the edits:  
![code before edit](https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/fa759925-e545-4f82-9d79-bd762716cbb4)  

And here is the code after I make the edits:  
![code after edit](https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/9d0bd29f-ca4f-45a7-b6bf-16aaaaea93ff)  

I am inclined to think that my code after the edits should work as intended and the script file should not be giving me the error message that it does. Do you think that there is an error with the script?  
Thanks,  
-Student Dax  

**TA's reply**  
Hi Student Dax,  
I have looked through the script file and there seems to be no errors with the file, so I would think that there is something that you're doing (or not doing!) that is causing the script to still give you that error message. Moreover, your code after the fixes seems about right so I wouldn't worry about that. Could you walk me through your exact steps that you take after you make your edits in Vim?  
-TA Dax  

**Student's response**
So after I make the edits, I just quit the insert mode by clicking `esc` and then quit Vim by typing in `:q!` and then hitting `enter` like this:  
![quit](https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/2311f3af-124f-4cf8-90e8-9eb26df20df6)  
Also, I am noticing now that the code that I altered last time I edited the file is no longer there and the file has reverted to its original (buggy) form. Why?  
-Student Dax  

**TA's reply**  
Hi Student Dax,
Kudos for spotting the difference in file content even after you make the edits. That is in fact related to the mistake you are making while editing. When you quit Vim, you also want to save the contents in your file now. Your `:q!` command only quits the Vim editor (and doesn't save the current progress). You should instead be using a command that saves your file content and then quits the editor. Refer back to one of our lectures or do a quick google search to find the command to be used now instead of the `:q!` command that you have been using thus far!  
Good luck!  
-TA Dax  

**Student's response**  
I understand now the mistake that I was making. I found the correct alternative through a google search and have used `:wq!` and running the script file now shows that my code now passes all tests!  

Me saving and quitting the Vim editor with the new command:  
![wq fr](https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/62722ad6-4be2-4d8c-bbf8-6567d7ed0c18)  
And this is me running the script successfully:  
![test pass](https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/6c309ca3-0ea2-4133-bc1a-d7fb924aed7e)  
Thank you so much, TA Dax!  
-Student Dax  


**My observation and the information required to debug:**  
TA Dax didn't really need the file structure in this case because the files are all in the the (https://github.com/ucsd-cse15l-s23/lab7) repository that has been provided by the course staff. Student Dax already did a good job providing as much info as he could to TA Dax, by showing the file contents and the failure messages. The screenshots were of the terminal so that TA Dax could see what commands Student Dax was running, but that ultimately didn't end up helping a lot as the problem was related to the student's command while quitting Vim and not the terminal commands themselves. TA Dax's step-by-step approach to pinpoint the specific error-causing action helped him to land on the command Student Dax was using to quit Vim, and the TA steered the student in the right direction without actually giving him the answer!  

## Part 2 - Reflection  

Before coming to this class, I used to think of Vim as some uber-cool editor used only by the most seasoned of programmers with years and years of coding experience; this was perhpas perpetuated by some Instagram reels I had come across and I was skeptical about my ability to learn the basics of Vim because of this. Now, however, I feel quite comfortable using Vim for short periods of time; VSCode will forever be my go-to editor though, it lets me use my mouse haha!  

>Dax Patel | 12 March


