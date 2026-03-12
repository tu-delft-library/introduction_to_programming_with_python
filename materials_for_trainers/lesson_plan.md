# 🌞 DAY 1 🌞
## 9:00 - Land - 10' - Cata
☕ Coffee/tea 🫖

## 9:10 - Housekeeping - 15' - CATA
- ✅ Roll call + 🤝 Code of Conduct
- 🖥 Did everyone:
    - install python
    - install `carpentries` environment
    - download the materials
- 🙋 Getting help (🆘 red  ✅ green stickers)

## 9:25 - Icebreaker - 5' - CATA
Find someone whose name starts with the last letter of your name: CATALINA -> ANDREA

Ask them: what is your favorite movie from childhood and what is it now?
 

## 9:30 - Introduction to python - 10' - CATA
- 🎦 introduction with [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20programming%20with%20Python.pptx?d=w0d581778c4b0479ab36e1e1706535b88&csf=1&web=1&e=gdimt4) 
- Why python?
- Why avoid generative AI during the workshop
- Explain the scenario
- Explain the CSV data

## 9:30 - Start Jupyter notebook - 10' - CATA
- Open terminal:
    - Mac open Terminal
    - Windows open Miniforge prompt
- Activate `carpentries` conda environment
```
conda activate carpentries
```
- Navigate to `swc-python` (where ever this may be)
```
cd ~/Desktop/swc-python
```
- Explain jupyter notebook will run in the current working directory
- Launch jupyter notebook
```
jupyter notebook
```

- Start a new jupyter notebook using Python 3
- Rename to `one` and save (not `day_one` to avoid confusion with directory name `data`)

## 9:45 - Python Fundamentals - 15' - CATA


### Variables
```python
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
```python
type(weight_kg)             # integer
weight_kg = 60.3            # add a floating point decimal
weight_kg                   # display new value
type(weight_kg)             # now variable is type float
patient_id = '001'          # single quotes to create a str
type(patient_id)            # function type shows the type of variable patient_id
```
### Using variables
```python
weight_lb = 2.2 * weight_kg             # make calculations
weight_lb                               # display new value
patient_id = 'inflam_' + patient_id     # add a prefix to string -> + concatenates
patient_id                              # display new value
```
### Built-in functions
```python
print(weight_lb)                # display info in screen
print(patient_id)               # follow function name by parenthesis
print(patient_id, 'weight in kilograms:', weight_kg) # multiple things at once
```
### Getting help
```python
help(print)         # shows docstring with parameters and usage
```

## 10:00 - 💪  Challenge - 10' - CATA
- Open `exercises_day_one` notebook from jupyter home
    - 1 ❓ Check your understanding
    - 2 ❓ Sorting out references
    - [OPTIONAL]❓ Arithmic with different types

## 10:10 - Break - 15'


## 10:25 - Lists - 20' - HALFORD
`lists` ordered collection of elements
```python
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
```python
sample_ages = [10, 12.5, 'Unknown']
```

`lists` can be modified
```python
odds.append(11)             # add element at the end
print('odds after adding a value:', odds)

odds.pop(0)   # pop removes an element in a specific index
print('odds after removing the first element:', odds)

odds.reserve()
print('odds after reversing:', odds)
```
Careful when modifying `lists` in-place. Variables pointing to the same list stay `connected`. Both variables are pointing to the same list.
```python
odds = [3, 5, 7]
primes = odds
primes.append(2)
print('primes:', primes)
print('odds:', odds)
```
For a simple copy, better to use the `list()` command
```python
odds = [3, 5, 7]
primes = list(odds)
primes.append(2)
print('primes:', primes)
print('odds:', odds)
```
A note about slicing: similarly to a numpy array, `lists` and `strings` can be sliced
```python
name = 'dolores santos'
name[0:7]                                   # how it works in a string

chromo = ['X', 'Y', '2', '3', '4']          # how it woks in a list
chromo[2:5]

chromo[-1]

```
## 10:45 - 💪  Challenge - 15' - HALFORD
    - 3 ❓ Slicing from the end
    - 4 ❓ Non-continuous slices


## 11:00 - More Lists - 15' - HALFORD
🎦 Use [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20programming%20with%20Python.pptx?d=w0d581778c4b0479ab36e1e1706535b88&csf=1&web=1&e=gdimt4) to explain `nested lists`

