# Data Analysis in Base Python - Introduction

In this section, you'll continue solidifying your knowledge of Python programming, descriptive statistics, and data visualization by performing key data analysis tasks. You will learn how to load data from CSV and JSON files into Python objects in memory, and wrap up with an analysis that joins together two datasets.

## Lesson Priorities
### 1st Priority

If you are short on time, be sure to make it through these items:
- File Input and Output in Python
- CSV
- JSON
- Data Serialization Formats - Cumulative Lab
> Note: If you can't yet see the cumulative lab, don't worry.  It may not be visible until a pair programming session led by your instructor.

### 2nd Priority
- JSON - Lab: 
>Good additional practice with key/value pairs, accessing a list by index values, and for loops.
- Working with Known JSON Schemas
- Working with Known JSON Schemas - Lab

### Appendix

Once you are familiar with file input/output in Python, CSV's, and JSONs, move on to the appendix.  

In it you will find even another opportunity to practice JSON's in the **Exploring and Transforming JSON Schemas** lesson/lab pair.  

You will also find a lesson/lab pair that goes into more detail about XML. XML is less important than JSON to the scope of the program, but important to know about for webscraping and general familiarity with common data structures.

## Base Python

When we say "base Python", this means that we are emphasizing the data types and modules that are part of Python itself, rather than using third-party libraries. For much of this course, you will use numerous Python libraries such as `pandas` and StatsModels, but first we want to dig into how data analysis tasks can be performed without them.

### Python Data Types and Control Structures

In this section, our data is stored in data structures that are built into the Python language: numbers, strings, lists, dictionaries, etc. For example, if we have this table of data:

| color  | number |
| ------ | ------ |
| green  | 7      |
| red    | 2      |
| orange | 1      |

A standard way we might represent that table would be a list of dictionaries, where each dictionary represents a row and has the keys `color` and `number`:

Then if we wanted to print out all of the values associated with the `color` keys, the logic would look something like this:

In later sections of this course, that same task (printing the list of colors) might look something like this, using the `pandas` library:

In the base Python example, we had a variable `info_table` which was type `list` (a built-in Python type), whereas in the pandas example, we had a variable `df` which was type `pandas.core.frame.DataFrame` (a custom type from the pandas library).

Then to print out the colors, in the base Python example we had a `for` loop and then code to extract the information from each individual dictionary. The string values got printed out without any additional markup. Then in the pandas example we did not have to use a loop (hint: this is *broadcasting* like we saw previously with NumPy) and also we had some extra markup where it printed out the index values as well as `Name: color, dtype: object`.

In this section you will practice performing data analysis with the first (base Python) format, before eventually learning how to use pandas instead.

### Python Modules

In addition to the data types used, we will also use built-in Python modules. These modules must be imported, but they are part of Python itself and do not require separate installation.

The main modules we will focus on are `csv` ([documentation here](https://docs.python.org/3/library/csv.html)) and `json` ([documentation here](https://docs.python.org/3/library/json.html)).

## Loading Data from Files

While trivial example data structures like the one above can be declared directly in Python code, more realistic data comes in the form of a file on disk.

In this section you will practice opening data files that use the CSV and JSON formats, then loading them into sensible objects using the `csv` and `json` libraries in order to perform additional analysis.

### CSV Files

The first major file type we will explore is CSV (comma-separated value). For example, this code loads a dataset of 5000 apple trees in an orchard, where the column `yield` represents the total pounds of apples yielded by that tree for a given year.

You can think of the table as looking like this, except that it is thousands of lines long:

| yield              |
| -----------------  |
| 39.741234289561504 |
| 39.872054738763474 |
| 44.33116416558151  |
| 46.6006230827385   |
| 40.694984210927196 |
| 40.96981882686812  |

In relatively few lines of code, we can perform some key data analysis tasks: counting, measuring central tendency, finding the maximum, and finding the minimum.

### JSON Files

The second major file type we will explore is JSON (JavaScript object notation). For example, this code loads a dataset of interactions between Twitter users, where each user is represented as a "node" and when one tweets at another that connection is represented as a "link".

You can think of this data as looking like this, although this version is truncated:

```
{
  'nodes': [
    {'id': '347457291'},
    {'id': '232762581'},
    {'id': '23678636'},
    {'id': '21278412'},
    {'id': '222040026'},
    {'id': '19579205'},
    {'id': '222957350'},
    {'id': '264013722'},
    ...
  ],
  'links': [
    {'source': '347457291', 'target': '232762581'},
    {'source': '347457291', 'target': '119706266'},
    {'source': '347457291', 'target': '421509544'},
    {'source': '232762581', 'target': '222957350'},
    {'source': '232762581', 'target': '21648607'},
    {'source': '232762581', 'target': '155691033'},
    {'source': '232762581', 'target': '59974294'},
    ...
  ]
  ...
}
```

In relatively few lines of code, we can count the number of users and find the users who were "sources" (the user initiating a tweet that tags someone else) most often and "targets" (the user being tagged in a tweet) most often.

## What About NumPy and Matplotlib?

You can continue using NumPy and Matplotlib as you see fit. For example, if you want to convert a base Python list into a NumPy array because it will help you perform some descriptive analysis task, that is not an issue. You will also need to use Matplotlib in the lessons ahead to create the required visualizations.

The main library that you will *not* be using extensively is `pandas`, which will be introduced in a future section.

## Summary

In this section you will learn how to load and manipulate CSV and JSON datasets using base Python. This means that we will mainly be using the data structures and modules built into Python, rather than third-party libraries. We also walked through some examples of the kinds of analysis you will be able to perform by the end of this section.
