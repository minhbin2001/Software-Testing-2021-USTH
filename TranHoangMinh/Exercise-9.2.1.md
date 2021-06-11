Exercise 9.2.1

Provide reachability conditions, infection conditions, propagation conditions, and test case values to kill mutants 2, 4, 5, and 6 in Figure 9.1.**

- Original

```Java
int min(int A, int B)
{
  int minVal;
  minVal = A;
  if (B < A)
  {
    minVal = B;
  }
  return minVal;
}
```

- Mutant 1

```Java
int min(int A, int B)
{
  int minVal;
  minVal = A;
  minVal = B;
  if (B < A)
  {
    minVal = B;
  }
  return minVal;
}
```

Test case: A = 5, B = 6

- Mutant 2

```Java
int min(int A, int B)
{
  int minVal;
  minVal = A;
  if (B > A)
  {
    minVal = B;
  }
  return minVal;
}
```

Test case: A = 5, B = 6

- Mutant 3

```Java
int min(int A, int B)
{
  int minVal;
  minVal = A;
  if (B < minVal)
  {
    minVal = B;
  }
  return minVal;
}
```

- Mutant 4

```Java
int min(int A, int B)
{
  int minVal;
  minVal = A;
  if (B < A)
  {
    minVal = B;
    Bomb();
  }
  return minVal;
}
```

Invalid Mutant.
Test case: A = 6, B = 5

- Mutant 5

```Java
int min(int A, int B)
{
  int minVal;
  minVal = A;
  if (B < A)
  {
    minVal = B;
    minVal = A;
  }
  return minVal;
}
```

Test case: A = 6, B = 5

- Mutant 6

```Java
int min(int A, int B)
{
  int minVal;
  minVal = A;
  if (B < A)
  {
    minVal = B;
    minVal = failOnZero(B);
  }
  return minVal;
}
```

Test case: A = 5, B = 0