```python
veg = [['lettuce', 'lettuce', 'peppers', 'zucchini'],
     ['lettuce', 'lettuce', 'peppers', 'zucchini'],
     ['lettuce', 'cilantro', 'peppers', 'zucchini']] # a list that contains other lists
print(veg[2]) # row at the bottom of the shelf 
print(veg[0]) # row at the top of the shelf
print(veg[0][0]) # basket top left corner
```

Omitting first/last index
```python
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

## 11:15 - 💪  Challenge - 10' - HALFORD
- 5 ❓ Overloading
- [OPTIONAL] ❓ Split even and odd

## 11:25 - Break - 15'

## 11:40 - Loops - 20' - CATA
why `loops` -> repeated actions on long lists
```python
odds = [1, 3, 5, 7]         # list with ordered elements
print(odds[0])              # access via index
print(odds[1])
print(odds[2])
print(odds[3])              # if list is long this becomes very tedious
```
Enter `loops` -> a structure that allows to repeat an operation once for each element in a sequence
```python
for number in odds:        # The : marks the start of the loop
    print(number)          # indention defines the block of the code that will be repeated
odds = [1,3,5,7,9,11,13,15,17,19,21]    # a longer list
for number in odds:         # runs the loop and it works again
    print(number)
```
Loop variable can have any name. Recommended to use descriptive names
```python
for banana in odds:
    print(banana)
for odd in odds:        # another standard -> singular of the list name
    print(odd)
```
Another example.
```python
length = 0
names = ['Curie', 'Darwin', 'Turing']
for value in names:
    length = length + 1            
print('There are', length, 'names in the list.')
```
Analyse step by step. Notice when the variables are modified.
- run 1 -> length = 0, value = 'Curie', +1, length = 1
- run 2 -> length = 1, value = 'Darwin', +1, length = 2
- run 3 -> length = 2, value = 'Turing', +1 , length = 3

Notice the variable still exists when the loop is over

```python
name = 'Rosalind'
print(name)
for name in ['Curie', 'Darwin', 'Turing']:
    print(name)
print('after the loop, name is', name)
```
`len` is a built-in function
```python
print(len([1,2,3,4,5]))
print(len(names))
print(len(odds))
```

## 12:00 - 💪  Challenge - 30' - CATA

- 6 ❓ From 1 to N
- 7 ❓ Understanding the loops
- 8 ❓ Summing a list
- 9 ❓ Computing the Value of a polynomial
- [OPTIONAL] ❓ Factorial calculation

## 12:30 - Break - 60'

## 13:30 - Loading data - 10' - HALFORD
- Importing a library is like getting a piece of lab equipment
- Only import what you need so it doesn't get messy
- Use shortcut to `import numpy`

```python
import numpy as np          # numerical python. Good for matrices operations
np.loadtxt(fname='data/inflammation-01.csv') # without delimiter to explain delimiter

data = np.loadtxt(fname='data/inflammation-01.csv', delimiter=','). # explain function call, . notation and parameters
type(data)              # n-dimensional array
data.shape              # array shape
```
- 📉 Draw on board 60 rows -> patients and 40 columns -> days
- 📉 Explain on the board the Python indexing [row, columns]
    - Explain zero based indexing -> offset from the first value in the array
- 🎦 use picture in [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20programming%20with%20Python.pptx?d=w0d581778c4b0479ab36e1e1706535b88&csf=1&web=1&e=gdimt4) 

```python
print('first value in data:', data[0, 0]) # single number from array we use an index
print('middle value in data:', data[29, 19]) #row 30, column 20.

```

## 13:40 - Slicing data - 10' - HALFORD
Reiterate the use of square brackets
```python
print(data[0:4, 0:10])          # select a section using :
```
`0:4`-> "start at index 0 and go up to, not including, index 4"
```python
print(data[5:10, 0:10])         # start the slice where ever you want
print(data[:3, 36:])            # no lower bound starts at zero, no upper bound goes to end 
```

## 13:50 - 💪  Challenge - 10'- HALFORD
- 10 ❓ Slicing strings
- [OPTIONAL] ❓ Counting vowels

## 14:00 - Analyzing data - 10' - HALFORD
Default functions from `np`
```python
print(np.mean(data))         # mean is a function. data is the argument
maxval = np.max(data)
minval = np.min(data)
stdval = np.std(data)        

