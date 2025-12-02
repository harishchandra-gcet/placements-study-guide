# Practice Questions - Coding

## Q1

There is a lift in your society that can accommodate a maximum weight of **X units**. The weights of the people planning to use the lift are given in an integer array **A** of size **N**. Your task is to find and return an integer value representing the **maximum number of people** that can use the lift together without exceeding its weight capacity.



### Input Specification:

* **input1**: An integer value $\mathbf{N}$ representing the number of people planning to use the lift.
* **input2**: An integer value $\mathbf{X}$ representing the maximum weight capacity of the lift.
* **input3**: An integer array $\mathbf{A}$ containing the weights of the people planning to use the lift.



### Output Specification:

Return an integer value representing the maximum number of people that can use the lift together without exceeding its weight capacity.



### Example 1:

* **input1**: 3
* **input2**: 9
* **input3**: $\mathbf{\{5, 1, 5\}}$

**Output**: 2

---

## Q2

You are given an array of integers containing $\mathbf{N}$ elements. Your task is to find and return an integer value representing the total number of **subarrays of size 3** such that the **sum of the first element and the third element is equal to the second element**.

> **Note**: A continuous part of an array is a subarray.



### Input Specification:

* **input1**: An integer array of size $\mathbf{N}$.
* **input2**: An integer value $\mathbf{N}$, representing the size of array.



### Output Specification:

Return an integer value representing the total number of subarrays of size 3 such that the sum of the first element and the third element is equal to the second element.



### Example 1:

* **input1**: $\mathbf{\{1, 2, 1, 3, 5, 2, 4, 2\}}$

**Output**: 3

---

## Q3

You need to arrange books in a library with the help of students. Each student has a collection of books. Bookshelves can hold a maximum of **K books** and must be fully filled. If a student has more books than shelf capacity, the **excess books carry over to the next student's shelf**. If they have fewer books, those books also carry over to the next student's shelf. Your task is to calculate and return the total number of fully decked bookshelves.

1.  If the last student has any extra books, those books are discarded.
2.  If the last student has fewer books than that of shelf capacity, then those books to be discarded.



### Input Specification:

* **input1**: An integer $\mathbf{N}$ representing the number of students.
* **input2**: An integer $\mathbf{K}$, representing the maximum number of books a shelf can hold.
* **input3**: An integer array representing the number of books each student has.



### Output Specification:

Return an integer value representing the **total number of bookshelves** that are completely decked by the books.



### Example 1:

* **input1**: 4
* **input2**: 4
* **input3**: $\mathbf{\{5, 7, 8, 10\}}$

**Output**: 7



