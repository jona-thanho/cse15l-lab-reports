# Week 3 Lab Report

## Part 1:
#### Here's my take on the StringServer implementation:

![image](https://user-images.githubusercontent.com/54877475/215667173-3c80d67e-7449-4e06-9f40-b44225c49820.png)

#### Upon testing, here's what results:

![image](https://user-images.githubusercontent.com/54877475/215655359-c0255f25-3a35-4ec7-a3ca-63b06a36a238.png)

#### The first method called is `main` within my `StringServer` class, where the int variable `port` stores the port number (from `args[0]`) I passed through the commmand line when running `StringServer` (`4001`). `Integer.parseInt` is utilized to convert the String value from `args[0]` into an int. The predefined `Server` class's `start` method is then invoked to create the localhost, taking in `port` and creating a new `Handler` object. Then, method `handleRequest` in class `Handler` is called, with the argument `url` being the entire URL that was entered into localhost. Methods `getPath` and `equals` are invoked to check whether the URL path contains argument `"/add-message"`. String array `query` is updated to contain the message entered after the `=` sign in the localhost URL (`Joe`), which is stored in index 1 of `query`. Methods `getQuery` and `split` are used to achieve this. The String `output` variable is then updated with the text to be displayed (`Joe`, from `query[1]`) as well as a newline character for formatting.

#### Another test input displays the following:

![image](https://user-images.githubusercontent.com/54877475/215658939-68ae9621-318e-4ed1-9a26-d86d0d6976c4.png)

#### The same steps outlined previously are executed for this test case. The key difference is changing the URL input after `=` alters `query[1]` to contain `Politz` which as a result updates `output` to `Politz\n`.

## Part 2:

#### Upon testing the `reverseInPlace` method in the `ArrayExamples` class, you can quickly see that something is off. For instance, the following JUnit test fails:

```Java
@Test 
public void testReverseInPlace() {
  int[] input1 = {3, 4, 5};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{5, 4, 3}, input1);
}
```
#### However, a test does pass:

```Java
@Test 
public void testReverseInPlace() {
  int[] input2 = {3};
  ArrayExamples.reverseInPlace(input2);
  assertArrayEquals(new int[]{3}, input2);
}
```
#### This is the symptom produced by running `input1` and `input2`: 

![image](https://user-images.githubusercontent.com/54877475/215676104-7ddb5736-7a6f-41fe-9977-f7584126af69.png)

#### To remedy this bug, I implemented these changes:

#### BEFORE:
```Java
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = temp[arr.length - i - 1];
  }
}
```
#### AFTER:
```Java
static void reverseInPlace(int[] arr) {
  int[] original = new int[arr.length];

  for (int i = 0; i < arr.length; i += 1) {
    original[i] = arr[i];
  }
  
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = original[arr.length - i - 1];
  }
}
```
#### My additions remove the bug as the second-half reversal of `arr` is now accounted for. By separating the array being reversed and the original array, the correct elements from either side of the array are swapped.

## Part 3:

#### It wasn't until last lab session when I finally got my `javac` to function properly in Git Bash. I'd been struggling with it for the past 1.5 lab sessions, with multiple tutors and TAs perplexed at how my code would *refuse* to compile. I'm not entirely sure what Dave (absolute beast TA) told me to do that solved my problem but from what I recall, I needed to alter the PATH variable to the correct directory in my C drive as it previously pointed somewhere in my D drive. I suspect what happened was that I downloaded either Java or Git Bash into a folder that was not the default "Program Files" folder in my C drive. In any case, you live you learn, eh?