print('maximum value', maxval)
print('minimum value', minval)
print('standard deviation',stdval)
```
Demo `numpy`. **TAB** to visualize the functions available from the library

## 14:10 - Numpy axes - 10' - HALFORD
```python
patient_0 = data[0, :] # 0 on the first axis (rows), everything on the second (columns)
print('maximum inflammation for patient 0:', np.max(patient_0))
print('maximum inflammation for patient 2:', np.max(data[2, :])) # no need to store in variable

```
🎦  Explain np axes with [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20programming%20with%20Python.pptx?d=w0d581778c4b0479ab36e1e1706535b88&csf=1&web=1&e=gdimt4) 

- axis 0 -> walks along rows
- axis 1 -> walks along columns

```python
print(np.max(data, axis=1)) # the same for all patients at once
print(np.max(data, axis=1).shape) # 60 patients
print(np.max(data, axis=0)) # the same for all days at once
print(np.max(data, axis=0).shape) # 40 days
print(np.mean(data, axis=1)) # mean inflammation for all patients at once
```

## 14:20 - 💪  Challenge - 10' - HALFORD
- 11 ❓ Change in inflammation

## 14:30 - Break - 15'

## 14:45 - Visualizing Tabular Data - 15' - CATA
Use shortcut to `import matplotlib`
```python
import matplotlib.pyplot as plt # another handy library using short-cut
image = plt.imshow(data) # heatmap: low values are blue, high values are yellow     
```
Quickly observe tendency of inflammation flare-ups around day 20 🔥

Patients take medication and inflammation drops to zero in about 3 weeks 👍

```python
plt.plot(np.mean(data, axis=0))       # avg inflammation per day. Reasonable rise and fall plot
plt.plot(np.max(data, axis=0))         # linear seems unlikely
plt.plot(np.min(data, axis=0))         # step function seems unlikely
```
Max and min look suspicious. This requires further investigation 😶

## 15:00 - Grouping plots - 15' - CATA
- `figure` creates a space (like a blank canvas) where to place our plots
- `add_subplot` takes 3 parameters: rows, columns, which subplot
- `set_ylabel` to name the axis
- `savefig` stores plot in a file (can be png, svg, pdf, jpeg)
```python
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

## 15:15 - 💪  Challenge - 20' - CATA
- 12 ❓ Plot scaling
- 13 ❓ Drawing straight lines
- 14 ❓ Make your own plot
- 15 ❓ Moving plots around
- [OPTIONAL] ❓ Plotting error bars

## 15:35 - Break - 15'

## 15:50 - Analysing multiple files - 15' - HALFORD
`glob` a library to get a list of all files in a directory

```python
print(glob.glob('inflammation*.csv')) # wildcard * matches zero or more characters
# arbitrary order
```
```python
import glob             
import numpy as numpy
import matplotlib.pyplot as plt

filenames = sorted(glob.glob('data/inflammation*.csv'))  
for filename in filenames[0:3]:
    print(filename)        

    data = numpy.loadtxt(fname=filename, delimiter=',')

    fig = plt.figure(figsize=(10.0, 3.0)) # one figure per file

    axes1 = fig.add_subplot(1, 3, 1)                    # 3 plots per file
    axes2 = fig.add_subplot(1, 3, 2)
    axes3 = fig.add_subplot(1, 3, 3)

    axes1.set_ylabel('average')
    axes1.plot(numpy.mean(data, axis=0)) # along rows = patients -> values per day

    axes2.set_ylabel('max')
    axes2.plot(numpy.amax(data, axis=0)) # along rows = patients -> values per day

    axes3.set_ylabel('min')
    axes3.plot(numpy.amin(data, axis=0)) # along rows = patients -> values per day

    plt.show()            # so that it renders after printing the filename
```
- File 1 and 2 -> similar patterns
- File 3 -> suspicious minima

```python
data = np.loadtxt(fname='data/inflammation-03.csv',delimiter=',')
plt.imshow(data)
```
Notice zero values spread across patients and days. Potential problem with data collection❗
## 16:10 - 💪  Challenge - 20' - HALFORD

- 16 ❓ Plotting Differences
- 17 ❓ Generate Composite Statistics

## 16:30 - Forgive the imaginary Dr. Maverick - 5' - HALFORD
🎦 Use [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20programming%20with%20Python.pptx?d=w0d581778c4b0479ab36e1e1706535b88&csf=1&web=1&e=gdimt4) 


