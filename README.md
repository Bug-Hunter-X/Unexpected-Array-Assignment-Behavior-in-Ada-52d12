# Ada Array Assignment Bug

This repository demonstrates a common misconception regarding array assignments in Ada.  While Ada supports array copying through simple assignment, this creates a *deep copy*.  Modifications to one array do not affect the other.

## Bug Description
The included `bug.ada` file contains a short Ada program that showcases this.  It initializes an array A, copies it to array B, and then modifies the first element of B.  The expectation might be that A(1) also changes; however, this is not the case in Ada.

## Solution
The `bugSolution.ada` file demonstrates no changes are required.  This behavior is the expected behavior of Ada. However, it's crucial to understand that the assignment creates a distinct copy, and understanding that it does is very important.  It does make certain copy operations more expensive than other languages where copy-on-write or other optimizations might apply.