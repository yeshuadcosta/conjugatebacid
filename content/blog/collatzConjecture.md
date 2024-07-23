---
title: The Impossible Conjecture
description: This is the very first post
date: 2023-10-29
tags:
  - mathematics
  - conjectures
---

### Introduction

The Collatz Conjecture is an unsolved problem in mathematics. This conjecture is named after the mathematician Lothar Collatz, who introduced the idea in 1937. The conjecture also known as Syrucuse conjecture or problem.

_Take any positive integer n. If n is even then divide it by 2, else do "triple plus one" and get 3n+1. The conjecture is that for all numbers, this process converges to **one**._ 

> Paul Erdős said about the Collatz conjecture, "Mathematics may not be ready for such problems."

> Jeffrey Lagarias stated that the Collatz conjecture "is an extraordinarily difficult problem, completely out of reach of present day mathematics."

**Implementation Of The Collatz Conjecture in C++**
```c
#include <iostream>

using namespace std;

int main (){
  int numeral{0};

	cout << "Enter the Numeral: ";
	cin >> numeral;

    int MAX_ITERATIONS{0};
    int count{0};

    cout << "Enter the number of iterations of the sequence: ";
    cin >> MAX_ITERATIONS;

    while (count<=MAX_ITERATIONS){
        if (numeral%2 == 0){
            // If the numeral is even, divide it by 2
            numeral = (numeral/2);
            cout << "/2: " << numeral << endl;
        }
        else if (numeral%2!=0){
            // If the numeral is odd, multiply it by 3 and add 1
            numeral = (numeral*3)+1;
            cout << "3x+1: " << numeral << endl;
        }

        // The following code restricts the number of repetitions of the sequence `4, 2, 1`
        if (numeral == 1)
            ++count;
    }

    cout << "The sequence `4, 2, 1` has been repeated " << MAX_ITERATIONS << " times!";
    return 0;
}
```

The constant `MAX_ITERATIONS` controls the maximum number of times, the sequence `4, 2, 1` is repeated while the variable `count` stores the number of occurences of the number `1`

If the number is _even_, it is divided by `2`, its divisibility by `2` is proven by `numeral%2`, which in this case, should be equal to zero.

If the number is _odd_, it is multiplied by `3` and '1' is added to the product, its divisibility by `2` in this case `numeral%2`, should not be equal to zero and should provide the remainder of the number on division by `2`

**Output of the C++ Code**

For the following example, the number `10` has been used

```bash
Enter the Numeral: 10
Enter the number of iterations of the sequence: 3
/2: 5.0
3x+1: 16.0
/2: 8.0
/2: 4.0
/2: 2.0
/2: 1.0
3x+1: 4.0
/2: 2.0
/2: 1.0
3x+1: 4.0
/2: 2.0
/2: 1.0
3x+1: 4.0
/2: 2.0
/2: 1.0
The sequence `4, 2, 1` has been repeated 3 times.
```