# Lab Report 4

### VIM

I completed steps 1-3 on my own.

#### Step 4:

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/a8bb6b27-82e8-4ff6-a7a9-3a0c6a5e6f28)

To login to ieng6, I type `ssh acalza@ieng6-201.ucsd.edu` to log into the server.

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/635add66-09f4-4cff-b4ff-69522417f993)

From there I went into `cs15lwi24`.

#### Step 5:

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/4c919a57-a056-4135-a606-ad94469f2cf1)

I used `git clone` with the `SSH` url from github to clone the repository into my directory on the server.

#### Step 6:

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/c73a1a82-7ccb-4ab4-bb2c-7da23094ef16)

Once the directory was cloned, I used `ls` to check where I needed to go and found that I needed to `cd lab7` to be in the correct directory to run the tests. From there I used `ls` again to see what files I needed to run and then ran `bash test.sh` to run the test. As you can see by the output, one test fails and one test passes.

#### Step 7:

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/c0aafe84-bdad-4aa2-aa2d-b988e406ab1d)

To get to this point, I will run you through all the commands I used to change the index from `index1` to `index2`. To begin I used `<down>` 43 times to get to the correct row and then pressed `<right>` 12 times to get the cursour on the number 1. I then pressed `<x>` to delete the character, preseed `<i>` to enter insert mode, and then added a `<2>` in. Once the change was completed, I pressed `<esc>` to exit insert mode followed by `:wq <enter>` to exit and save the changes in the vim editor.

#### Step 8:

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/20e438ae-f1fc-4b3b-8ff3-3167d6330e1a)

I reran the test using `bash test.sh` and as you can see, both tests passed indicating the changes were saved.

#### Step 9:
![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/31a23561-7dae-450d-8543-12dd6a17603b)

I commited the changes to my git hub account using `git commit -m "Update"` to commit the changes with the message "Update". 

Note: The 2 file changes are due to me accidentaily adding the smh file the vim creates to the repo along with the correct changes to the ListExamples file.
