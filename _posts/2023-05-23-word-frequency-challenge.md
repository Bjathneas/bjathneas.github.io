---
title:  "Word Frequency Challenge"
date:   2023-05-22 00:03:00 -0500
header:
  teaser: /assets/images/WFC.png
author_profile: true
categories: challenges projects
tags: c++
---
# Introduction
After spending all day working on leetcode solutions, I decided to ask chatGPT to give me a programming challenge. This is the challenge that was given 
to me, and how I decided to solve it.

# chatGPT's Challenge
## Challenge: Word Frequency Counter

Write a program that reads a text file and outputs the frequency of each word in descending order. The program should ignore punctuation and treat uppercase and lowercase letters as the same.

## Requirements:

    The program should prompt the user to enter the path to the text file.
    The program should read the file and count the frequency of each word.
    Words should be considered as sequences of characters separated by whitespace.
    Punctuation marks (such as periods, commas, and parentheses) should be ignored.
    The program should ignore the case of words, treating uppercase and lowercase letters as the same.
    The program should output each word along with its frequency, sorted in descending order of frequency.
    If multiple words have the same frequency, they should be sorted alphabetically.
    The program should handle large text files efficiently.

## Example:
Given the following text file "sample.txt":

```sql
The quick brown fox jumps over the lazy dog.
The dog and the fox are good friends.
```

Output:

```sql
the - 3
fox - 2
dog - 2
and - 1
are - 1
brown - 1
friends - 1
good - 1
jumps - 1
lazy - 1
over - 1
quick - 1
```

## Note:

* The word "the" appears three times and is the most frequent, followed by "fox" and "dog" with a frequency of two.
* The words "and," "are," "brown," "friends," "good," "jumps," "lazy," "over," and "quick" appear once each.

# My Solution
After having read the challenge, it was time to run cppship init to create a new project and begin programming.

My first step was to get the user's input and validate it, then it was time for gathering data from the file. I decided to load the file streams 
buffer into a stringstream, where it could then be looped through word by word. To meet the requirements, each word was changed to lowercase 
and then all unwanted characters were purged.

After I got that out of the way, I created a new function to generate a map that would store each word and 
its frequency. Then that map was turned into a dynamic array which was sorted according to the requirements.

Finally, I output the array to the console and a file called 'WFC_output.txt'. To test the speed of this algorithm, I then imported the entire bible(beginning to end) into a plain text file.
I then ran this file through my program, and as soon as I hit enter the program was finished in under a second, granted my computer is very fast and powerful.

My solution can be found [here](https://github.com/Bjathneas/WFC), feel free to mess around with.