## 16:35 - Key points - 10' - HALFORD
```python
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

li = [another_list, yet_another_list]

li[1] = 5 # lists are mutable -> update value
s[0] ='k' # strings are immutable -> items inside cannot be changed -> only fully replaced

for variable in sequence:
    print(variable)         # notice indentation

len(li)                  # length of something that contains other values (eg. list)

import numpy as np
data = np.loadtxt(fname='data/inflammation-01.csv', delimiter=',')
np.mean(data, axis=0)

import matplotlib.pyplot as plt
plt.imshow(data)
plt.plot(np.mean(data, axis=0))
plt.show()

import glob
glob.glob('data/inflammation*.csv')
```


# 🌞 DAY 2 🌞
## 9:00 - Land - 10' - HALFORD
☕ Coffee/tea 🫖

## 9:10 - Housekeeping - 15' - HALFORD
- ✅ Roll call + 🤝 Code of Conduct
- 🖥 Restart Jupyter notebook
    - Restart Jupyter notebook
    - Make a new notebook with Python 3 kernel
    - Rename to `two` and save

## 9:20 - Recap from day one - 10' - HALFORD

```python
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

li = [another_list, yet_another_list]

li[1] = 5 # lists are mutable -> update value
s[0] ='k' # strings are immutable -> items inside cannot be changed -> only fully replaced

for variable in sequence:
    print(variable)         # notice indentation

len(li)                  # length of something that contains other values (eg. list)

import numpy as np
data = np.loadtxt(fname='data/inflammation-01.csv', delimiter=',')
np.mean(data, axis=0)

import matplotlib.pyplot as plt
plt.imshow(data)
plt.plot(np.mean(data, axis=0))
plt.show()

import glob
glob.glob('data/inflammation*.csv')
```

## 9:30 - Making choices - 20' - HALFORD
Make a choice with `if`
```python
num = 37
if num > 100:               # if statement is true -> executes code inside if body
    print('greater')    
else:                       # if statement is false -> execute code inside else body  
    print('not greater')
print('done')
```
`else` is optional
```python
num = 53
print('before conditional...')
if num > 100:                           # if statement false
    print(num, 'is greater than 100')
print('...after conditional')           # python skips if body and continues on this line
```
chain multiple tests with `elif`
```python
num = -3

if num > 0:
    print(num, 'is positive')
elif num == 0:                      # test for equality uses double equal (==) vs single equal (=) means assign
    print(num, 'is zero')
else:
    print(num, 'is negative')
```

comparing in Python: explain comparison operators
```python
5 == 5
5!=3
5 > 4
5 >= 5
5 < 7
5 <= 5

```
Combine test using `and` and `or`
```python
if (1 > 0) and (-1 >= 0):
    print('both parts are true')            
else:
    print('at least one part is false')
if (1 < 0) or (1 >= 0):
    print('at least one test is true')
```

`True` AND `False` are special words in python called `booleans`
```python
1<0
-1<0
```
Let's use this concepts to check our data
- if max inflammation day 0 and middle (day 20) are the same as the day number

```python
import numpy as np          # if needed import numpy again!
data = np.loadtxt(fname='data/inflammation-01.csv', delimiter=',')

max_inflammation_0 = np.max(data, axis=0)[0]
max_inflammation_20 = np.max(data, axis=0)[20]

if max_inflammation_0 == 0 and max_inflammation_20 == 20: # max equal to day number
    print('Suspicious looking maxima!')
elif np.sum(np.min(data, axis=0)) == 0:                   # min is zero (no inflammation)
    print('Minima add up to zero!')
else:
    print('Seems OK!')                                    # all good
```
```python
data = np.loadtxt(fname='data/inflammation-03.csv', delimiter=',')

max_inflammation_0 = np.max(data, axis=0)[0]
max_inflammation_20 = np.max(data, axis=0)[20]

if max_inflammation_0 == 0 and max_inflammation_20 == 20: # max equal to day number
    print('Suspicious looking maxima!')
elif np.sum(np.min(data, axis=0)) == 0:                   # min is zero (no inflammation)
    print('Minima add up to zero!')
else:
    print('Seems OK!')                                    # all good
```

## 9:50 - 💪  Challenge - 15' - HALFORD
- Open `exercises_day_two` notebook from jupyter home
    - 1 ❓ What Is Truth?
    - 2 ❓ Close Enough
    - 3 ❓ Sorting a List Into Buckets
    - [OPTIONAL] ❓ In-Place Operators

