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


# B. CUBES DIVISIBLE BY 4 PROBLEM
>Using NumPy, create the first 100 positive integers, cube every element, and reshape the result into a
10 × 10 ndarray named C. Thus, C begins with 13 and ends with 1003
.
Use a Boolean condition on C to obtain every cubed value divisible by 4. Store the selected values in
div by 4. Preserve NumPy’s normal row-major selection order.
Required checks: Display the shape of C, the array div by 4, and the number of selected elements.
A correct solution has 50 selected elements; the first is 8 and the last is 1,000,000.





# C. ABOVE-MEAN SQUARES PROBLE
> Create a 6 × 6 ndarray named S containing the squares of the first 36 positive integers in increasing
row-major order. Compute the mean of all elements of S and store it in S mean. Then use Boolean
filtering to select only the elements strictly greater than S mean. Store these values in above mean.
Required checks: Display S, S mean, above mean, and the number of selected elements. A correct
solution has 15 selected elements; the first is 484 and the last is 1296







#### HISTORY 
- August 31, 2026 - README.md File Created, Google Colab Solutions Notebook Uploaded
- September 1, 2026 - README.md File Updated, Google Colab Solutions Notebook Updated
