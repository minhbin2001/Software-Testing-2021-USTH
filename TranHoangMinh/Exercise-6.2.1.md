Exercise 6.2.1

Write down all 64 tests to satisfy the All Combinations (ACoC) criterion for the second categorization of triang()’s inputs in Table 6.2. Use the values in Table 6.3.

### Code
```java
public enum Triangle {
   SCALENE, ISOSCELES, EQUILATERAL, INVALID
}
public class TriangleType
{
   /**
     * @param s1, s2, s3:  sides of the putative triangle
     * @return enum describing type of triangle
     */
   public static Triangle triangle (int s1, int s2, int s3)
   {
      // Reject non-positive sides
      if (s1 <= 0 || s2 <= 0 || s3 <= 0)
         return (Triangle.INVALID);

      // Check triangle inequality
      if (s1+s2 <= s3 || s2+s3 <= s1 || s1+s3 <= s2)
         return (Triangle.INVALID);

      // Identify equilateral triangles
      if ((s1 == s2) && (s2 == s3))
         return Triangle.EQUILATERAL;

      // Identify isosceles triangles
      if ((s1 == s2) || (s2 == s3) || (s1 == s3))
         return Triangle.ISOSCELES;

      return (Triangle.SCALENE);
   }
}
```
### Two tables
|Partition|b1|b2|b3|b4|
|---|---|---|---|---|
|side1|>1|=1|=0|<0|
|side2|>1|=1|=0|<0|
|side3|>1|=1|=0|<0|

Table: partitioning of `triang()`s inputs (interface-based)

|Partition|b1|b2|b3|b4|
|---|---|---|---|---|
|side1|2|1|0|-1|
|side2|2|1|0|-1|
|side3|2|1|0|-1|

### Test case
```
(2, 2, 2), (2, 2, 1), (2, 2, 0), (2, 2, −1)
(2, 1, 2), (2, 1, 1), (2, 1, 0), (2, 1, −1)
(2, 0, 2), (2, 0, 1), (2, 0, 0), (2, 0, −1)
(2, −1, 2), (2, −1, 1), (2, −1, 0), (2, −1, −1)

(1, 2, 2), (1, 2, 1), (1, 2, 0), (1, 2, −1)
(1, 1, 2), (1, 1, 1), (1, 1, 0), (1, 1, −1)
(1, 0, 2), (1, 0, 1), (1, 0, 0), (1, 0, −1)
(1, −1, 2), (1, −1, 1), (1, −1, 0), (1, −1, −1)

(0, 2, 2), (0, 2, 1), (0, 2, 0), (0, 2, −1)
(0, 1, 2), (0, 1, 1), (0, 1, 0), (0, 1, −1)
(0, 0, 2), (0, 0, 1), (0, 0, 0), (0, 0, −1)
(0, −1, 2), (0, −1, 1), (0, −1, 0), (0, −1, −1)

(−1, 2, 2), (−1, 2, 1), (−1, 2, 0), (−1, 2, −1)
(−1, 1, 2), (−1, 1, 1), (−1, 1, 0), (−1, 1, −1)
(−1, 0, 2), (−1, 0, 1), (−1, 0, 0), (−1, 0, −1)
(−1, −1, 2), (−1, −1, 1), (−1, −1, 0), (−1, −1, −1)
```