## 10:05 - Break - 15'
## 10:20 - Creating functions - 20' - CATA
use python for calculations using variables
```python
fahrenheit_val = 99
celsius_val = ((fahrenheit_val - 32) * (5/9)) # convert temperature F to C

fahrenheit_val2 = 43                        # copy the line and rename the variables
celsius_val2 = ((fahrenheit_val2 - 32) * (5/9))

```
if repeat for many variables -> long, clumsy and ugly 😕

short way to reuse code -> `function`
```python
def explicit_fahr_to_celsius(temp):
    # Assign the converted value to a variable
    converted = ((temp - 32) * (5/9))
    # Return the value of the new variable
    return converted
    
def fahr_to_celsius(temp):
    # Return converted value more efficiently using the return
    # function without creating a new variable. This code does
    # the same thing as the previous function but it is more explicit
    # in explaining how the return command works.
    return ((temp - 32) * (5/9))
```
- `def` function definition
- `fahr_to_celsius` function name
- `(temp)` parenthesized list of parameter
- `body` defined by indention (same as `loops`)
- `return` ends body followed by return value

```python
fahr_to_celsius(32)     # 32 assigned to `temp`
                        # returns the converted valued
print('freezing point of water:', fahr_to_celsius(32), 'C')
print('boiling point of water:', fahr_to_celsius(212), 'C')
```
Another function to convert C to K
```python
def celsius_to_kelvin(temp_c):
    return temp_c + 273.15

print('freezing point of water in Kelvin:', celsius_to_kelvin(0.))
```
Call a function inside a function -> composing functions
```python
# compose functions
def fahr_to_kelvin(temp_f):
    temp_c = fahr_to_celsius(temp_f)
    temp_k = celsius_to_kelvin(temp_c)
    return temp_k

print('boiling point of water in Kelvin:', fahr_to_kelvin(212.0))

```
This is how large programs are built.

The variables inside a function are called `local variables`

```python
print('Again, temperature in Kelvin was:', temp_k) # temp_k does not exist after execution
temp_kelvin = fahr_to_kelvin(212.0)     # store return value of function in variable
print('temperature in Kelvin was:', temp_kelvin)

def print_temperatures():
    print('temperature in Fahrenheit was:', temp_fahr)
    print('temperature in Kelvin was:', temp_kelvin)

temp_fahr = 212.0                       # variable outside function is global
temp_kelvin = fahr_to_kelvin(temp_fahr)

print_temperatures()
``` 
**NOTE** `print` and `return` don't have the same behavior.
- `print` makes data visible on the screen for us humans to read
- `return` makes data visible to the program
```python
def add(a, b):
    print(a + b)      # prints on the screen

A = add(7, 3)
print(A)            # return None

def add(a, b):
    return a + b      # returns 
A = add(7, 3)
print(A)            # returns a + b

```

let's practice making functions with the code we've written so far:

```python
def visualize(filename): #use a descriptive name for function

    data = np.loadtxt(fname=filename, delimiter=',')

    fig = plt.figure(figsize=(10.0, 3.0))

    axes1 = fig.add_subplot(1, 3, 1)
    axes2 = fig.add_subplot(1, 3, 2)
    axes3 = fig.add_subplot(1, 3, 3)

    axes1.set_ylabel('average')
    axes1.plot(np.mean(data, axis=0))

    axes2.set_ylabel('max')
    axes2.plot(np.amax(data, axis=0))

    axes3.set_ylabel('min')
    axes3.plot(np.amin(data, axis=0))

    plt.show()

def detect_problems(filename): 

    data = np.loadtxt(fname=filename, delimiter=',')

    if np.amax(data, axis=0)[0] == 0 and np.amax(data, axis=0)[20] == 20:
        print('Suspicious looking maxima!')
    elif np.sum(np.amin(data, axis=0)) == 0:
        print('Minima add up to zero!')
    else:
        print('Seems OK!')
    # no need for return
```
reusing functions makes code easy to read 😀
```python
filenames = sorted(glob.glob('data/inflammation*.csv'))

for filename in filenames[:3]:
    print(filename)
    visualize(filename)
    detect_problems(filename)
```

## 10:40 - 💪  Challenge - 10' - CATA
- 4 ❓ Combining Strings
- 5 ❓ Selecting Characters From Strings

