# 🌞 DAY 1 🌞
## Land - 10'
☕ Coffee/tea 🫖

## Installation check, housekeeping - 15'
- ✅ Roll call + 🤝 Code of Conduct
- 🖥 Did everyone:
    - install python
    - download the materials
- 🙋 Getting help (🆘 red  ✅ green stickers)

## Icebreaker - 5'
A short icebreaker from [resources document](https://tud365.sharepoint.com/:w:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/resources.docx?d=waea671d7fc6a46d5b5c068fc19f41940&csf=1&web=1&e=f2QYgy)


## Introduction to version control - 10'
- 🎦 introduce git using [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20programming%20with%20Python.pptx?d=w0d581778c4b0479ab36e1e1706535b88&csf=1&web=1&e=gdimt4) 
- Why python?
- Why avoid generative AI during the workshop
- Explain the scenario
- Explain the CSV data

## Start Jupyter notebook
- Open terminal
- Navigate to Desktop
    - Note that users of Windows 10 will probably save the data in `OneDrive` Desktop.  
    - `"/c/Users/[username]/OneDrive\ -\ Delft\ University\ of\ Technology\Desktop"`
- Navigate to `data` directory (inside `swc-python`)
- Launch jupyter notebook

### Live coding - 10'
- Mac open Terminal
- Windows open Miniforge prompt
```
conda activate carpentries
cd ~/Desktop/swc-python/data
jupyter notebook
```
- Start a new jupyter notebook -> Python 3
- Rename and save

## Python Fundamentals

### Live coding - 20'
#### Variables
```
3 + 5 * 4               # python as calculator 
weight_kg = 60          # assign value to a variable with =
weight_kg               # python recalls value assigned to variable
```
A variable is a `name for a value`
* May include letters, digits and underscores
* May not start with a digit
* are _case sensitive_

#### Types of data
Three most common types:
* integer numbers
* floating point numbers
* strings
```
type(weight_kg)             # integer
weight_kg = 60.3            # add a floating point decimal
weight_kg                   # display new value
type(weight_kg)             # now variable is type float
patient_id = '001'          # single quotes to create a str
type(patient_id)            # function type shows the type of variable patient_id
```
#### Using variables
```
weight_lb = 2.2 * weight_kg             # make calculations
weight_lb                               # display new value
patient_id = 'inflam_' + patient_id     # add a prefix to string -> + concatenates
patient_id                              # display new value
```
#### Built-in functions
```
print(weight_lb)                # display info in screen
print(patient_id)               # follow function name by parenthesis
print(patient_id, 'weight in kilograms:', weight_kg) # multiple things at once
```
#### Getting help
```
help(print)         # shows docstring with parameters and usage
```

### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document
    - Check your understanding
    - Sorting out references

## Break - 15'

## Analyzing Patient Data

### Live coding - 20'
#### Loading data into Python
- Importing a library is like getting a piece of lab equipment
- Only import what you need so it doesn't get messy
```
import numpy            # numerical python. Good for matrices operations
numpy.loadtxt(fname='inflammation-01.csv', delimiter=','). # explain function call, . notation and parameters
type(data)              # n-dimensional array
data.shape              # array shape
```
-  📉 Draw on board 60 rows -> patients and 40 columns -> days

```
print('first value in data:', data[0, 0]) # single number from array we use an index
print('middle value in data:', data[29, 19]) #row 30, column 20.

```
- 📉 Explain on the board the Python indexing [row, columns]
    - Explain zero based indexing -> offset from the first value in the array
- [Optional] 🎦 use picture in slides

#### Slicing data
- Reiterate the use of square brackets
```
print(data[0:4, 0:10])          # select a section using :
```
- 0:4-> "start at index 0 and go up to, not including, index 4"
```
print(data[5:10, 0:10])         # start the slice where ever you want
print(data[:3, 36:])            # no lower bound starts at zero, no upper bound goes to end 
```

### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Slicing strings

#### Analyzing data with numpy

### Live coding - 10'
- Default functions from `numpy`
```
print(numpy.mean(data))         # mean is a function. data is the argument
maxval = numpy.max(data)
minval = numpy.min(data)
stdval = numpy.std(data)        

print('maximum value', maxval)
print('minimum value', minval)
print('standard deviation',stdval)
```
- Demo `numpy`. **TAB** to visualize the functions available from the library

#### Numpy axes - 10'
```
patient_0 = data[0, :] # 0 on the first axis (rows), everything on the second (columns)
print('maximum inflammation for patient 0:', numpy.amax(patient_0))
print('maximum inflammation for patient 2:', numpy.amax(data[2, :])) # no need to store in variable

```
- 🎦  Explain numpy axes with slides
    - axis 0 -> walks along rows
    - axis 1 -> walks along columns

```
print(numpy.max(data, axis=1)) # the same for all patients at once
print(numpy.max(data, axis=1).shape) # 60 patients
print(numpy.max(data, axis=0)) # the same for all days at once
print(numpy.max(data, axis=0).shape) # 40 days
print(numpy.mean(data, axis=1)) # mean inflammation for all patients at once
```

### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document
    - Change in inflammation


### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Plot scaling
    - Drawing straight lines

### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Make your own plot
    - Moving plots around

## Storing Multiple Values in Lists
### Live coding - 20'
```
odds = [1, 3, 5, 7]
print('odds are:', odds)

print('first element:', odds[0])
print('last element:', odds[3])
print('"-1"th element:', odds[-1])

names = ['Curie', 'Darwing', 'Turing']
print('names is originally:', names)
names[1] = 'Darwin' # correct our typo
print('final value of names:', names)

name = 'Darwin'
name[0] = 'd'
```

### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Overloading
    - Non-continuous slices

### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Slicing from the end


### 💪  Challenge - 30'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - From 1 to N
    - Understanding the loops
    - Summing a list
    - Computing the Value of a polynomial


### 💪  Challenge - 20'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Plotting Differences
    - Generate Composite Statistics


## Key points - 10'
```

```


# 🌞 DAY 2 🌞
## Land - 10'
☕ Coffee/tea 🫖

## Installation check, housekeeping - 15'
- ✅ Roll call + 🤝 Code of Conduct
- 🖥 Restart Jupyter notebook
- 🙋 Getting help (🆘 red  ✅ green stickers)

## Icebreaker - 5'
A short icebreaker from [resources document](https://tud365.sharepoint.com/:w:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/resources.docx?d=waea671d7fc6a46d5b5c068fc19f41940&csf=1&web=1&e=f2QYgy)

## Recap from day one - 10'
```
```

## Making choices

### Live coding - 20'
```
```

### 💪  Challenge - 15'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - What Is Truth?
    - Close Enough
    - Sorting a List Into Buckets

### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Combining Strings
    - Testing and Documenting Your Function

### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Rescaling an Array
    - Defining Defaults
    - Testing and Documenting Your Function

### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Reading Error Messages

### 💪  Challenge - 15'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Identifying Syntax Errors
    - Identifying Variable Name Errors
    - Identifying Index Errors



### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Pre- and Post-Conditions

### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Testing Assertions

### 💪  Challenge - 40'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Debug With a Neighbor
    - Not Supposed to be the Same
    - TODO other debugging excersices (missing "", ], : )

### 💪  Challenge - 40'
TODO a big practice exercise

## Key points - 10'
```

```

## Feedback - 10'
* Ask participants to fill in the feedback survey