# 3121 Format for Final

## Polynomial Multiplication

1. Write down assumptions

   The product of a polynomial A(x) of degree 16 and a polynomial B(x) of degree 8 is a polynomial C(x) of degree 24.

2. Specify required inputs

    Hence in order to uniquely determine C(x), we need its values at 25 inputs, so we choose x = −12, −11, . . . , −1, 0, 1, . . . , 12.

3. Evaluate individual polynomial functions

   We now evaluate A(i) and B(i) for all i such that −12 ≤ i ≤ 12. Note that this does not involve any multiplication of two arbitrarily large numbers but only multiplications of one arbitrarily large number (a coefficient of A(x) or B(x)) with a constant.

4. Combine individual results from A(i) and B(i), leads to C(i)

   We now perform 25 large number multiplications which produce the values of the product polynomial C(x) = A(x)B(x) at inputs ranging from −12 to 12.

   Having found C(−12) = A(−12)B(−12), . . . , C(12) = A(12)B(12), we now solve the following system of 25 linear equations in variables C0, . . . , C24: {C0 + C1i + C2i 2 + . . . + C24i 24 = C(i) = A(i)B(i) : −12 ≤ i ≤ 12}

5. Conclusion

   Solving such a system expresses the solutions for C0, . . . , C24 as a linear combination of values of C(i) and thus involves only constants times large values multiplications. So in total we have used only 25 multiplications where both numbers can be arbitrarily large, because they depend on the values of the coefficients of polynomials A(x) and B(x).

   