## 10:50 - Creating functions - cont - 20' - CATA
How do I know the function works as intended? We use `tests`. Example:

```python
def offset_mean(data, target_mean_value):
    # offsets a dataset so that it’s mean value shifts to a user-defined value
    return (data - np.mean(data)) + target_mean_value


# synthetic testing data
z = np.zeros((2, 2)) # create matrix of zeros
print(offset_mean(z, 3)) # offset its values to have a mean value of 3

data = np.loadtxt(fname='data/inflammation-01.csv', delimiter=',')
print(offset_mean(data, 0)) # test on real data

```
hard to tell correctness! So, let's write more test to check.
```python
print('original min, mean, and max are:', np.min(data), np.mean(data), np.max(data))
offset_data = offset_mean(data, 0)
# shifted mean to ~zero. Lower bound to -6.1
print('min, mean, and max of offset data are:',
      np.min(offset_data),
      np.mean(offset_data),
      np.max(offset_data))
# same std
print('std dev before and after:', np.std(data), np.std(offset_data))
```
Looks good!
Now let's document our function.

Comments are often used to document code. Better to use a `docstring`. String that goes beneath the function `def`

```python
def offset_mean(data, target_mean_value):
    """Return a new array containing the original data
    with its mean offset to match the desired value."""
    return (data - np.mean(data)) + target_mean_value
help(offset_mean)   # docstrings are used by help function

```
the triple quotes `"""` allows to break the line and add examples.
```python
def offset_mean(data, target_mean_value):
    """Return a new array containing the original data
       with its mean offset to match the desired value.

    Examples
    --------
    >>> offset_mean([1, 2, 3], 0)
    array([-1.,  0.,  1.])
    """
    return (data - numpy.mean(data)) + target_mean_value

help(offset_mean)

```
Another important aspect of functions are `parameters`.
They can be given with and without name of variable.
```python
np.loadtxt('inflammation-01.csv', delimiter=',') # works without variable name
np.loadtxt('inflammation-01.csv', ',') # does not work. We'll see why a little bit later
```
To understand the error above, let's first talk about `default` values. We can give default values using `name_variable = value` in the definition. That variable gets a value even if user does not define it.
```python
def offset_mean(data, target_mean_value=0.0):
    """Return a new array containing the original data
       with its mean offset to match the desired value, (0 by default).

    Examples
    --------
    >>> offset_mean([1, 2, 3])
    array([-1.,  0.,  1.])
    """
    return (data - numpy.mean(data)) + target_mean_value
test_data = np.zeros((2, 2))
print(offset_mean(test_data, 3))
more_data = 5 + numpy.zeros((2, 2))
print('data before mean offset:')
print(more_data)
print('offset data:')
print(offset_mean(more_data))   # just one parameter. second parameter uses default
```
this is handy to set default behaviour of a function with options for user to change.
```python
def display(a=1, b=2, c=3):
    print('a:', a, 'b:', b, 'c:', c)

print('no parameters:')
display()
print('one parameter:')
display(55)
print('two parameters:')
display(55, 66)

print('only setting the value of c')
display(c=77)

```
now let's understand the `loadtxt` error from before
```python
help(np.loadtxt)
np.loadtxt('data/inflammation-01.csv', ','). # fname is understood but ',' is not valid for dtype
```
In general, using `parameter names` when calling a function is part of making your code readable. It also reduces the chance of bugs (i.e. by assigning values to the intended variable)

**OPTIONAL:**
Here's another example of making code readable:
```python
def s(p):
    a = 0
    for v in p:
        a += v
    m = a / len(p)
    d = 0
    for v in p:
        d += (v - m) * (v - m)
    return np.sqrt(d / (len(p) - 1))

# function computationally equivalent
def std_dev(sample):
    # using intuitive names
    sample_sum = 0
    for value in sample:
        sample_sum += value
     # adding blank lines
    sample_mean = sample_sum / len(sample)
   
    sum_squared_devs = 0
    for value in sample:
        sum_squared_devs += (value - sample_mean) * (value - sample_mean)

    return np.sqrt(sum_squared_devs / (len(sample) - 1))

```

## 11:10 - 💪  Challenge - 10' - CATA
- 6 ❓ Rescaling an Array
- 7 ❓ Defining Defaults
- 8 ❓ Testing and Documenting Your Function
- [OPTIONAL] ❓ Mixing Default and Non-Default 

