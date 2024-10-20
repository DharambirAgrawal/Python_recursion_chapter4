```markdown
# Python Recursion

## Overview

This repository contains various algorithms and their implementations, focusing on recursive techniques. The goal is to provide a comprehensive understanding of recursion through practical examples and detailed explanations.

## Table of Contents

1. [Introduction](#introduction)
2. [Algorithms](#algorithms)
    - [Finding Maximum Element](#finding-maximum-element)
    - [Power Computation](#power-computation)
    - [Harmonic Number Calculation](#harmonic-number-calculation)
    - [String to Integer Conversion](#string-to-integer-conversion)
    - [Isabel's Summation Algorithm](#isabels-summation-algorithm)
3. [Recursion Traces](#recursion-traces)
4. [Running Time and Space Usage](#running-time-and-space-usage)

## Introduction

This repository is designed to help you understand and implement recursive algorithms. Each algorithm is accompanied by a detailed explanation and a recursion trace to visualize the process.

## Algorithms

### Finding Maximum Element

A recursive algorithm to find the maximum element in a sequence of `n` elements.

```python
def find_max(S, n, max):
    if n == 0:
        return max
    if max < S[n]:
        return find_max(S, n-1, S[n])
    else:
        return find_max(S, n-1, max)

S = [6, 0, 5, 3, 7, 2, 64, 2, 89, 7]
a = find_max(S, len(S)-1, S[0])
print(a)
```

### Power Computation

A recursive function to compute the power of a number using the traditional method and repeated squaring algorithm.

```python
def power(x, n):
    if n == 0:
        return 1
    else:
        partial = power(x, n // 2)
        result = partial * partial
        if n % 2 == 1:
            result *= x
        return result

power(2, 5)
```

### Harmonic Number Calculation

A recursive function to compute the nth Harmonic number.

```python
def harmonic(n):
    if n == 1:
        return 1
    return 1/n + harmonic(n-1)

harmonic(3)
```

### String to Integer Conversion

A recursive function to convert a string of digits into the integer it represents.

```python
def conv_num(str, ord):
    if len(str) == 0:
        return 0
    return int(str[len(str)-1]) * ord + conv_num(str[:-1], ord * 10)

str = '123452'
a = conv_num(str, 1)
print(a, type(a))
```

### Isabel's Summation Algorithm

Isabel's method for summing up the values in a sequence where the length is a power of two.

```python
# There are total log n levels, and the total number of operations performed per level is n.
# so running time is O(n log(n))
```

## Recursion Traces

Detailed recursion traces for various algorithms to help visualize the recursive process.

### Power Computation Trace

```python
# power(2, 4)
#   -> 2 * power(2, 3)
#       -> 2 * power(2, 2)
#           -> 2 * power(2, 1)
#               -> 2 * power(2, 0)
#                   -> 1 (base case)
#               <- 2
#           <- 4
#       <- 8
#   <- 16
```

### Reverse Function Trace

```python
# reverse(S=[4,3,6,2,6], 0,5)
#   ->  reverse(S=[6,3,6,2,4],1, 4)
#       -> reverse(S=[6,2,6,3,4],2, 3)
#           ->  reverse(S=[5,5,6,3,4],3, 2) (base case since 3>2)
```

## Running Time and Space Usage

- **Finding Maximum Element**: Time Complexity O(n), Space Complexity O(n)
- **Power Computation**: Time Complexity O(log n), Space Complexity O(log n)
- **Harmonic Number Calculation**: Time Complexity O(n), Space Complexity O(n)
- **String to Integer Conversion**: Time Complexity O(n), Space Complexity O(n)
- **Isabel's Summation Algorithm**: Time Complexity O(n log(n))

```