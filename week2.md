# Lecture - 1

Whenever we have an algorithm, there are three questions we always ask about it:
1. Is it correct?
2. How much time does it take, as a function of n?
3. And can we do better?

## Fibonacci Series

The fibonacci series is a sequence of numbers each the sum of its two immediate predecessors.
0, 1, 1, 2, 3, 5, 8, 13, 21 .... so on.

Formally, the n <sup>th</sup> fibonacci number in the sequence (f <sub>n </sub>) is given by:
- F <sub>n </sub> = F<sub> n-1 </sub> + F <sub> n-2 </sub> if n > 1
- F <sub>n </sub> = 1               if n = 1 
- F <sub>n </sub> = 0               if n = 0 

### Algorithm 1 to calculate F <sub>n</sub>

This algorithm recursively calculates F <sub>n</sub>:

```python 
function fib1(n)
if n = 0: return 0
if n = 1: return 1
return fib1(n − 1) + fib1(n − 2)
```

