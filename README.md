
# Collaborative Filtering Book Recommendation System

## Table of Contents
1. [Introduction](#introduction)
2. [Installation](#installation)
3. [Code Explanation](#code-explanation)
   - [parse_genre_string function](#parse_genre_string-function)
   - [book_response function](#book_response-function)
4. [Example](#example)
5. [Usage](#usage)

## Introduction
This repository contains a book recommendation system based on collaborative filtering algorithm using book genres data. It provides recommendations based on user-specified genres.

## Installation
There is no specific installation required for this repository apart from having Python and necessary libraries (like pandas) installed.


## Code Explanation

### Functions

#### `parse_genre_string` function

This function is responsible for parsing the genre information from the dataset. It takes a genre string in a specific format and returns a list of genres.

##### Explanation:

1. `genre_string.strip('[]')`: Removes leading and trailing square brackets from the genre string.
2. `genre_string.replace("'", "")`: Removes any single quotes from the string.
3. `genre_string.strip()`: Removes any leading or trailing whitespace.
4. `genre_string.split(", ")`: Splits the cleaned string by comma and space to extract individual genres.

#### `book_response` function

This function performs the actual recommendation based on user inputs. It iterates through each row of the dataset and checks if any of the user-specified genres match with the genres of the current book.

##### Explanation:

1. `user_inputs = [input.lower() for input in user_inputs]`: Converts user inputs to lowercase for case-insensitive matching.
2. Iterates through each row in the dataset (`df.iterrows()`).
3. `parse_genre_string(row['genres'])`: Parses genres for the current book.
4. Checks if any user input matches any genre in the current row.
5. Collects titles of books that match the user inputs and returns up to 10 recommendations.



## Example

```python
# Example usage
user_inputs = ['fantasy', 'adventure']
recommendations = book_response(user_inputs)
print("Recommended books:")
for title in recommendations:
    print(title)
```

## Usage
To use the recommendation system:
1. Ensure you have the required dataset (`books_reviews.csv`) in the same directory.
2. Run the `book_response` function with appropriate user inputs to get book recommendations.