## 11:20 - Break - 15' - CATA

## 11:35 - Errors and exceptions - 10' - HALFORD
Errors are inevitable. We can learn to understand them so they become easier to fix.

A `traceback` is how python displays errors.
```python
def favorite_ice_cream():
    ice_creams = [
        'chocolate',
        'vanilla',
        'strawberry'
    ]
    print(ice_creams[3]) # an intentional error

favorite_ice_cream()
```
This error has 2 levels (number of `---->`), which point to the line where error happened

Last level is where the error actually occurred -> `print(ice_creams[3])`

Python tells us the type of error: `IndexError: list index out of range`.

## 11:45 - 💪  Challenge - 10' - HALFORD
- 9 ❓ Reading Error Messages

## 11:55 - Errors and exceptions - cont - 15' - HALFORD
Most common types of errors.

`Syntax Errors` are like a typing error. Missing colon, indentation, parenthesis.
```python
def some_function()             # missing:
    msg = 'hello, world!'
    print(msg)
     return msg
```
```python
def some_function():             
    msg = 'hello, world!'
    print(msg)
     return msg             # indentation
```
```python
# all fixed!
def some_function():             
    msg = 'hello, world!'
    print(msg)
    return msg             
```

`Name Errors` mean the variable does not exist
```python
print(a)            # undefined variable

print(hello)        # forgot string quotes

for number in range(10):
    count = count + number      # does not exist YET
print('The count is:', count)

Count = 0                       # variables are case sensitive
for number in range(10):
    count = count + number      
print('The count is:', count)
```

`Index Errors` refer to containers (e.g. lists, strings)
```python
letters = ['a', 'b', 'c']
print('Letter #1 is', letters[0])
print('Letter #2 is', letters[1])
print('Letter #3 is', letters[2])
print('Letter #4 is', letters[3])
```

`File Error` refer to reading a file.
```python
file_handle = open('myfile.txt', 'r')       # file does not exist
```
often caused by incorrect path or that filename has a typo.

## 12:10 - 💪  Challenge - 15' - HALFORD
- 10 ❓ Identifying Syntax Errors
- 11 ❓ Identifying Variable Name Errors
- 12 ❓ Identifying Index Errors

## 12:25 - Break - 60'

## 13:25 - Defensive Programming - 15' - CATA
How can I make my programs `correct`?
Define what correct means and write tests that check this correctness.

Writing tests take time yes! It's like measuring multiple times before cutting a piece of wood.

Assume mistakes will happen and guard against them. This is called `defensive programming`. We can use `assertions` -> if `True` it continues, if `False` it stops

```python
numbers = [1, 2, 3, -0.1, 4]
total = 0.0
for num in numbers:
    assert num > 0.0, 'Data should only contain positive values'
    total += num
print('total is:', total)
```
Assertions can be:
- precondition: true at the start of function
- postcondition: true at the end of function

```python
# example simplified from normalize_rectangle()
# explain tuple: similar to list but immutable
def shift_rectangle(rectangle):   
    """Shift a rectangle to origin.
    Input should be of the format (x0, y0, x1, y1).
    (x0, y0) and (x1, y1) define the lower left and upper right corners
    of the rectangle, respectively."""
    assert len(rectangle) == 4, 'Rectangles must contain 4 coordinates'
    x0, y0, x1, y1 = rectangle
    assert x0 < x1, 'Invalid X coordinates'
    assert y0 < y1, 'Invalid Y coordinates'

    upper_x = x1 - x0
    upper_y = y0 - y1

    assert 0 < upper_x <= x1, 'Calculated upper X coordinate invalid'
    assert 0 < upper_y <= y1, 'Calculated upper Y coordinate invalid'

    return (0, 0, upper_x, upper_y)
```
```python
print(shift_rectangle( (1, 2, 3) )) # missing the fourth coordinate
print(shift_rectangle( (3, 2, 1, 4) )) # X axis inverted
print(shift_rectangle( (1, 4, 3, 2) )) # Y axis inverted
print(shift_rectangle( (1, 2, 3, 4) )) # line 14 -> y1 - y0
```
```python
# fix bug in line 12
upper_y = y1 - y0       # show how to see line number in jupyter
```

- fail early, fail often. 
- turn bugs into assertions

## 13:40 - 💪  Challenge - 10' - CATA
- 13 ❓ Pre- and Post-Conditions

