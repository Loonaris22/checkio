# First Word (simplified)
You are given a string and you have to find its first word.

This is a simplified version of the First Word mission, which can be solved later.

The input string consists of only English letters and spaces.
There aren’t any spaces at the beginning and the end of the string.

Input: A string.

Output: A string.

```python
def first_word(text: str) -> str:

    return (text.split())[0]
```

# The Most Frequent
You have a sequence of strings, and you’d like to determine the most frequently occurring string in the sequence. It can be only one.

Input: non empty list of strings.

Output: a string.

```python
def most_frequent(data: list) -> str:
    counter = 0
    num = []
    for i in data:
        current = data.count(i)
        if current > counter:
            counter = current
            num = i
    return num
```

# Number Length
You have a positive integer. Try to find out how many digits it has?

Input: A positive Int

Output: An Int.

```python
def number_length(a: int) -> int:
    return len(str(a))
if __name__ == "__main__":
    print("Example:")
    print(number_length(10))
```

# End Zeros
Try to find out how many zeros a given number has at the end.

Input: A positive Int

Output: An Int.

```python
def end_zeros(num: int) -> int:
    string = str(num)[::-1]
    counter = 0
    for i in string:
        if i == '0':
            counter += 1
        else:
            break
    return counter
```

# Backward String
You should return a given string in reverse order.

Input: A string.

Output: A string.

```python
def backward_string(val: str) -> str:
    return val[::-1]
if __name__ == '__main__':
    print("Example:")
    print(backward_string('val'))
```

# Easy Unpack
Your mission here is to create a function that gets a tuple and returns a tuple with 3 elements - the first, third and second element from the last for the given array.

Input: A tuple, at least 3 elements long.

Output: A tuple.

```python
def easy_unpack(elements: tuple) -> tuple:
    return (elements[0], elements[2], elements[-2])
if __name__ == '__main__':
    print('Examples:')
    print(easy_unpack((1, 2, 3, 4, 5, 6, 7, 9)))
```

# Remove All Before
Not all of the elements are important. What you need to do here is to remove from the list all of the elements before the given one.

We have two edge cases here: (1) if a cutting element cannot be found, then the list shoudn't be changed. (2) if the list is empty, then it should remain empty.

Input: List and the border element.

Output: Iterable (tuple, list, iterator ...).

```python
def remove_all_before(items: list, border: int) -> Iterable:
    if border in items:
        return items[items.index(border):]
    else:
        return items
```

# All Upper I
Check if a given string has all symbols in upper case. If the string is empty or doesn't have any letter in it - function should return True.

Input: A string.

Output: a boolean.

```python
def is_all_upper(text: str) -> bool:
    new = ''.join(text.split())
    if new == '' or new.isdigit() == True:
        return True
    else:
        if new.isupper() == True:
            return True
        else:
            return False
```

# Replace First
In a given list the first element should become the last one. An empty list or list with only one element should stay the same.

Input: List.

Output: Iterable.

```python
def replace_first(items: list) -> Iterable:
    if items != []:
        items.append(items[0])
        items.pop(0)
        return items
    else:
        return items
```

# Split Pairs
Split the string into pairs of two characters. If the string contains an odd number of characters, then the missing second character of the final pair should be replaced with an underscore ('_').

Input: A string.

Output: An iterable of strings.

```python
def split_pairs(a):
    new = []
    if len(a) % 2 != 0:
        a += '_'
    for i in range(0, len(a), 2):
        new.append(a[i : i + 2])
    return new
```

# Between Markers (simplified)
You are given a string and two markers (the initial one and final). You have to find a substring enclosed between these two markers. But there are a few important conditions.

This is a simplified version of the Between Markers mission.

The initial and final markers are always different.
The initial and final markers are always 1 char size.
The initial and final markers always exist in a string and go one after another.
Input: Three arguments. All of them are strings. The second and third arguments are the initial and final markers.

Output: A string.

```python
def between_markers(text: str, begin: str, end: str) -> str:
    first = text.index(begin)
    second = text.index(end)
    if second - first != 0:
        return text[first + 1 : second]
    else:
        return ''
```

# Correct Sentence
For the input of your function, you will be given one sentence. You have to return a corrected version, that starts with a capital letter and ends with a period (dot).

