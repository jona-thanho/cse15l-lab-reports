# Week 5 Lab Report
#### Want to find out 4 different ways to use the `grep` command? Read on!

## 1. `grep -rl "string to search" /path/to/file/`
#### Here's it in action:
```
$ grep -rl "Louvre" written_2/
written_2/non-fiction/OUP/Rybczynski/ch1.txt
written_2/travel_guides/berlitz1/HistoryFrance.txt
written_2/travel_guides/berlitz1/WhereToEdinburgh.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/WhereToGreek.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
written_2/travel_guides/berlitz2/Paris-WhatToDo.txt
written_2/travel_guides/berlitz2/Paris-WhereToGo.txt
```
#### Here `grep` is searching all files within `written_2/` for the string `Louvre`. The `r` stands for a recursive search of `written_2/` and its subdirectories the `l` instructs `grep` to output the file name that contains `Louvre`.

#### Another example is:
```
$ grep -rl "pasta" written_2/travel_guides/berlitz2/                
written_2/travel_guides/berlitz2/Boston-WhereToGo.txt
```
#### We see that `grep` searches all files within `written_2/travel_guides/berlitz2/` for the string `pasta`, resulting in one file found. From these two examples, we see that this command is useful when we want to know the file name/path in which a specific string is located.

###### *Source: https://stackoverflow.com/questions/16956810/how-to-find-all-files-containing-specific-text-string-on-linux*

## 2. `grep -rn "string to search" /path/to/file/`
#### This is how it works, using the previous string and file path for comparison:
```
$ grep -rn "pasta" written_2/travel_guides/berlitz2/
written_2/travel_guides/berlitz2/Boston-WhereToGo.txt:53:Salem Street, just north of Hanover, is another atmospheric street lined with wonderful delicatessens redolent with the scents of fresh cheeses, sausages, and pasta, newsagents selling Corriere della Sera and La Gazzetta dello Sport, and such bakeries as Bova, selling first-rate cakes and pastries at number 134.
```
#### The output is the exact same as that of the previous example, except now, the line number (`53`) and corresponding text where `pasta` was found is also outputted. It is the `n` that leads to this change, with the `r` still standing for a recursive search.

#### To give another instance:
```
$ grep -rn "18.5 miles" written_2/
written_2/travel_guides/berlitz1/WhereToJapan.txt:1291:Miho Museum. Some 30 km (18.5 miles) outside Kyoto, set
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:142:The mountain areas surrounding the Capalita River are also the site of many natural treasures, including the Capalitilla Cascades. About 30 km (18.5 miles) north of Tangolunda a grouping of waterfalls, with heights averaging 25 m (80 feet) form natural Jacuzzis and clear pools for swimming. The area is also popular for horseback riding and rappelling.
```
#### Again, the two line numbers and their associated text are outputted to the terminal. We see that this command is useful for when you want to view the surrounding text of a specific keyword (i.e. gain context) or know the line number of that keyword.

###### *Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/*

## 3. `grep -c "string to search" /path/to/file/`.
#### This is how you use it:
```
$ grep -c "and" written_2/travel_guides/berlitz2/Paris*.txt
written_2/travel_guides/berlitz2/Paris-WhatToDo.txt:30
written_2/travel_guides/berlitz2/Paris-WhereToGo.txt:139
```
#### What happens here is the `c` option outputs the number of occurences (`30` and `139` in their respective files) of string `and` in `written_2/travel_guides/berlitz2/Paris*.txt`.

#### Another instance is:
```
$ grep -c "Joe" written_2/travel_guides/berlitz2/Portugal*.txt
written_2/travel_guides/berlitz2/Portugal-History.txt:0
written_2/travel_guides/berlitz2/Portugal-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt:0
```
#### Joe, if you're reading this, don't be sad. I'm sure Portugal has nothing against you. Anyway...searching for string `Joe` in `written_2/travel_guides/berlitz2/Portugal*.txt` shows that `Joe` is nowhere to be found (`0`, `0`, and `0` occurences). All in all we see that this command could be used for finding a word/character count (I know there's a separate command for that, but that's beyond the scope of this article).

###### *Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/*

## 4. `grep`
