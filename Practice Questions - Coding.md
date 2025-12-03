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

---

## Q4

You are a teacher organizing a field trip for your students. You have a class of **N students**, and you want to divide them into two groups for the trip. However, you have a special requirement:

* One group should only consist of students with **even-numbered IDs**.
* The other group should only consist of students with **odd-numbered IDs**.
* Both groups must be of the **same length**.

Your task is to find and return an integer value representing the **maximum number of students** that can be included in both groups.

### Input Specification:

* **input1**: An integer value $\mathbf{N}$ representing the total number of students.
* **input2**: An integer array containing the **IDs** of the students.

### Output Specification:

Return an integer value representing the **maximum number of students** that can be included in both groups.

---

## Q5

A ship needs to transport a certain number of people from **Point A to Point B**. The capacity of the ship is denoted by an integer $\mathbf{C}$, and the total number of people to be transported is denoted by an integer $\mathbf{N}$. Your task is to find and return the number of rounds the ship needs to make in order to transport all the people from Point A to Point B.

> **Note**: One round consists of the ship travelling from Point A to Point B and then returning to Point A.

### Input Specification:

* **input1**: An integer value $\mathbf{C}$ representing the capacity of the ship.
* **input2**: An integer value $\mathbf{N}$ representing the total number of people to be transported.

### Output Specification:

Return an integer value representing the number of rounds the ship needs to make.

---

## Q6

You are given an array of length $\mathbf{N}$ with the salary details of some people. You can pay the salary using only **one type of note of any value**. Your task is to find and return an integer value representing the **minimum number of notes required to pay the salary of all the people** if you can change the salary of a maximum of one person.

### Input Specification:

* **input1**: An integer value $\mathbf{N}$ representing the number of people.
* **input2**: An integer array, representing the salary of every person.

### Output Specification:

Return an integer value representing the minimum number of notes required to pay the salary of all the people.

### Example 1:

* **input1**: 4
* **input2**: $\mathbf{\{2, 4, 6, 3\}}$

**Output**: 7

---

## Q7

You are given a **string array** of length $\mathbf{N}$. Your task is to find and return an integer value representing the **maximum permutation count** of the strings after **removing all the vowels** from every element in the string array.

### Note:

* Consider all the letters in the string as **different** (if the word is 'doll', then consider both 'l's as different).
* If there are no permutable characters, then return $\mathbf{0}$.
* The string consists of both uppercase and lowercase characters. (However, the examples treat 'a' and 'A' as the same vowel, and all resulting characters as unique for permutation count).

### Input Specification:

* **input1**: A string array of length $\mathbf{N}$.
* **input2**: An integer value $\mathbf{N}$, representing the size of the string array.

### Output Specification:

Return an integer value representing the **maximum permutation count** of the string elements.

### Example 1:

* **input1**: $\{\text{"hello"},\ \text{"ccbc"},\ \text{"aaeiou"}\}$
* **input2**: 3
* **Output**: 24

#### Explanation:

Here, we are given the string array $\{\text{"hello"},\ \text{"ccbc"},\ \text{"aaeiou"}\}$. The permutations possible for these string elements excluding the vowels are as under:

1.  The first element, "**hello**," has 2 vowels ('e', 'o'), so the permutable letters are $5-2=3$, i.e., 'h', 'l', 'l'. So, its permutations are $3! = 6$.
2.  The second element, "**ccbc**," has no vowel, so the permutable letters are 4, i.e., 'c', 'c', 'b', 'c'. So, its permutations are $4! = 24$.
3.  The third element, "**aaeiou**," has vowels only ('a', 'a', 'e', 'i', 'o', 'u'), so there are no permutable letters. So, its possible permutation is 0.

As we can see, "**ccbc**" has the maximum possible permutation of 24. Therefore, $\mathbf{24}$ is returned as the output.

### Example 2:

* **input1**: $\{\text{"eio"}\}$
* **input2**: 1
* **Output**: 0

#### Explanation:

Here, we are given the string array contains one element. This element, "**eio**," has only vowels ('e', 'i', 'o'), and there are no permutable letters. Hence no permutation is possible. Therefore, $\mathbf{0}$ is returned as the output.