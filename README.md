Created by: Raphael Luis L. Bachoco | 2ECE-D

This repository contains content that pertains to Programming Assignment 2 of ECE 2112: Advanced Computer Programming and Algorithms, SY: 2026-2027

# A. REPRODUCIBLE NORMALIZATION PROBLEM
> Create a reproducible random 5×5 integer ndarray named X. Use the following two statements before
> performing any calculation:
> np.random.seed(2112)
> X = np.random.randint(10, 101, size = (5, 5))
> Normalize the complete array using $Z = \frac{X - \bar{x}}{\sigma},$
> where ¯x is the mean of all 25 elements and σ is their population standard deviation as returned by
NumPy’s default std() call. Store the normalized array in X normalized.
Required checks: Display X, X normalized, its mean, and its standard deviation. Up to floatingpoint rounding, the normalized mean must be 0 and the normalized standard deviation must be 1.

```
import numpy as np
```
First we start off with importing numpy into the notebook while creating a shortcut for it using the name ` np`. This way we can call future numpy fuctions using just `np.`.

```
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
```
We are given the random seed 2112 of which the generated array seed will be assigned to the variable X, with its shape to be (5,5) with the values of numbers from 10 to 100. Note that in creating an array the last number would not be included. For example 101 would not be included but rather 100.

```
Mean = np.mean(X)
```
To get the mean of the array we can use the given code which call a numpy function of which it is assigned to the variable `Mean`.

```
Std = np.std(X)
```
We can also get the standard deviation of the given array using the given code of which would be assigned to the variable Std.

```
A = X - Mean
```
This step is done to calculate the numerator of the formula which is $Z = \frac{X - \bar{x}}{\sigma},$.

```
X_normalized = A / Std
```
We can  get X_normalized using the new variable A and the standard deviation of which A/Std is the normalized array.

```
X_normalized_Mean = np.mean(X_normalized)
```
To get the mean of X_normalized we can use the numpy fuction `np.mean()` then we can assign it to the new variable `X_normalized_Mean`

```
X_normalized_Std = np.std(X_normalized)
```
Same goes for `np.std()` of which the given value is the standard deviation of X_normalized of which we can assign it to `X_normalized_Std`

```
np.save("X_normalized.npy",X_normalized)
```
Used to save the array `X_normalized`

Problem A Function:
```
import numpy as np
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
Mean = np.mean(X)
Std = np.std(X)
A = X - Mean
X_normalized = A / Std
X_normalized_Mean = np.mean(X_normalized)
X_normalized_Std = np.std(X_normalized)
np.save("X_normalized.npy",X_normalized)
```


# B. CUBES DIVISIBLE BY 4 PROBLEM
>Using NumPy, create the first 100 positive integers, cube every element, and reshape the result into a
10 × 10 ndarray named C. Thus, C begins with 13 and ends with 1003
.
Use a Boolean condition on C to obtain every cubed value divisible by 4. Store the selected values in
div by 4. Preserve NumPy’s normal row-major selection order.
Required checks: Display the shape of C, the array div by 4, and the number of selected elements.
A correct solution has 50 selected elements; the first is 8 and the last is 1,000,000.

```
A = np.arange(1,101,1)
```
We can create an array using the another numpy function `np.arrange()` in which the first 100 positive integers are the elements. Note that the final element would not be 101 but rather 100.

```
C = A ** 3
```
This is used to cube every element inside the array "A" and the results would be assigned to the variable C .

```
C.reshape(10,10)
```
To get the array to have the shape of (10,10) `.reshape()` is used to get the desired shape which in this case is 10x10. 

```
Z = C[C % 4 == 0]
```
To calculate which elements would remain in the array we can use the given code. `C % 4 == 0` Calculates each elements of the array to modulo 4 and if the element is equal to 0, given by ` == 0 ` of which the given results would either be true or false. `C[C % 4 == 0]` by adding `C` it stores the true values in the variable `C` in which it stored to the new variable `Z` by using  `Z = C[C % 4 == 0`

```
div_by_4 = Z
```
The variable Z is stored onto the new variable div_by_4.

```
np.save("div_by_4.npy",div_by_4)
```
Used to save the array `div_by_4`

Problem B Function:
```
A = np.arange(1,101,1)
C = A ** 3
C.reshape(10,10)
Z = C[C % 4 == 0]
div_by_4 = Z
np.save("div_by_4.npy",div_by_4)
```

# C. ABOVE-MEAN SQUARES PROBLE
> Create a 6 × 6 ndarray named S containing the squares of the first 36 positive integers in increasing
row-major order. Compute the mean of all elements of S and store it in S mean. Then use Boolean
filtering to select only the elements strictly greater than S mean. Store these values in above mean.
Required checks: Display S, S mean, above mean, and the number of selected elements. A correct
solution has 15 selected elements; the first is 484 and the last is 1296


```
B = np.arange(1,37,1)
```
An array with the variable name `B` is created using the numpy function `np.arrage()` which has the elements of the first 36 positive integers. Note that 37 is not included but rather 36.

```
S = (B ** 2).reshape(6,6)
```
To square each element in the array `B` we can use `B ** 2` and to reshape the shape into a 6x6 array we can use `.reshape()`. After all this we can store it to the new variable `S`

```
S_mean = np.mean(S)
```
To get the mean of the array `S` we can call the numpy function `np.mean()` and assign it to the variable name `S_mean`

```
above_mean = S[S > S_mean]
```
To get the elements inside the array `S` which has greater values than the mean of the array `S` we can use `S[S > S_mean]` which basically means to get the elements which has a greater value than the calculated mean and assign it to the variable name `above_mean`

```
np.save("above_mean",above_mean)
```
Used to save the array `above_mean`


Problem C Function:
```
B = np.arange(1,37,1)
S = (B ** 2).reshape(6,6)
S_mean = np.mean(S)
above_mean = S[S > S_mean]
np.save("above_mean",above_mean)
```
#### HISTORY 
- August 31, 2026 - README.md File Created, Google Colab Solutions Notebook Uploaded
- September 1, 2026 - README.md File Updated, Google Colab Solutions Notebook Updated
- September 2, 2026 - README.md File Updated, Problem A,B,C Updated, Uploaded X_normalized.npy, div_by_4.npy, above_mean.npy Files
