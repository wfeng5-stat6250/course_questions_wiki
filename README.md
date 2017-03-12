# Course Questions Wiki

This document contains questions and answers corresponding to reading from the course textbook.

To contribute,

1. fork this repo to your GitHub Account (e.g., using the "Fork" button in the upper-right-hand corner of the GitHub web interface),

2. make appropriate changes/corrections using Markdown (see https://guides.github.com/features/mastering-markdown/), and

3. initiate a pull request using

- the master branch of the stat6250/course_questions_wiki repo as the base fork and

- your version of the repo as the head fork.

********************************************************************************

## Chapter 1 Questions

[Chapter 1, Problem 8]
- Question (AP):Can we configure the default length for the variable types? How?
- Answer(AP):We can configure the default length for variables using the length statement. General format is LENGTH variable-list $ number-of-bytes;


## Chapter 2 Questions

[Chapter 2, Problem 7]
- Question (IL): What's the difference between starting a SAS program with "data" versus "proc", and why do both end types of programs end with the same "run" command, even though the bodies of the programs look nothing alike?
- Answer (IL): SAS programs are divided into "steps", each step is either a data step or a proc step (as determined by the first word in the step), and all steps are typically terminated by a "run" statement. However, when using a "cards" or "dataline" statement in a data step, then the data step is terminated by a closing semicolon. In addition, some procs (like the interactive proc glm) are only terminated with a "quit" statement.

-Question(AP):What are the kinds of statements that should go in the data and proc components of the SAS program?
-Answer(AP):DATA step: Used to put external data into SAS data sets, create new data sets by merging, subsetting external data sets, compute values and check and correct errors in external data sets
PROC step: Analyse and process data from the sas data set, create reports, produce descriptive statistics etc

[Chapter 2, Problem 9]
- Question (IL): What is a "libref", and how does it differ from a "LIBNAME"?  In particular, what fundamental distinction causes one to be written out in lower-case letters and the other in upper-case letters?
- Answer: TBD

## Chapter 3 Questions
[Chapter 3, Problem 3]
- Question (AP):The error continues to occur in other SAS programs if the statement is not canceled(unclosed quotation marks). So, when we find such errors in the log window how do we make sure it of the current SAS program and not some other program from the session
- Answer(AP): Cancel all SAS statements, correct the error and run the SAS program again.

## Chapter 4 Questions


## Chapter 5 Questions


## Chapter 6 Questions


## Chapter 7 Questions


## Chapter 8 Questions


## Chapter 10 Questions


## Chapter 11 Questions


## Chapter 12 Questions


## Chapter 13 Questions


## Chapter 14 Questions


## Chapter 15 Questions


## Chapter 16 Questions


## Chapter 17 Questions


## Chapter 19 Questions


## Chapter 20 Questions
