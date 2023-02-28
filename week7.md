# Week 7 Lab Report

### Want to know the secrets to a fast *CSE Labs “Done Quick”* time? Read on!
###### DISCLAIMER: My method wasn't the fastest, but it's definitely more practical than running everything in one line as the winner did. I swear I'm not salty...

## 1. "Log into ieng6"

![image](https://user-images.githubusercontent.com/54877475/221727984-a8d92399-d563-4374-949c-a8a707e5bc93.png)

### Keys pressed: `<ctrl r>`, ss, `<enter>`

#### Since I had previously ran the `ssh` command, I used `<ctrl r>` to search in my command history and typed the letters *ss* to match the `ssh`. Once it was found, I hit `<enter>` which ran the command.

## 2. "Clone your fork of the repository from your Github account"

![image](https://user-images.githubusercontent.com/54877475/221729572-6d0fd902-927d-42da-907f-925ca1f63963.png)

### Keys pressed: `<ctrl r>`, git, `<space>`, cl, `<enter>`

#### Similar to the previous step, I used `<ctrl r>` and typed *git cl* to search for `git clone`. I had to type out more letters to get a match since `git clone` closely resembles `git commit`, the latter being the most recent command I ran. Once `git clone` was found, I hit `<enter>` to run it.

## 3. "Run the tests, demonstrating that they fail"

![image](https://user-images.githubusercontent.com/54877475/221737219-bf80ed41-a94c-4c60-a282-a2d32bd94b2f.png)

### Keys pressed: 
#### Line 1 - cd l *(lowercase L)*, `<tab>`, `<enter>`
#### Line 2 - `<ctrl r>`, javac, `<enter>`
#### Line 3 - `<ctrl r>`, java, `<space>`, `<enter>`

#### In line 1, I typed *cd l* and pressed `<tab>` to autocomplete the `lab7` directory name. I hit `<enter>` to run the resulting command.
#### In line 2, I used `<ctrl r>` (Yes, again! Very useful.) and typed *javac* to find my previously run `javac` command, pressing `<enter>` to run that command.
#### For line 3, `<ctrl r>` was used with keyword *java* along with one `<space>` to find the `java` command. Without `<space>`, the `javac` command is found instead. `<enter>` then ran this line.

## 4. "Edit the code file to fix the failing test"

![image](https://user-images.githubusercontent.com/54877475/221734886-3be3ff87-6a34-4b3c-bf1f-d1bdb24a2238.png)

### Keys pressed: `<ctrl r>`, nan, `<enter>`, `<ctrl shift ->`, 43, `<enter>`, `<right arrow>` *(12 times)*, `<backspace>`, 2, `<ctrl o>`, `<enter>`, `<ctrl x>`

#### All that for a tiny line of code? Yep, lots of behind the scenes stuff. `<ctrl r>`, *nan*, and `<enter>` are used to locate and run the `nano` command. Once inside the nano editor, I used `<ctrl shift ->` and typed *43* to move my cursor to the beginning of line 43 in `ListExamples.java`, which is where the bug is located. I then hit the `<right arrow>` 12 times to move my cursor right after variable `index1` and hit `<backspace>` and *2* to change it to `index2`. With the bug fixed, I use `<ctrl o>` and `<enter>` to save my changes and `<ctrl x>` to exit the nano editor.

## 5. "Run the tests, demonstrating that they now succeed"

![image](https://user-images.githubusercontent.com/54877475/221737974-dfede263-c968-48e4-aeee-01e5a1b50a6a.png)

### Keys pressed:
#### Line 1 - `<ctrl r>`, javac, `<enter>`
#### Line 2 - `<ctrl r>`, java, `<space>`, -, `<enter>`

#### For line 1, `<ctrl r>`, *javac*, and `<enter>` locates and executes the `javac` command.
#### For line 2, `<ctrl r>`, *java*, and `<space>`and is not enough to match the `java` command, as it matches the previous `nano ListExamples.java` command. Therefore, I needed to enter *java -* instead. With the correct command found, `<enter>` runs it.

## 6. "Commit and push the resulting change to your Github account (you can pick any commit message!)"

![image](https://user-images.githubusercontent.com/54877475/221739492-090c0a67-d8d1-4912-97bd-a676747e436a.png)

### Keys pressed:
#### Command 1 (`git add .`) - git, `<space>`, add, `<space>`, ., `<enter>`
#### Command 2 (`git commit -m "ok"`) - git, `<space>`, commit, `<space>`, -m, `<space>`, "ok", `<enter>`
#### Command 3 (`git push`) - git, `<space>`, push, `<enter>`

#### For these last 3, I just typed them out manually. I definitely could've saved a few keystrokes by using `<ctrl r>`, but for some reason I decided not to. It's probably because I was already so used to typing them manually, way before I learned about `<ctrl r>`. It's hard to break old habits :')
