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

#### Analysis:

For larger values of n, there are two recursive invocations of fib1, taking time
T(n − 1) and T(n − 2), respectively, plus three computer steps (checks on the value
of n and a final addition). Therfore, the recurrence relation comes out to be:

T(n) = T(n − 1) + T(n − 2) + 3 for n > 1

We see that T(n) ≥ F<sub>n</sub>. This implies that the running time of the algorithm grows as fast as the
Fibonacci numbers! T(n) is exponential in n, which implies that the algorithm is
impractically slow except for very small values of n.
So this naive algorithm is correct but inefficient in time complexity.

### Algorithm 2 to calculate F <sub>n</sub>

fib1 was inefficient because many computations are repeated in the recursive calls. 
A more sensible scheme would store the intermediate results—the values F <sub>0</sub> , F <sub>1</sub> , . . . ,F <sub>n-1</sub> as soon as they become known. 
fib2 does the same:

```python
function fib2(n)
if n = 0: return 0
create an array f[0 . . . n]
f[0] = 0, f[1] = 1
for i = 2 . . . n:
f[i] = f[i − 1] + f[i − 2]
return f[n]
```

#### Analysis:

The time complexity appears to be linear but it is not for larger values of n.
It is reasonable to treat addition as a single computer step if small numbers are being added, 32-bit numbers say. But the nth Fibonacci number is about 0.694n bits long, and this can far exceed 32 as n grows.
Given that the addition of two n-bit numbers takes time roughly proportional to n, the time complexity of fib2 is proportional to n<sup>2</sup>.

### Algorithm 3 to calculate F <sub>n</sub>

We use matrix multiplication to calculate F <sub>n</sub>. We express each F <sub>i</sub> in the form of a 2*2 matrix.
As in,

![f0](f0.png)

![fn](fn.png)

