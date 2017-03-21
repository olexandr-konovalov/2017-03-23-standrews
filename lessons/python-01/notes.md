# LESSON 01 - Building Programs With Python

These notes are a guide to the speaker, as they present the material.

----
**SLIDE** Building Programs With Python (1)

----
**SLIDE** INTRODUCTION

----
**SLIDE** GOAL 1

* We are teaching programming, not `Python` *per se*
* We need to use *some* language, though
* Python is free, and likely to be usable on your machine
* Python is widely-used, and there's lots of support online
* It can be easier for novices to pick up than other languages
* You should use what is common in your area/with your colleagues
* The principles of programming are the same in other languages

----
**SLIDE** GOAL 2

* We're using a motivating example of data analysis
* Data is in plain text, tabular (CSV)
* Data represents patients and daily measurements
* We're going to analyse the data
* We're going to visualise the data
* We're going to get the computer to do this for us
* Automation is key: fewer human mistakes, easier to apply to other datasets, and share with others (transparency)

----
**SLIDE** SETUP

----
**SLIDE** SETTING UP - 1 - **DEMO**

* We want a neat (clean) working environment
* Change directory to desktop (in terminal or Explorer)
* Create directory `python-novice-inflammation`
* Change your working directory to that directory

----
**SLIDE** SETTING UP - 2 - **DEMO**

* We need to acquire our data (and also a little code that can help us)
* Copy `.zip` files from repository (or online!) **PUT IN ETHERPAD**
* Extract files (command-line or in Explorer)

----
**SLIDE** GETTING STARTED

----
**SLIDE** STARTING `JUPYTER` **DEMO**

* Start `Jupyter` from the command-line

----
**SLIDE** `JUPYTER` LANDING PAGE **DEMO**

* Landing page is a file browser, like Explorer/Finder
* Point out `Python` (`.py`) files, `.zip` files, and directories)
* Point out directory (`data`), and how the file symbols are different.
* Point out `New` button.

----
**SLIDE** CREATE A NEW NOTEBOOK **DEMO**

* Click on `New -> Python 3`
* Point out that there may or may not be other options in the student's installation
* Indicate the new features on the empty notebook:
  * The notebook name: `Untitled`
  * Checkpoint information
  * The menu bar (`File Edit etc.`) - just like `Word` or `Excel`
  * An indication of which kernel you're using/language you're in
  * Icon view (just like `Word` or `Excel`)
  * An empty cell with `In [ ]:`

----
**SLIDE** MY FIRST NOTEBOOK **DEMO**

* Give the notebook the name `variables`

----
**SLIDE** CELL TYPES **DEMO**

* `Jupyter` documents are comprised of `cells`
* A `cell` can be one of several types - we'll focus on two:
  * `Code`: code in the current kernel/language
  * `Markdown`: text, with the opportunity for formatting
* Change the first cell type to `Markdown`
  * The box colour changes from green to blue
  * The `In []` prompt disappears

----
**SLIDE** MARKDOWN TEXT **DEMO**

