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



