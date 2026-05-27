# Chinese ID Checksum Tool

This is a simple C++ program for calculating and validating the checksum digit of a Chinese Resident Identity Card number.

The program is designed for educational and validation purposes only. It demonstrates how the checksum digit of an 18-digit Chinese National ID number is calculated using the official weighting method.

## Features

- Calculate the final checksum character from the first 17 digits of a Chinese ID number
- Validate whether an 18-digit Chinese ID number has the correct checksum
- Support checksum values from `0` to `9` and `X`
- Handle lowercase `x` as valid input when validating a full ID number
- Provide basic input checking for length and digit format

## Background

An 18-digit Chinese Resident Identity Card number consists of several parts:

- The first 6 digits represent the administrative region code
- Digits 7 to 14 represent the birth date in `YYYYMMDD` format
- Digits 15 to 17 represent the sequence code
- Digit 18 is the checksum character

The checksum is calculated from the first 17 digits using a fixed set of weights.

The weight values are:

7, 9, 10, 5, 8, 4, 2, 1, 6, 3, 7, 9, 10, 5, 8, 4, 2

After multiplying each of the first 17 digits by its corresponding weight, the products are added together. The sum is then divided by 11, and the remainder is used to determine the checksum character.

The checksum mapping is:

0 -> 1  
1 -> 0  
2 -> X  
3 -> 9  
4 -> 8  
5 -> 7  
6 -> 6  
7 -> 5  
8 -> 4  
9 -> 3  
10 -> 2  

## How It Works

For a 17-digit input, the program calculates the correct final checksum character and prints the complete 18-digit number.

For an 18-digit input, the program recalculates the checksum from the first 17 digits and compares it with the final character entered by the user.

If the two values match, the ID number passes the checksum validation.

## Example

Input:

11010519491231002

Output:

The checksum character is: X  
The complete ID number is: 11010519491231002X

Another example:

Input:

11010519491231002X

Output:

This ID number has a valid checksum.

## How to Compile

Use a C++ compiler such as `g++`.

g++ main.cpp -o id_checksum

## How to Run

After compiling the program, run:

./id_checksum

On Windows, run:

id_checksum.exe

## File Structure

main.cpp

## Notes

This program only checks the mathematical checksum of a Chinese ID number.

It does not verify whether the ID number belongs to a real person. It also does not confirm whether the region code, birth date, or sequence code is officially registered.

This project should not be used to generate, collect, store, or expose real personal identity information.

## Purpose

This project was created as a small C++ practice program. It is useful for learning:

- String processing
- Character and integer conversion
- Arrays
- Input validation
- Functions
- Basic checksum algorithms

## Disclaimer

This tool is for programming practice and educational use only. It should be used responsibly and only with test data or data that the user is authorized to check.