* `Markdown` lets us enter formatted text
  * Headers are preceded by a hash: `#`
  * The level of header is determined by the number of hashes: `#`
  * Italics are shown by enclosing text in single asterisks: `*italic*`
  * Typewriter text/code is shown by enclosing in backticks: ```
  * LaTeX can be entered within dollar signs `$`
* Press `Shift + Enter` to execute a cell
* The cell is rendered, and a new cell appears beneath the executed cell

----
**SLIDE** ENTERING CODE **DEMO**

* Mathematical statements can be entered directly into a code cell
  * **ENTER `1+2`**
* Before the cell is executed, note that the `In []` prompt has no value in it
* Note that the code is colour syntax-highlighted
  * **EXECUTE THE CELL**
* Note that after execution, the `In []` prompt now has a number in it to indicate the order in which cells are executed
* Note also that because there is no place to put the output, a value has been returned as `OUT [1]`, showing the result of the calculation
* A new code cell is created beneath the executed cell.
* **ASK THE LEARNERS GO THROUGH THE EXERCISE**

----
**SLIDE** MY FIRST VARIABLE

* **TYPE THE MARKDOWN IN A CELL AND EXECUTE**
  * This is to keep the notebook as an example of literate programming (and a handy reference for the students)
* You can think of a variable as a labelled box, containing a data item
  * Here, we have a box labelled `Name` - this is the variable name
  * We've put the value `Samia` into the box
  * **LET'S DO THIS FOR REAL IN PYTHON**
    * To *assign* a value we use the *equals sign*
    * The variable name/box label goes on the left, and the data item goes on the right
    * *Character strings*, or *strings*, are enclosed in quotes
    * Executing the cell assigns the variable
  * So now, if we refer to the variable `Name`, we get the value that's in the box: `Samia`

----
**SLIDE** WORKING WITH VARIABLES

* Lead the students through the code:

```python
weight_kg = 55
print(weight_kg)
2.2 * weight_kg
print("weight in pounds", 2.2 * weight_kg)
weight_kg = 57.5
print("weight in kilograms is now:", weight_kg)
```

* Assign an integer (assignment is the same for all data items)
* Print `weight_kg` to see its value
* Variables can be substituted by name wherever a value would go
* The `print()` function will take more than one argument, separated by commas, and print them
* Reassigning to the same variable overwrites the old value

* **Changing the value of one variable does not change the values of other variables**
* Lead students through the code

```python
print(weight_kg)
weight_lb = 2.2 * weight_kg
print('weight in kilograms:', weight_kg, 'and in pounds:', weight_lb)
weight_kg = 100
print('weight in kilograms:', weight_kg, 'and in pounds:', weight_lb)
```
* **Although we changed the value in `weight_kg`, we did not change `weight_lb` when we did so**

----
**SLIDE** DATA ANALYSIS

----
**SLIDE** START A NEW NOTEBOOK

* Create a new notebook, and give it the name `analysis`

----
**SLIDE** EXAMINE THE DATA

* Use the terminal (`head` from this morning)
 
```bash
head data/inflammation-01.csv
```

* Describe plain text, csv format
* State that we'll use the `numpy` library

----
**SLIDE** `PYTHON` LIBRARIES

* `Python` contains many basic and general functions and tools
* Specialised tools are packaged in *libraries*
* We can call on libraries with the `import` statement, when we need them
* Importing a library is like getting a new piece of equipment out of the locker and onto the lab bench
* Libraries add functionality to your current `Python` instance

----
**SLIDE** `JUPYTER` MAGIC

* `Jupyter` provides another way to load libraries, through *magics*
* **Do the `pylab` magic**
* **Import `numpy` and `seaborn`**
* Note that warnings about fonts may be normal.

----
**SLIDE** `NUMPY`, `SEABORN`, `PYLAB`

* `numpy` is a library that provides functions and pethods to work with arrays and matrices, such as those in your dataset
* `seaborn` is a library that enables attractive graphs and statistical summaries
* `pylab` is a library that mimics `MatLab` in `Python`, providing a number of useful tools for numerical operations and visualisation

----
**SLIDE** LOAD DATA

* The `numpy` library gives us a function called `loadtxt()` that loads tabular data from a file
* It's used as `numpy.loadtxt()`
* *Dotted notation* tells us that `loadtxt()` belongs to `numpy`
* `loadtxt()` expects two *arguments* or *parameters*
* The parameter `fname` takes the path to the file we want to load
* The parameter `delimiter` takes the character that we think separates columns in that file
* `Python` will accept double- or single-quotes around strings
* **Execute the line in a cell**

----
**SLIDE** LOADED DATA

* Since we didn't ask `Python` to do anything with the data, it just shows it to us.
* The data display is truncated by default - *ellipses* (`...`) show rows and columns that were excluded for space 
* Significant digits are not shown
* **NOTE that integers in the file have been converted to floating point numbers**
* **Ask the learners to assign the matrix to a variable called `data`**

----
**SLIDE** WHAT IS OUR DATA? **LIVE DEMO**

* Take the learners through the code:

```python
type(data)
print(data.dtype)
print(data.shape)
```

* `type(data)` is a `numpy.ndarray` - an *n*-dimensional array
* `print(data.dtype)` tells us that the values in the array are 64-bit floating point numbers
* `print(data.shape)` tells us that there are 60 rows and 40 columns in the dataset

----
**SLIDE** MEMBERS AND ATTRIBUTES

* When we created `data` we didn't just create the array, we also created information about the array, called *members* or *attributes*
* This information belongs to `data` so is accessed in the same way as a module function, through *dotted notation*

----
**SLIDE** INDEXING ARRAYS

* **Take learners through making notes in the notebook**
* To get a single element from the array, index using *square bracket* notation - row first, then column
* In `Python` we index from zero, so the first element is `data[0, 0]`
* **Do the two `print()` examples**

```python
print('first value in data:', data[0, 0])
print('middle value in data:', data[30, 20])
```

----
**SLIDE** SLICING ARRAYS

* **Take learners through making notes in the notebook**
* To get a section from the array, index using *square bracket* notation - but specify start and end points, separated by a colon
* The slice `0:4` means start at index zero and go up to, but not including, index 4. So it takes elements `0, 1, 2, 3` (four elements)
* **Do the two `print()` examples**

```python
print(data[0:4, 0:10])
print(data[5:10, 0:10])
```

----
**SLIDE** MORE SLICES, PLEASE!

* If we don't specify a start for the slice, `Python` assumes the first element is meant (element zero)
* If we don't specify an end for the slice, `Python` assumes the last element is meant
* To get the top-right corner of the array, we can specify `data[:3, 36:]`
* **Demo the code**

```python
small = data[:3, 36:]
print('small is:')
print(small)
```

----
**SLIDE** ARRAY OPERATIONS

* Arithmetic operations on `array`s are performed elementwise.
* **Demo the code**
* Operations with scalars act *elementwise*
* Operations with two arrays are *elementwise*

```python
doubledata = data * 2.0
print('original:')
print(data[:3, 36:])
print('doubledata:')
print(doubledata[:3, 36:])
```