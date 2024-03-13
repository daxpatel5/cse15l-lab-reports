# Lab Report 4
> Last Edited: 12 March, 2024  
> Dax Patel

## Step 4: Logging into ieng6  
<img width="1008" alt="4 updated" src="https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/178cfb2d-da66-4153-bd3f-28b1ae0f9f0d">
Keys pressed: `ssh <space> dap014@ieng6-202.ucsd.edu <enter>`  
I have now logged into my remote server based in the CSE basement on my MacBook (without inputting my passowrd) and can now go ahead with the rest of the lab report!  

## Step 5: Cloning fork of repository from my GitHub account  
![5 4](https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/7f518423-9d79-4338-8f5e-764ff86396fb)  
Keys pressed: `git <space> clone <space> git@github.com:daxpatel5/cse15l-lab7.git <enter>`  
I have now succesfully cloned my fork of the original repository on the ieng6 server and can now access the files contained in the repo!  

## Step 6: Running the tests, demonstrating that they fail  
![6](https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/c121b294-ce06-4bab-9c23-9827b63cd206)  
Keys pressed: `ls <enter> cd <space> cse15l-lab7/ <enter> ls <enter> bash <space> test.sh <enter>`  
I have shown that the repository is cloned as is and when the files are run, we encounter an error, which needs to be fixed now!  

## Step 7: Editing the code to fix the failing test  
Keys pressed: `vim <space> ListExamples.java <enter>`  
<img width="896" alt="7 1" src="https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/52faca32-ce56-4749-b913-1bfd1618da27">  
Above is the code in ListExamples.java before we edit it.  
Keys pressed: `j (44 times) l (13 times) i <delete> 2 <esc> :wq! <enter>`  
Now this is the code after the edit:  
<img width="908" alt="7 2" src="https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/b0001b26-6599-40b5-8c8c-b0c08b748ac1">  
Now that our code has been edited succesfully, we will run the bash script once again to verify that all the tests pass!  

## Step 8: Running the tests again to check success  
Keys pressed: `bash <space> test.sh <enter>`  
Terminal output:  
 <img width="527" alt="8 updated" src="https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/0a933ba1-f0ba-4f7a-b0c2-1f6245960fc0">  
Now that we have established that the code works as intended and that there are no errors, we can go ahead and commit this change directly to our GitHub repository!  

## Step 9: Committing and pushing changes to my GitHub
Keys pressed: `git <space> add <space> ListExamples <enter> git <space> commit <space> -m <space> "<*My commit message*>" <enter> git <space> push <space> origin <space> main <enter>`  
<img width="903" alt="9 final" src="https://github.com/daxpatel5/cse15l-lab-reports/assets/83134389/95d1934f-d7fd-4312-aeb5-3cc73aa8da71">  
After this commit, the updated version of the file should be available on our repository and our work here is effectively done!  

Revision: This is an updated version of my original Lab Report 4, in which I have fixed some errors from my initial submission. Specifically, I can now login into my ieng6 machine without using my password. I also now understand that compiling `ListExamples.java ` after fixing the bugs is redundant. I have also corrected my approach to committing and pushing changes to `main` after the bugs are fixed! I hope this lab report is now good enough to receive full points!  


>Dax Patel | 12 March