Pay attention to the fact that not all of the fixes are necessary. If a sentence already ends with a period (dot), then adding another one will be a mistake.

Input: A string.

Output: A string.

```python
def correct_sentence(text: str) -> str:
    if text[-1] != '.':
        return text.replace(text[0], text[0].upper(), 1) + '.'
    else:
        return text.replace(text[0], text[0].upper(), 1)
```

# Beginning Zeros
You have a string that consist only of digits. You need to find how many zero digits ("0") are at the beginning of the given string.

Input: A string, that consist of digits.

Output: An Int.

```python
def beginning_zeros(number: str) -> int:
    counter = 0
    for i in number:
        if i == '0':
            counter += 1
        else:
            break
    return counter
```

# Nearest Value
Find the nearest value to the given one.

You are given a list of values as set form and a value for which you need to find the nearest one.

For example, we have the following set of numbers: 4, 7, 10, 11, 12, 17, and we need to find the nearest value to the number 9. If we sort this set in the ascending order, then to the left of number 9 will be number 7 and to the right - will be number 10. But 10 is closer than 7, which means that the correct answer is 10.

```python
def nearest_value(values: set, one: int) -> int:
    if one in values:
        return one
    n = 1
    while True:
        if (one - n) in values:
            return one - n
        elif (one + n) in values:
            return one + n
        n += 1
```

# Sum Numbers
In a given text you need to sum the numbers while excluding any digits that form part of a word.

The text consists of numbers, spaces and letters from the English alphabet.

Input: A string.

Output: An int.

```python
def sum_numbers(text: str) -> int:
    new = text.split()
    list = []
    for i in new:
        if i.isdigit() == True:
            list.append(int(i))
    return sum(list)
```

# Even the Last
You are given an array of integers. You should find the sum of the integers with even indexes (0th, 2nd, 4th...). Then multiply this summed number and the final element of the array together. Don't forget that the first element has an index of 0.

For an empty array, the result will always be 0 (zero).

Input: A list of integers.

Output: The number as an integer.

```python
def checkio(array: list) -> int:
    if len(array) >= 1:
        return (sum(array[::2])) * array[-1]
    else:
        return 0
```

# Three Words
You are given a string with words and numbers separated by whitespaces (one space). The words contains only letters. You should check if the string contains three words in succession . For example, the string "start 5 one two three 7 end" contains three words in succession.

Input: A string with words.

Output: The answer as a boolean.

```python
def checkio(words: str) -> bool:
    list = words.split()
    count = 0
    for i in list:
        if not i.isdigit():
            count += 1
            if count == 3:
                return True
        else: 
            count = 0
    return False 
```

# Sun Angle
Every true traveler must know how to do 3 things: fix the fire, find the water and extract useful information from the nature around him. Programming won't help you with the fire and water, but when it comes to the information extraction - it might be just the thing you need.

Your task is to find the angle of the sun above the horizon knowing the time of the day. Input data: the sun rises in the East at 6:00 AM, which corresponds to the angle of 0 degrees. At 12:00 PM the sun reaches its zenith, which means that the angle equals 90 degrees. 6:00 PM is the time of the sunset so the angle is 180 degrees. If the input will be the time of the night (before 6:00 AM or after 6:00 PM), your function should return - "I don't see the sun!".

Input: The time of the day.

Output: The angle of the sun, rounded to 2 decimal places.

```python
from typing import Union


def sun_angle(time: str) -> Union[int, str]:
    n = int(time[:2]) + int(time[3:]) / 60
    if 6 <= n <= 18:
        return (n - 6) * 15
    else:
        return "I don't see the sun!"
```

# Split List
You have to split a given array into two arrays. If it has an odd amount of elements, then the first array should have more elements. If it has no elements, then two empty arrays should be returned.

Input: Array.

Output: Array or two arrays.

```python
from math import *
def split_list(items: list) -> list:
    result = [[], []]
    lenght = ceil((len(items) / 2))
    for i in range(lenght):
        result[0].append(items[i])
    for i in range(1, len(items) - lenght + 1):
        result[1].append(items[-i])
    result[1].reverse()
    return result
```

# All the Same
In this mission you should check if all elements in the given list are equal.

Input: List.

Output: Bool.

```python
from typing import List, Any
def all_the_same(elements: List[Any]) -> bool:
    return len(set(elements)) <= 1
```