# Week 9 Lab Report
#### You read my last lab report on how to get a pretty fast *CSE Labs “Done Quick”* time, but you want more. You want it EVEN FASTER. Lucky for you, you're in the right place. This article will show you how to utilize a bash script to complete the tasks in TWO lines (yes, you read that right).

## Step 1. "Log into ieng6" the old-fashioned way

>#### But wait, if we're using a bash script, can't we just put all the commands in the script, reducing the required steps to only one?

#### Good question! Unfortunately, the bash script (see next steps for full script) failed to execute completely when I included `ssh cs15lwi23aps@ieng6.ucsd.edu`:

![image](https://user-images.githubusercontent.com/54877475/224846135-d1874192-f3bb-496e-a67e-d9b1aeaffe7b.png)

#### As you can see, the script (`cldq.sh`) stops running after it logs into the remote. It's a weird behavior that I was not able to figure out. Anyway, proceed to logging into the remote as outlined in my previous lab post: use `<ctrl r>` to search for `ssh [your course username]`.

## Steps 2-6. Using a bash script

#### Now for the fun part. Here's the bash script I created:

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
#### Now on the remote, I used the `touch` command to create the new bash script, naming it `cldq.sh`. Each line is the same command I ran when completing the tasks without a bash script, except for step 4's `sed -i '43s/.*/      index2 += 1;/' ListExamples.java`, which I had to research for 

###### *Source: [Stack Overflow](https://stackoverflow.com/questions/11145270/how-to-replace-an-entire-line-in-a-text-file-by-line-number)*
