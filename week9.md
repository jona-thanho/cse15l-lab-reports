# Week 9 Lab Report
### You read my last lab report on how to get a pretty fast *CSE Labs “Done Quick”* time (hopefully), but you want more. You want it EVEN FASTER. Lucky for you, you're in the right place. This article will show you how to utilize a bash script to complete the tasks in TWO lines (yes, you read that right).

## Step 1. "Log into ieng6" the old-fashioned way

#### Proceed to logging into the remote as outlined in my previous lab post: use `<ctrl r>` to search for `ssh [your course username]`.

## Steps 2-6. Using a bash script

#### Now for the fun part. On the remote, I executed `touch cldq.sh` to create the new bash script, naming it `cldq.sh`. I then used `nano cldq.sh` to enter `cldq.sh` and type the following:
```
# 2. "Clone your fork of the repository from your Github account"
git clone git@github.com:jona-thanho/lab7.git

# 3. "Run the tests, demonstrating that they fail"
cd lab7/
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

# 4. "Edit the code file to fix the failing test"
sed -i '43s/.*/      index2 += 1;/' ListExamples.java

# 5. "Run the tests, demonstrating that they now succeed"
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

# 6. "Commit and push the resulting change to your Github account (you can pick any commit message!)"
git add .
git commit -m "Changed line 43"
git push
```

#### Each line is the same command I ran when completing the tasks without a bash script, except for step 4's `sed -i '43s/.*/      index2 += 1;/' ListExamples.java`, which I had to [research](https://stackoverflow.com/questions/11145270/how-to-replace-an-entire-line-in-a-text-file-by-line-number) specfically to make this script work. Essentially, this command replaces line `43` in `ListExamples.java` with `      index2 += 1;` (extra spaces for consistent indentation). It's important to note that this command works even when completing the tasks without a bash script. Looking back, it would've saved me many, many keystrokes as opposed to using `nano` and manually editing `ListExamples.java`.

#### All you need to do now is run `bash cldq.sh` and sit back and relax: 

![image](https://user-images.githubusercontent.com/54877475/224852151-2d2c8e33-6622-4d4e-b481-950dd468ae92.png)

#### Here you see all the correct output, just in a different format. Everything is now condensed together which can be confusing to read, but try drawing imaginary lines where each command would be originally.

## But wait...
>### If we're using a bash script, can't we also include step 1 in the script, reducing the required steps to only one?

#### Good question! Unfortunately, the script failed to execute completely when I included `ssh cs15lwi23aps@ieng6.ucsd.edu` in the first line of the script:

![image](https://user-images.githubusercontent.com/54877475/224846135-d1874192-f3bb-496e-a67e-d9b1aeaffe7b.png)

#### As you can see, `cldq.sh` stops running after it logs into the remote. It's a weird behavior that I was not able to figure out. But hey, the steps outlined above will already give you a world-class time. Best of luck :)