## 13:50 - Defensive programming - cont - 20' - CATA
With `asserts` we check specific points of the code. Next step is to check the overall behaviour of the code.

What we did so far was to write the function first and test it after. 

Another way to do it is start with a broken test before implementing the function. This is called `test driven development (TDD)` and it has some advantages:
- reduces confirmation bias -> subconsciously write test to prove the code works rather than to find errors
- helps figure out what the function should do, what the inputs and outputs should be


🎦 use [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20programming%20with%20Python.pptx?d=w0d581778c4b0479ab36e1e1706535b88&csf=1&web=1&e=gdimt4) to introduce our next task -> `range_overlap`


```python
def range_overlap(ranges):      # empty function
    pass
assert range_overlap([ (0, 1) ]) == (0, 1)
assert range_overlap([ (2, 3), (2, 4) ]) == (2, 3)
assert range_overlap([ (0, 1), (0, 2), (-1, 1) ]) == (0, 1)
```
We expected the failure as the functions is empty.

By writing the asserts we decided what our input is: a list of pairs.

what about unexpected inputs? -> no overlap at all
```python
assert range_overlap([ (0, 1), (5, 6) ]) == ???
assert range_overlap([ (0, 1), (1, 2) ]) == ???
```
We have to make decisions to define the expected behavior of our code. 
- overlap should be non-zero
- no overlap returns `None`
These scenarios are called `edge cases`
```python
assert range_overlap([ (0, 1), (5, 6) ]) == None        # it passes -> it returns None
assert range_overlap([ (0, 1), (1, 2) ]) == None
```
```python
def range_overlap(ranges):
    """Return common overlap among a set of [left, right] ranges."""
    max_left = 0
    min_right = 1
    for (left, right) in ranges:
        max_left = max(max_left, left)
        min_right = min(min_right, right)
    return (max_left, min_right)
```
Let's run the tests
```python
def test_range_overlap():
    assert range_overlap([ (0, 1), (5, 6) ]) == None
    assert range_overlap([ (0, 1), (1, 2) ]) == None
    assert range_overlap([ (0, 1) ]) == (0, 1)
    assert range_overlap([ (2, 3), (2, 4) ]) == (2, 3)
    assert range_overlap([ (0, 1), (0, 2), (-1, 1) ]) == (0, 1)
    assert range_overlap([ ]) == None
```
We are initialising the  `max_left = 0` and `min_right = 1`. This violates an important rule: `always initialize from data`.

Our function is not working as expected. So for now we will leave it behind and practice assertions in a different way.

## 14:10 - 💪  Challenge - 10' - CATA
- 14 ❓ Testing Assertions

## 14:20 - Break - 15'

## 14:35 - Debugging - 15' - HALFORD
🎦 use [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20programming%20with%20Python.pptx?d=w0d581778c4b0479ab36e1e1706535b88&csf=1&web=1&e=gdimt4) 


## 14:50 💪  Challenge - 40' - HALFORD
- 15 ❓ Minimum Failure
- 16 ❓ Not Supposed to be the Same
- 17 ❓ Common code errors

## 15:30 - Break - 15'

## 15:45 - Putting it all together - 40' - CATA
- 18 ❓ Putting it all together

## 16:25 - Key points - 10' - CATA
```
# making choices
if, elif, else  
use indentation to mark the body of the condition
`==`  to test equality
zero, empty strong and empty lists are considered False
`True` and `False` represent truth values

# functions
`def function_name(parameter):`
Body should be indented
Call a function using `function_name(value)
variables inside disappear at end of the function
variables outside the functions are global variables
we can specify default values for parameters using `name=value`

# errors
errors can be intimidating. They usually provide useful information to hep us fix it
`SyntaxError` -> typos
`IndentationError` -> indentations
`NameError` -> when variable does not exist
`IndexError` -> trying to access items in a container that don't exist
`FileNotFoundError` -> trying to read files that do not exists

# defensive programming
Put assertions in programs to check their state as they run, and to help readers understand how those programs are supposed to work.

preconditions to check that the inputs to a function are safe to use.

postconditions to check that the output from a function is safe to use.

Write tests before writing code in order to help determine exactly what that code is supposed to do.

# debugging
Is a very important skill

```

## 16:35 - Feedback - 10' - CATA
* Ask participants to fill in the feedback survey
