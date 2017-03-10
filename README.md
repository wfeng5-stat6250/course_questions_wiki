# Course Questions Wiki

This document contains questions and answers corresponding to reading from the course textbook.

To contribute,

1. fork this repo to your GitHub Account (e.g., using the "Fork" button in the upper-right-hand corner of the GitHub web interface),

2. make appropriate changes/corrections using Markdown (see https://guides.github.com/features/mastering-markdown/), and

3. initiate a pull request using

- the master branch of the stat6250/course_questions_wiki repo as the base fork and

- your version of the repo as the head fork.

The instructor will then review the pull request and make comments should further revision be needed. Then, after the contents of the pull request have been finalized without any merge conflicts, the instructor will merge the pull request.

********************************************************************************

## Chapter 1 Questions

[Chapter 1, Problem 1]
- Question (SK): Is indentation  crucial in SAS or it is just for readability? If not then why does some programs gives error because of wrong indentation?
- Answer (SK): Writing codes with proper indent is a best practice for programming.

- Question (WF): Does SAS make the distinction between a variable and an array?
- Answer (WF): array is a set of variables grouped together for the duration of a data step by being given a name in an ARRAY statement.

- Question (WF): Is it possible to have a completely empty
    observation? Would there be any reason to allow this?
- Answer (WF): It’s possible to create an empty dataset by stopping
    process before output.

\[Chapter 1, Problem 3\]
- Question (WF): Can a variable's type be both character and numeric?
- Answer (WF): No, a variable can be numeric or character. Numeric values represent numbers, can be read in a variety of ways, and are stored in floating-point format. Character values can contain letters, numbers, and special characters and can be from 1 to 32,767 characters long.

- Question (WF): Are there traditional variables found in SAS, variables without attributes?
- Answer (WF): all variables have its own attributes.

- Question (WF): In this problem, AcctNum appears like it should be set to a numeric type. What must be done to update it's type and correct the values? The first two need their underscores removed.'Romano' and 'Choi' are names, not account numbers.
- Answer (WF): Once a variable is defined numeric or character, you cannot change it's data type, you must create a new variable.

\[Chapter 1, Problem 5\]
- Question (WF): Is there a maximum length for variables?
- Answer (WF): default is 8 bytes for numeric and character.

\[Chapter 1, Problem 8\]
- Question (WF): Why was 8 bytes chosen? Is it efficient to store all variables with such a large precision?
- Answer (WF): 8 bytes is 64bits, which most CPUs today are 64-bit architecture.


## Chapter 2 Questions

\[Chapter 2, Problem 3\]
- Question (WF): Is a file format engine a type of dataset?
- Answer (WF): A library engine is an engine that accesses groups of files and puts them into a logical form for processing by SAS. It’s a set of code and instruction.

- Question (WF): With 4 digit year values in data lines to be read correctly, does it mean that the YEARCUTOFF=option can be eliminated in the program data lines?
- Answer (WF): yes.

\[Chapter 2, Problem 7\]
- Question (IL): What's the difference between starting a SAS program with "data" versus "proc", and why do both end types of programs end with the same "run" command, even though the bodies of the programs look nothing alike?
- Answer (IL): SAS programs are divided into "steps", each step is either a data step or a proc step (as determined by the first word in the step), and all steps are typically terminated by a "run" statement. However, when using a "cards" or "dataline" statement in a data step, then the data step is terminated by a closing semicolon. In addition, some procs (like the interactive proc glm) are only terminated with a "quit" statement.

- Question (SK): What is YEARCUTOFF= option? Why is this different in two year and four year naming conventions?
- Answer (SK): The value of the YEARCUTOFF= system option affects only two-digit year values. A date value that contains a four-digit year value will be interpreted correctly even if it does not fall within the 100-year span set by the YEARCUTOFF= system option.

- Question (WF): What is a libref? Can a libref be within a DATA, SET, or PROC statement?
- Answer (WF): To create a new SAS library with SAS code, you use the LIBNAME statement. The LIBNAME statement associates the name of the library, or libref, with the physical location of the library. LIBNAME statement can be executed in bot DATA or PROC step.

- Question (WF): Can I name a library with some key words like SPSS? 
- Answer (WF): SAS reserves a few names for automatic variables and variable lists, SAS data sets, and librefs, such as WORK, SASHELPER, SASUSER...

\[Chapter 2, Problem 8\]
- Question (WF): How are namespace conflict issues resolved when two libraries are needed which have the same naming naming conventions and same names?
- Answer (WF): SAS won’t allow to create or move a library at a location that has an existing library with the same name.

- Question (WF): If a data set with two-digit year values has the range of the year more than 100, how to set YEARCUTOFF= value? how to process the year correctly?
- Answer (WF): The YEARCUTOFF= option cannot reliably assign centuries to two-digit years if the range of dates for a variable is greater than 100 years. If the date ranges for a variable span more than 100 years, you must either specify the dates with 4-digit years, or use DATA step logic to assign a century to each year (perhaps based on the value of another variable).

\[Chapter 2, Problem 9\]
- Question (IL): What is a "libref", and how does it differ from a "LIBNAME"?  In particular, what fundamental distinction causes one to be written out in lower-case letters and the other in upper-case letters?
- Answer (SG): A libname statement is the syntactical statement used to initiate a particular library. The libref is the actual syntax used to name it.

- Question (WF):  How to reference a library which is also a data file? for example, libname rptdata spss 'g:\\myspss.spss';
- Answer (WF): libname xdb excel "c:\\mymachine\\pcfdata\\demo.xlsx";


## Chapter 3 Questions
[Chapter 3, General Question]
- Question (AS): Is there a way to print out the values of certain variables during debugging i.e. equivalent of a print statement?
- Answer: TBD

\[Chapter 3, Problem 1\]
- Question (WF): Can DATA and PROC steps begin somewhere else other than column one? How about the RUN statement?
- Answer (WF): SAS programs include two types of steps: DATA steps and PROC steps. DATA steps begin with the keyword DATA, and PROC steps begin with the keyword PROC. Therefore, DATA and PROC steps begin in column one.

\[Chapter 3, Problem 3\]
- Question (WF): When syntax errors like unbalanced quotation marks are in a program, can quotation marks be added and resubmit the program to fix the error?
- Answer (WF): Yes, SAS program can be run or re-run by selecting a block of codes.

- Question (WF): if we use "sum" command, does the "fee" have to be defined in the variable section? 
- Answer (WF): “fee” is a variable in dataset clinic.stress.

- Question (WF): What are some errors that SAS can correct automatically? 
- Answer (WF): SAS does not correct error automatically, it find error for you.

\[Chapter 3, Question 5\]
- Question (WF): what happens if the data values are not appropriate for the SAS statements? Is there a way to convert the data? 
- Answer (WF): SAS would write error message in the SAS log. You cannot convert variable data type.

- Question (WF): what would happen if the elements were right but not valid for that usage? 
- Answer (WF): You might be encountering run-time errors or getting wrong results.

- Question (WF): what does it look like to have program statements that are not conformed to the rules of the SAS language?
- Answer (WF): You would get syntax error.

\[Chapter 3, Problem 7\]
- Question (WF): What do you do to fix misspelled words in SAS statements?
- Answer (WF): SAS is statistics, not word processing. You need to use an external spellchecker.

## Chapter 4 Questions

\[Chapter 4, Problem 1\]

- Question (WF): Are English date formats the only formats SAS processes/produces? 
- Answer (WF): No, you can use “OPTIONS DATESTYLE=mdy; “ (or YDM, or YMD, or DMY…) to change date format.

- Question (WF): When do we want to make a label instead of just using them as a variable? Is it when for the convenience of the variables?
- Answer (WF): Using a LABEL statement in a DATA step permanently associates labels with variables by affecting the descriptor information of the SAS data set that contains the variables. 

\[Chapter 4, Problem 4\]
- Question (WF): If you specify the same out=ref.name in your procs does it overwrite the previous values in that SAS data object? 
- Answer (WF): Yes.

- Question (WF): What to do when you have more than one variable to be sorted? Does it still through the BY statement?
- Answer (WF):
```SAS
    PROC SORT statement option:
        OUT=
    BY statement
```
\[Chapter 4, Problem 7\]
- Question (WF): Must you always have a data out in the proc signature? 
- Answer (WF): The PROC Step or Procedure Step processes one (or more) data set(s) in some way to produce a result. This step is one of two types of SAS program steps, the other being a DATA Step, both are fundamental components of the SAS Language.

\[Chapter 4, Problem 10\]
- Question (WF): what’s to do if we want to remove columns or rows for the table that is not sorted through frequency?
- Answer (WF): To remove observations in SAS, you can use the IF statement in a DATA step, search and remove matched observation. 

- Question (WF): Can you specify triple spacing or more within the proc print statement?
- Answer (WF): No, there is an only double space.

- Question(BP): Can PROC PRINT default be changed for a session?
- Answer(BP):DATA and PROC statements signal the beginning of a new step. When SAS encounters a subsequent DATA, PROC, or RUN statement (for DATA steps and most procedures) or a QUIT statement (for some procedures), SAS stops reading statements and executes the previous step in the program. In our sample program, each step ends with a RUN statement.
- Question(BP): Does Data step statement produces output after executing Data step statement?
- Answer(BP) When the program is processed, it creates the SAS data set. The DATA step produces messages in the SAS log, but it does not create a report or other output.

## Chapter 5 Questions
\[Chapter 5, Problem 1\]
-   Question (WF): Why the format here is ".dat"?
-   Answer (WF): “dat” file extension here only indicates that’s a data
    file, it can be text or csv.
    
\[Chapter 5, Problem 2\]
-   Question (WF): Once a fileref is assigned to an external file, can
    the fileref be saved and utilized in other SAS sessions? 
-   Answer (WF): File Shortcuts are active only during the current
    SAS session. 
    
\[Chapter 5, Problem 6\]
-   Question (WF): Where to define the name/position for Infile command?
-   Answer (WF): The FILENAME option defines a variable, whose name you
    supply, that SAS sets to the value of the physical name of the
    currently open input data set.
   
[Chapter 5, Problem 7]
- Question (AS): How to read a raw data set in which each observation's data values are on two lines?
- Answer (AS): SAS provides the slash (/) and #n to handle cases where more than one record in the input file is required to compose one observation in the dataset. When SAS encounters a slash, it continues to read values till end of Input statement. Then writes the PDV out as one observation. The slash is a relative line pointer and #n is a specifc line pointer.
- Question (SK): Is there a way we can change the columns name and its size once we defined them ? How can we delete a column or reduce its size?
- Answer (IW): To delete a column in the SAS output, use *DROP* in the data option:
```SAS
        data sales_new(drop=store_inventory);
            set sales_old;
        run;
```
Alternatively, to delete any variable in a *DROP* statement within the DATA statement:.
```SAS
        data sales_new;
            set sales_old;
            drop store_inventory;
        run;
```
To modify column name, use a *RENAME* statment:
 ```SAS
        data sales_new;
            set sales_old;
            rename store_inventory = total_inventory;
        run;
```

Then to modify the column size, use a *PROC SQL* statement:
 ```SAS
        proc sql;
         alter table sql.sales_new;
            modify total_inventory int(5);
        quit;
```

-   Question (WF): Why is StockNumber read in as a character instead of
    a numeric type?
-   Answer (WF): Stock Number is a name, not a numeric value that
    requires calculation.
    
-   Question (WF): With the Price variable, can a $ be used to identify
    the variable?
-   Answer (WF): Numeric variable can only contain number(s), not any
    other character.
    
-   Question (WF): Would the "data" and "run" portions of the statement
    also need to be included for this to run properly or is it complete
    on its own?
-   Answer (WF): The RUN statement is the last statement in a DATA
    Step and indicates to SAS that the step is complete and can now be
    run.\[Ch 5, Q8\]

-   Question (WF): How would you create a new variable and then subset
    based off of that variable? Is it possible to do in one data block?
-   Answer (WF):
```SAS 
        DATA auto;
                INPUT make $ price mpg foreign;
            DATALINES;
            AMC 4099 22 0
            Audi 6295 23 1
            ; 
                set import;
                where foreign = ‘1’
            run;
```
## Chapter 6 Questions
\[Chapter 6, Problem 1\]
-   Question (WF): What is the size of the input buffer?
-   Answer (WF): The default input buffer size on Windows is 256 bytes.

\[Chapter 6, Problem 2\]
- Question (WF): Since incorrect values and formats are not considered syntax errors, how can they best be detected and fixed?
- Answer (WF): Semantic Errors shows in the SAS log window, and <span id="z1377902" class="anchor"></span>you can use system options to control error handling (resolve errors) in your program.

- Question (WF): what does it look like in SAS execution step when there is incorrect values and formates?
- Answer (WF): SAS skids the wrong codes and write error to SAS log.

\[Chapter 6, Problem 3\]
- Question (AS): What are the additional commands used to direct the DATA step not to execute for each record? What are the conditions in which we need to use such commands and what are the advantages? Can we give an example?
- Answer (AS): Each iteration of a data step reads in data from the input file into the buffer,  the input statement writes it into the program data vector, and  at the end of the DATA step,SAS writes teh PDV contents out into the result dataset. Sometimes, you may need to test some conditions for selecting what observations get written out into teh result dataset. Based on an IF condition, The DELETE statement can be used to stop processing current iteration of data step and return to the beginning of the data step so that teh row is not written out to the result dataset.                  

- Question (WF): What type of statement is used for the data step to execute more than once for each record in the input file?
- Answer (WF): using \# to move pointer to different row of in the group, for example:

```SAS

        INPUT
        #1 row1 2. data1 $7. @11 ar1 1.
        #2 row2 2. data2 $7. @11 ar2 1.
```
\[Chapter 6, Problem 4\]
- Question (WF): At the beginning of the execution phase, can the value \_N\_  and \_ERROR\_ be different than the default value?
- Answer (WF): \_N\_<span id="a001375305" class="anchor"></span>is initially set to 1. Each time the DATA step loops past the DATA statement, the variable \_N\_ increments by 1. The value of \_N\_ represents the number of times the DATA step has iterated.<span id="a001375306" class="anchor"></span> \_ERROR\_<span id="a001375307" class="anchor"></span>is 0 by default but is set to 1 whenever an error is encountered, such as an input data error, a conversion error, or a math error, as in division by 0 or a floating point overflow. You can use the value of this variable to help locate errors in data records and to print an error message to the SAS log.

\[Ch 6, Q5\]
- Question (WF): Is it possible to sum up the total \_ERROR\_ count
    for a summary statistic?
- Answer (WF): \_*ERROR*\_ is a binary automatic variable, you need to
    write additional codes to sum up .
    
[Chapter 6 , Problem 6]
- Question (SK): When does LINES or CARDS  statements are used in the last statement of a data step ? when both are alias of   DATALINE statement?
- Answer: TBD

- Question (WF): Why is it so important that the variables initially be set to missing?
- Answer (WF): SAS must have some character to display for missing, it won't allow no character.



## Chapter 7 Questions

[Chapter 7 ,Problem 7]
- Question (SK): Need to see an example using "OTHER" for missing numeric values in a proc format step?
- Answer:TBD

## Chapter 8 Questions
\[Chapter 8, Problem 1\]
- Question (WF): Is it possible to create a stem-leaf display? 
- Answer (WF): Using The PROC UNIVARIATE statement.

- Question (WF): Does the raw data need to be totally clean before performing PROC statements?
- Answer (WF): No PROC step can also take actions when errors occur, but it is highly recommended to clean up data set in DATA step.

\[Chapter 8, Problem 4\]
- Question (WF): Is there any difference in the data output that would make either CLASS or BY a better choice, or is it simply a matter of ease and organization?
- Answer (WF): The input dataset must be sorted by the BY variables. It doesn't have to be sorted by the CLASS variables. The MEANS procedure is more efficient at treating BY groups than CLASS groups.

- Question (WF): When using BY with PROC SUMMARY should SORT need to be used first as well?
- Answer (WF): Yes.

\[Chapter 8, Problem 7\]
- Question (WF): How do you return a single ratio value from the sum of two columns? 
- Answer (WF):

```SAS
    DATA have;
         input COL1 COL2;
    DATALINE;
    2 4
    5 6
    ;
     run;
    PROC SORT data=have; 
        by COL1; 
    run;
    PROC MEAN data=have noprint;
        by COL1;
    output ratio=COL1/(COL1+COL2) out=want (drop = \_type\_ \_freq\_);
     run;
    proc print data=want;
    run;
```
\[Chapter 8, Problem 8\]
- Question (WF): What's the best way to work on continuous values, numeric values and unique values? Maybe to sort the data first before perform the frequency distribution? 
- Answer (WF): Recommended. By using PROC SORT, you can also do things like create a new data set, subset your data, rename, drop, keep,
format, or label your variables all in that same procedure.

\[Chapter 8, problem 10\]
- Question (WF): Does memory can impact when we use multiple PROC freq command to generate cross-tabulations.
- Answer (WF): Yes, The system option MEMSIZE sets a limit on the amount of memory used by the SAS System. The memory size impact SAS program performance in general.

## Chapter 10 Questions


## Chapter 11 Questions


## Chapter 12 Questions

\[Chapter 12, Problem 4\]
- Question (JG): What is the result of submitting the following program?

```SAS
        data work.getobs5;
            obsnum=5;
            set company.usa(keep=manager payroll) point=obsnum;
            stop;
        run;
```
- Answer (IW): The above program use *POINT* option to access 5th observation and the new output will produce the dataset work.getobs5 that contains values for manager and payroll variables for the 5th observation from company.usa dataset.  

## Chapter 13 Questions
\[Chapter 13, Problem 5\]
 - Question (IW): How do you convert a numeric date, eg: 01032020 to a SAS date?
 - Answer: TBD
 
## Chapter 14 Questions


## Chapter 15 Questions


## Chapter 16 Questions

[Chapter 16, Problem 5]
- Question (SK): What does COMMAw.d work and how does it interpret parenthesis?
- Answer (SK): The COMMAw.d informat does more than simply read the raw data values. It removes special characters such as    commas from numeric data and stores only numeric values in a SAS data set.

## Chapter 17 Questions

[Chapter 17, Problem 2]
- Question (SK): If we are unfamiliar with the SAS dataset how will we find the formats and variable names of each dataset?
- Answer (IW): Using the Holiday dataset in SAS, use *PROC CONTENTS* statement to review variable names and format:
```SAS
    proc contents data = sashelp.holiday
	    out = data_info(keep=name type length format);
    run;
```

## Chapter 19 Questions

[Chapter 19, problem 7]
- Question (SK): What is the difference between / and #n ? Which one is more preferable / or #n in order to read data value sequentially and no sequencially?
- Answer : TBD

## Chapter 20 Questions

[Chapter 20 , Problem 6]
- Question (SK): Is it possible to get the calculations like summation or average of the data values in each iteration when using @@?
- Answer: TBD
