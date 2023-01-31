# Week 3 Lab Report

## Part 1:
##### Here's my take on the StringServer implementation:

![image](https://user-images.githubusercontent.com/54877475/215667173-3c80d67e-7449-4e06-9f40-b44225c49820.png)

##### Upon testing, here's what results:

![image](https://user-images.githubusercontent.com/54877475/215655359-c0255f25-3a35-4ec7-a3ca-63b06a36a238.png)

##### The first method called is the `main` method within my `StringServer` class. In `main`, int variable `port` stores the port number (from `args[0]`) I passed through the commmand line when running `StringServer` (i.e. `4001`). `Integer.parseInt` is utilized to convert the String value from `args[0]` into an int. The predefined `Server` class's `start` method is then invoked to create the localhost, taking in `port` and creating a new `Handler` object. Then, method `handleRequest` in class `Handler` is called, with the argument `url` being the entire URL that was entered into localhost. Methods `getPath` and `equals` are invoked to check whether the URL path contains argument `"/add-message"`. String array `query` is updated to contain the message entered after the `=` sign in the localhost URL (`Joe`), which is stored in index 1 of `query`. Methods `getQuery` and `split` are used to achieve this. The String `output` variable is then updated with the text to be displayed (`Joe` in `query[1]`) as well as a newline character for formatting.

##### Another test input displays the following:

![image](https://user-images.githubusercontent.com/54877475/215658939-68ae9621-318e-4ed1-9a26-d86d0d6976c4.png)

##### The same steps outlined previously are executed for this test case. The key difference is changing the URL input after `=` alters `query[1]` to contain `Politz` which as a result updates `output` to `Politz\n`.

## Part 2:

##### Upon testing the `reverseInPlace` method in the `ArrayExamples` class, one quickly finds bugs. For instance, the following JUnit test fails:`

```
@Test 
public void testReverseInPlace() {
  int[] input1 = {3, 4, 5};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{5, 4, 3}, input1);
}
```
##### However, some tests do pass:

```
@Test 
public void testReverseInPlace() {
  int[] input2 = {3};
  ArrayExamples.reverseInPlace(input2);
  assertArrayEquals(new int[]{3}, input2);
}
```
