# Classes and Objects in Python: Calculate the Area of a Circle

## 🎯 Aim
To write a Python program that calculates the **area of a circle** based on the radius provided by the user. This program uses a class named `cse` and a method `mech` to perform the calculation.

## 🧠 Algorithm
1. **Get user input**: Take the radius of the circle as input from the user.
2. **Define the class**: Create a class named `cse`.
3. **Define the method**: Inside the class, define the method `mech` to calculate the area of the circle using the formula:  
   Area = pi *r^2 
4. **Execute the program**: Create an object of the class and call the method with the radius value.

## 🧾 Program
```
import math

# 2. Define the class
class cse:
    # 3. Define the method to calculate the area
    def mech(self, radius):
        area = math.pi * (radius ** 2)
        return area

# 1. Get user input
try:
    user_radius = float(input("Enter the radius of the circle: "))

    # 4. Execute the program: Create an object and call the method
    circle_object = cse()
    result = circle_object.mech(user_radius)

    print(f"The area of the circle with radius {user_radius} is: {result:.2f}")

except ValueError:
    print("Please enter a valid numerical value for the radius.")
```

## Output
```
Enter the radius of the circle: 5
The area of the circle with radius 5.0 is: 78.54
```

## Result
Using class and objects the program is functioned.


## Dictionary Operations in Python: Merging Two Dictionaries

## 🎯 Aim
To write a Python program that merges **two dictionaries** and combines their key-value pairs.

## 🧠 Algorithm
1. Define two dictionaries `dict1` and `dict2` with some key-value pairs.
2. Define a function `merge()` that merges the two dictionaries using the `**` unpacking operator.
   - The merged result will combine keys from both dictionaries. If a key exists in both, the value from `dict2` will overwrite that from `dict1`.
3. Call the `merge()` function and print the merged dictionary.

## 🧾 Program
```
# 1. Define two dictionaries
dict1 = {'a': 1, 'b': 2, 'c': 3}
dict2 = {'b': 20, 'd': 40}

# 2. Define the function to merge using the ** operator
def merge(d1, d2):
    # The second dictionary (d2) will overwrite shared keys in the first (d1)
    merged_dict = {**d1, **d2}
    return merged_dict

# 3. Call the function and print the result
result = merge(dict1, dict2)
print("Merged Dictionary:", result)
```

## Output
```
Merged Dictionary: {'a': 1, 'b': 20, 'c': 3, 'd': 40}
```

## Result
Two dictionaries are combined.


# 🔤 Dictionary-Python Program to Sort a Dictionary by Keys and Values

This Python program demonstrates how to sort a dictionary:
- Alphabetically by keys
- Alphabetically by values

---

## 🎯 Aim

To write a Python program that sorts a dictionary's:
- Keys in alphabetical order
- Values in alphabetical order

---

## 🧠 Algorithm

1. **Start the program.**
2. **Define** a dictionary with key-value pairs.
3. **Sort by Keys**:
   - Use `sorted(dictionary.items())`
   - Convert the result to a dictionary using `dict()`
4. **Sort by Values**:
   - Use `sorted(dictionary.items(), key=lambda item: item[1])`
   - Convert the result to a dictionary using `dict()`
5. **Display** the original and sorted dictionaries.
6. **End the program.**

---

## 🧪Program
```
# 1. Start the program
# 2. Define a dictionary with key-value pairs
data = {
    "Mango": 50,
    "Apple": 20,
    "Banana": 10,
    "Cherry": 30
}

# 3. Sort by Keys
# sorted() returns a list of tuples, so we wrap it in dict()
sorted_by_keys = dict(sorted(data.items()))

# 4. Sort by Values
# item[1] refers to the value in the (key, value) tuple
sorted_by_values = dict(sorted(data.items(), key=lambda item: item[1]))

# 5. Display the dictionaries
print("Original Dictionary:", data)
print("-" * 30)
print("Sorted by Keys (A-Z):", sorted_by_keys)
print("Sorted by Values (Ascending):", sorted_by_values)


```

## Sample Output
```
Original Dictionary: {'Mango': 50, 'Apple': 20, 'Banana': 10, 'Cherry': 30}
------------------------------
Sorted by Keys (A-Z): {'Apple': 20, 'Banana': 10, 'Cherry': 30, 'Mango': 50}
Sorted by Values (Ascending): {'Banana': 10, 'Apple': 20, 'Cherry': 30, 'Mango': 50}
```

## Result
Sorting of dictionary is done.


# Exception Handling in Python: Avoiding Index Errors

## 🎯 Aim
To write a Python program that handles an **IndexError** when trying to access an element beyond the available range of a list.

## 🧠 Algorithm
1. Define a list `list1` with some integer elements.
2. Use a **try-except** block:
   - In the `try` block, attempt to access an index that is out of range (e.g., `list1[5]`).
   - In the `except` block, catch the error and print a custom message `"You're out of list range"`.
3. Print the result based on whether the index access succeeds or fails.

## 🧾 Program
```
# 1. Define a list with some integer elements
list1 = [10, 20, 30]

# 2. Use a try-except block
try:
    # Attempting to access index 5 (which does not exist in a 3-item list)
    print("Attempting to access index 5...")
    result = list1[5]
    
    # 3. This only prints if the index access succeeds
    print("Access successful! The value is:", result)

except IndexError:
    # This catches the specific error and prints your custom message
    print("You're out of list range")
```

## Output
```
Since list1 only has three elements (indices 0, 1, and 2), the program will jump straight to the except block:

Attempting to access index 5...
You're out of list range
```

## Result
Exception handing is done through python code.

# File Handling in Python: Count Lines Not Starting with 'T'

## 🎯 Aim
To write a Python program that counts the number of lines in a text file `story.txt` that do **not** start with the alphabet `'T'`.

## 🧠 Algorithm
1. Open the file `story.txt` in **read mode**.
2. Initialize a counter `count` to zero.
3. Iterate through each line of the file:
   - Check if the first character of the line is **not** `'T'`.
   - If the line does not start with `'T'`, increment the `count` by 1.
4. After processing all lines, print the `count` value, which represents the number of lines that do not start with `'T'`.

## 🧾 Program
```
# 1. Open the file story.txt in read mode
try:
    with open("story.txt", "r") as file:
        # 2. Initialize a counter to zero
        count = 0
        
        # 3. Iterate through each line of the file
        for line in file:
            # Strip whitespace to handle empty lines or leading spaces
            clean_line = line.strip()
            
            # Check if the line is not empty and the first character is NOT 'T'
            if clean_line and not clean_line.startswith('T'):
                # Increment the count
                count += 1
                
    # 4. Print the final count
    print(f"Number of lines that do not start with 'T': {count}")

except FileNotFoundError:
    print("Error: The file 'story.txt' was not found. Please create it first.")
```

## Output
```
If your story.txt contains the following:

The quick brown fox.
A small dog barked.
There is a house.
Birds are flying.

The Sample Output would be:


Number of lines that do not start with 'T': 2
```

## Result
File handling is explained clearly.
