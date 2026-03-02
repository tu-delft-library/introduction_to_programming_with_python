# 🌞 DAY 1 🌞
## Land - 10'
☕ Coffee/tea 🫖

## Installation check, housekeeping - 15'
- ✅ Roll call + 🤝 Code of Conduct
- 🖥 Did everyone:
    - install python
    - install `carpentries` enviroment
    - download the materials
- 🙋 Getting help (🆘 red  ✅ green stickers)

## Icebreaker - 5'
A short icebreaker from [resources document](https://tud365.sharepoint.com/:w:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/resources.docx?d=waea671d7fc6a46d5b5c068fc19f41940&csf=1&web=1&e=f2QYgy)


## Introduction to version control - 10'
- 🎦 introduction with [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20programming%20with%20Python.pptx?d=w0d581778c4b0479ab36e1e1706535b88&csf=1&web=1&e=gdimt4) 
- Why python?
- Why avoid generative AI during the workshop
- Explain the scenario
- Explain the CSV data

## Start Jupyter notebook - 10'
- Open terminal:
    - Mac open Terminal
    - Windows open Miniforge prompt
- Activate carpentries conda environment
```
conda activate carpentries
```
- Navigate to Desktop
```
cd ~/Desktop
```
- Users of Windows 10 will probably save the data in `OneDrive` Desktop.  
    `"/c/Users/[username]/OneDrive\ -\ Delft\ University\ of\ Technology\Desktop"`

- Navigate to `data` directory (inside `swc-python` inside)
```
cd swc-python/data
```
- Explain jupyter notebook will run in the current working directoy
- Launch jupyter notebook
```
jupyter notebook
```


- Start a new jupyter notebook using Python 3
- Rename and save

## Python Fundamentals - 20'


### Variables
```
3 + 5 * 4               # python as calculator 
weight_kg = 60          # assign value to a variable with =
weight_kg               # python recalls value assigned to variable
```
A variable is a `name for a value`
* May include letters, digits and underscores
* May not start with a digit
* are _case sensitive_

### Types of data
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
### Using variables
```
weight_lb = 2.2 * weight_kg             # make calculations
weight_lb                               # display new value
patient_id = 'inflam_' + patient_id     # add a prefix to string -> + concatenates
patient_id                              # display new value
```
### Built-in functions
```
print(weight_lb)                # display info in screen
print(patient_id)               # follow function name by parenthesis
print(patient_id, 'weight in kilograms:', weight_kg) # multiple things at once
```
### Getting help
```
help(print)         # shows docstring with parameters and usage
```

### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document
    - Check your understanding
    - Sorting out references

## Break - 15'


## Lists - 20'
`lists` ordered collection of elements
```
odds = [1, 3, 5, 7]                 # use square brackets separate with commas
print('odds are:', odds)

print('first element:', odds[0])    # access elements using indices: first is 0
print('last element:', odds[3])     
print('"-1"th element:', odds[-1])  # last element -1. Counts backwards from the end
print('"-2"th element:', odds[-2])  # second to last element

names = ['Curie', 'Darwing', 'Turing'] # a list of any data type e.g. str
print('names is originally:', names)
names[1] = 'Darwin'                     # correct our typo
print('final value of names:', names)

name = 'Darwin'                 
name[0] = 'd'                # str can not be corrected the same way -> immutable
```

`lists` are mutable and `strings` are immutable
- `immutable` types can only be updated by replacing old value with a new one
- `mutable` modify individual elements using indices
`lists` can contain elements of different types
```
sample_ages = [10, 12.5, 'Unknown']
```

`lists` can be modified
```
odds.append(11)             # add element at the end
print('odds after adding a value:', odds)

odds.pop(0)   # pop removes an element in a specific index
print('odds after removing the first element:', odds)

odds.reserve()
print('odds after reversing:', odds)
```
Careful when modifying `lists` in-place. Variables pointing to the same list stay `connected`. Both variables are pointing to the same list.
```
odds = [3, 5, 7]
primes = odds
primes.append(2)
print('primes:', primes)
print('odds:', odds)
```
For a simple copy, better to use the `list()` command
```
odds = [3, 5, 7]
primes = list(odds)
primes.append(2)
print('primes:', primes)
print('odds:', odds)
```
A note about slicing: similarly to a numpy array, `lists` and `strings` can be sliced
```
name = 'dolores santos'
name[0:7]                                   # how it works in a string

chromo = ['X', 'Y', '2', '3', '4']          # how it woks in a list
chromo[2:5]

chromo[-1]

```
### 💪  Challenge - 15'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Slicing from the end
    - Non-continuous slices

## More Lists - 15'
- 🎦 Use [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20programming%20with%20Python.pptx?d=w0d581778c4b0479ab36e1e1706535b88&csf=1&web=1&e=gdimt4) to explain `nested lists`

```
veg = [['lettuce', 'lettuce', 'peppers', 'zucchini'],
     ['lettuce', 'lettuce', 'peppers', 'zucchini'],
     ['lettuce', 'cilantro', 'peppers', 'zucchini']] # a list that contains other lists
print(veg[2]) # row at the bottom of the shelf 
print(veg[0]) # row at the top of the shelf
print(veg[0][0]) # basket top left corner
```

- Omitting first/last index
```
date = 'Monday 4 January 2016'
day = date[0:6]
print(day)
day = date[:6]                  # omit first index
print(day)
months = ['jan', 'feb', 'mar', 'apr', 'may', 'jun']
till_summer = months[3:7]
print(till_summer)
till_summer = months[3:]        # omit last index
print(till_summer)
```


### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Overloading


## Loops - 20'
- why `loops` -> repeated actions on long lists
```
odds = [1, 3, 5, 7]         # list with ordered elements
print(odds[0])              # access via index
print(odds[1])
print(odds[2])
print(odds[3])              # if list is long this becomes very tedious
```
- Enter `loops` -> a structure that allows to repeat an operation once for each element in a sequence
```
for number in odds:        # The : marks the start of the loop
    print(number)          # indention defines the block of the code that will be repeated
odds = [1,3,5,7,9,11,13,15,17,19,21]    # a longer list
for number in odds:         # runs the loop and it works again
    print(number)
```
- Loop variable can have any name. Recommended to use descriptive names
```
for banana in odds:
    print(banana)
for odd in odds:        # another standard -> singular of the list name
    print(odd)
```
- Another example.
```
length = 0
names = ['Curie', 'Darwin', 'Turing']
for value in names:
    length = length + 1            
print('There are', length, 'names in the list.')
```
- Analyse step by step. Notice when the variables are modified.
    - run 1 -> length = 0, value = 'Curie', +1, length = 1
    - run 2 -> length = 1, value = 'Darwin', +1, length = 2
    - run 3 -> length = 2, value = 'Turing', +1 , length = 3
- Notice the variable still exists when the look is over

```
name = 'Rosalind'
print(name)
for name in ['Curie', 'Darwin', 'Turing']:
    print(name)
print('after the loop, name is', name)
```
- `len` is a built-in function
```
print(len([1,2,3,4,5]))
print(len(names))
print(len(odds))
```

### 💪  Challenge - 30'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - From 1 to N
    - Understanding the loops
    - Summing a list
    - Computing the Value of a polynomial

## Break - 60'

## Analyzing Patient Data

### Loading data - 10'
- Importing a library is like getting a piece of lab equipment
- Only import what you need so it doesn't get messy
- Use shortcut to import numpy 
```
import numpy as np          # numerical python. Good for matrices operations
np.loadtxt(fname='inflammation-01.csv', delimiter=','). # explain function call, . notation and parameters
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
- 🎦 use picture in [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20programming%20with%20Python.pptx?d=w0d581778c4b0479ab36e1e1706535b88&csf=1&web=1&e=gdimt4) 


### Slicing data - 10'
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


### Analyzing data - 10'
- Default functions from `np`
```
print(np.mean(data))         # mean is a function. data is the argument
maxval = np.max(data)
minval = np.min(data)
stdval = np.std(data)        

print('maximum value', maxval)
print('minimum value', minval)
print('standard deviation',stdval)
```
- Demo `numpy`. **TAB** to visualize the functions available from the library

### Numpy axes - 10'
```
patient_0 = data[0, :] # 0 on the first axis (rows), everything on the second (columns)
print('maximum inflammation for patient 0:', np.amax(patient_0))
print('maximum inflammation for patient 2:', np.amax(data[2, :])) # no need to store in variable

```
- 🎦  Explain np axes with [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20programming%20with%20Python.pptx?d=w0d581778c4b0479ab36e1e1706535b88&csf=1&web=1&e=gdimt4) 

    - axis 0 -> walks along rows
    - axis 1 -> walks along columns

```
print(np.max(data, axis=1)) # the same for all patients at once
print(np.max(data, axis=1).shape) # 60 patients
print(np.max(data, axis=0)) # the same for all days at once
print(np.max(data, axis=0).shape) # 40 days
print(np.mean(data, axis=1)) # mean inflammation for all patients at once
```

### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document
    - Change in inflammation

## Break - 15'

## Visualizing Tabular Data

### Visualizing - 20'
- Use shortcut to import matplotlib 
```
import matplotlib.pyplot as plt # another handy library using short-cut
image = plt.imshow(data) # heatmap: low values are blue, high values are yellow     
```
- Quickly observe tendency of inflammation flare-ups around day 20 🔥
- Patients take medication and inflammation drops to zero in about 3 weeks 👍

```
plt.plot(np.mean(data, axis=0))       # avg inflammation per day. Reasonable rise and fall plot
plt.plot(np.max(data, axis=0))         # linear seems unlikely
plt.plot(np.min(data, axis=0))         # step function seems unlikely
```
- Max and min look suspicious. This requires further investigation 😶

### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Plot scaling
    - Drawing straight lines

### Grouping plots - 15'
- `figure` creates a space (like a blank canvas) where to place our plots
- `add_subplot` takes 3 parameters: rows, columns, which subplot
- `set_ylabel` to name the axis
- `savefig` stores plot in a file (can be png, svg, pdf, jpeg)
```
fig = plt.figure(figsize=(10.0, 3.0))       # create a blank canvas and set size

axes1 = fig.add_subplot(1, 3, 1)            # 1 row, 3 columns, plot 1
axes2 = fig.add_subplot(1, 3, 2)            # 1 row, 3 columns, plot 2
axes3 = fig.add_subplot(1, 3, 3)            # 1 row, 3 columns, plot 3

axes1.set_ylabel('average')                 
axes1.plot(np.mean(data, axis=0))

axes2.set_ylabel('max')
axes2.plot(np.amax(data, axis=0))

axes3.set_ylabel('min')
axes3.plot(np.amin(data, axis=0))

plt.savefig('inflammation.png')

```

### 💪  Challenge - 10'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Make your own plot
    - Moving plots around

## Break - 15'
### Analysing multiple files - 15'
- `glob` a library to get a list of all files in a directory

```
print(glob.glob('inflammation*.csv')) # wildcard * matches zero or more characters
# arbitrary order
```
```
import glob             
import numpy as numpy
import matplotlib.pyplot as plt

filenames = sorted(glob.glob('inflammation*.csv'))  
for filename in filenames[0:3]:
    print(filename)        

    data = numpy.loadtxt(fname=filename, delimiter=',')

    fig = matplotlib.pyplot.figure(figsize=(10.0, 3.0)) # one figure per file

    axes1 = fig.add_subplot(1, 3, 1)                    # 3 plots per file
    axes2 = fig.add_subplot(1, 3, 2)
    axes3 = fig.add_subplot(1, 3, 3)

    axes1.set_ylabel('average')
    axes1.plot(numpy.mean(data, axis=0)) # along rows = patients -> values per day

    axes2.set_ylabel('max')
    axes2.plot(numpy.amax(data, axis=0)) # along rows = patients -> values per day

    axes3.set_ylabel('min')
    axes3.plot(numpy.amin(data, axis=0)) # along rows = patients -> values per day

    matplotlib.pyplot.show()            # so that it renders after printing the filename
```
- File 1 and 2 -> similar patterns
- File 3 -> suspicious minima

```
data = np.loadtxt(fname='inflammation-03.csv',delimiter=',')
plt.imshow(data)
```
- Notice zero values spread across patients and days. ❗ Potential problem with data collection❗
### 💪  Challenge - 20'
- TODO notebook
- Exercise notebook link + instructions in collaborative document:
    - Plotting Differences
    - Generate Composite Statistics

## Forgive the imaginary Dr. Maverick -5'
🎦 Use [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20programming%20with%20Python.pptx?d=w0d581778c4b0479ab36e1e1706535b88&csf=1&web=1&e=gdimt4) 


## Key points - 10'
```
variables = 3 # variable to store values
i = 10
f = 10.3
s = 'strings'

s[3]
s[:4]
s[2:]
s[-1]
s[-2]

li = [1,2,3,4]

li[0]
li[2:4]
for k in li:
    print(k)

import numpy as np
data = np.loadtxt(fname='inflammation-01.csv',delimiter=',')
np.mean(data, axis=0)

import matplotlib.pyplot as plt
plt.imshow(data)
plt.plot(np.mean(data, axis=0))
plt.show()

import glob
sorted(glob.glob('inflammation*.csv'))
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