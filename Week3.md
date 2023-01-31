# Week 3 Lab Report

## Part 1:
##### Here's my take on the StringServer implementation:

![image](https://user-images.githubusercontent.com/54877475/215655157-fa522980-5a6c-4dd4-bae6-a5f17e3d4e09.png)

##### Here's what results:

![image](https://user-images.githubusercontent.com/54877475/215655359-c0255f25-3a35-4ec7-a3ca-63b06a36a238.png)

##### The first method to be called is the `main` method within my `StringServer` class. In `main`, int variable `port` stores the port number I passed through the commmand line when running `StringServer` (i.e. `4001`). The predefined `Server` class's `start` method is then invoked to create the localhost, taking in `port` and creating a new `Handler` object. Then, method `handleRequest` in class `Handler` is called, with the argument being the entire URL that was entered into the localhost.
