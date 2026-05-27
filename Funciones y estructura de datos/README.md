# Creation of Functions, Data Structures and Loops

## Description

This project contains the solution to various real-world problems using data structures and control flow in Python. The goal is to consolidate Python syntax fundamentals and create reusable functions.

## Project Structure

```
Functions and Data Structures/
├── functions_structures_data_loops.ipynb   # Main notebook
├── historic_matches.txt                    # Football match data
├── tu_me_quieres_blanca.txt               # Text for word counter
└── README.md
```

## Exercise Levels

### Level 1

#### 1. Body Mass Index (BMI) Calculator
Function that calculates BMI from weight (kg) and height (m), classifying the result into categories:
- Underweight
- Normal weight
- Overweight
- Obesity

**Validation:** Check that values are positive and reasonable.

#### 2. Temperature Converter
Function that converts temperatures between multiple units (Celsius, Fahrenheit, Kelvin, etc.).

**Requirements:**
- Minimum 2 conversions returned
- Results stored in variables (not just prints)
- Input data validation

**Extra:** Implement conversions in a single data structure (dictionary or list).

#### 3. Word Counter
Function that analyzes text and shows the frequency of each word.

**Extra:** Calculate the average length of words.

#### 4. Reverse Dictionary
Function that inverts the keys and values of a dictionary, with duplicate detection.

### Level 2

#### 1. Word Counter and Organizer
Reads a TXT file and displays words sorted alphabetically with their frequencies.

#### 2. Data Type Conversion
Function that separates list elements into two groups: convertible to float and non-convertible.

### Level 3

#### 1. Password Generator
Creates secure random passwords with configurable parameters:
- `length` (int): Desired length
- `uppercase` (bool): Include uppercase letters
- `lowercase` (bool): Include lowercase letters
- `numbers` (bool): Include numbers
- `signs` (bool): Include special characters

**Extra:** Automatically copy to clipboard.

#### 2. Data Processing - Football Matches
Processes a file with match history and returns:
- Total goals per team
- Highest-scoring team
- Most-scored-against team
- Overall standings (win: 3 pts, draw: 1 pt, loss: 0 pts)

## 🚀 How to Use

1. Open the file `functions_structures_data_loops.ipynb` in Jupyter Notebook or JupyterLab
2. Execute the cells for each exercise
3. Results will be displayed directly in the notebook

### Usage Example

```python
# BMI Calculator
bmi_result = calculate_bmi(70, 1.75)
print(bmi_result)

# Temperature Converter
conversions = convert_temperature(25, 'C')
print(conversions)

# Word Counter
frequency = count_words("Hello how are you? Hello!")
print(frequency)
```

## Dependencies

- Python 3.7+
- numpy (for password generator)
- pandas (optional, for data processing)

## Completion Requirements

- ✔️ Reproducible and well-commented code
- ✔️ Functions return results (not just prints)
- ✔️ Input data validation
- ✔️ Working demonstration for each exercise
- ✔️ Handling of special cases and errors

## Important Notes

- All outputs that need to be stored must be returned as variables, not just displayed with `print()`
- It is recommended to validate user inputs to avoid errors
- Try to optimize code by avoiding repetitive structures (multiple if/else statements)
