Ex 1.5
# Program 1

 findLast()
```Java
// findLast()

public static int findLast (int[] x, int y)
   {
      // As the example in the book points out, this loop should end at 0.
      for (int i=x.length-1; i > 0; i--)
      {
         if (x[i] == y)
         {
            return i;
         }
      }
      return -1;
   }
```

a, Explain what is wrong with the given code. Describe the fault precisely by proposing a modification to the code.

The given code intended to return the last index of a value y in an array x. However, the code does not look for the value y in the 0 index of x.  
A modification to the code:
```java
public static int findLast (int[] x, int y)
{ 
  // As the example in the book points out, this loop should end at 0.
   for (int i=x.length-1; i >= 0; i--) // change made here
   {
      if (x[i] == y) 
      {
         return i;
      }
   }
   return -1;
}
```
b, If possible, give a test case that does not execute the fault. If not, briefly explain why not.
Test case:
x = [1,2,3]  
y = 2

c, If possible, give a test case that executes the fault, but does not result in an error state. If not, briefly explain why not.
x = [1,1,1]
y = 1

# Program 2

lastZero
```Java
// lastZero()

public static int lastZero (int[] x)
   {
      for (int i = 0; i < x.length; i++)
      {
         if (x[i] == 0)
         {
            return i;
         }
      }
      return -1;
   }
```

a, Explain what is wrong with the given code. Describe the fault precisely by proposing a modification to the code.
This program intended to return the last index of 0 in an array x. However, it returns the index of the first 0 found.  
A modification to the code:  
```java
public static int lastZero (int[] x)
   {
      for (int i = 0; i < x.length; i++)
      {
         if (x[i] == 0)
         {
            pos0 = i;
         }
      }
      if(pos0 != null){
      	return pos0;
      }
      return -1;
   }
```
b, If possible, give a test case that does not execute the fault. If not, briefly explain why not.
x = [0, 1, 2]


c, If possible, give a test case that executes the fault, but does not result in an error state. If not, briefly explain why not.
x = [0]

# Program 3

countPositive
```Java
// countPositive()

public static int countPositive (int[] x)
   {
      int count = 0;

      for (int i=0; i < x.length; i++)
      {
         if (x[i] >= 0)
         {
            count++;
         }
      }
      return count;
   }
```

a, Explain what is wrong with the given code. Describe the fault precisely by proposing a modification to the code.
This program intended to count positive elements of an array x. However, it also counts 0.  
A modification to the code:  
```java
public static int countPositive (int[] x)
   {
      int count = 0;
   
      for (int i=0; i < x.length; i++)
      {
         if (x[i] > 0)
         {
            count++;
         }
      }
      return count;
   }
```

b, If possible, give a test case that does not execute the fault. If not, briefly explain why not.
x = [-2, 4, -6]

c, If possible, give a test case that executes the fault, but does not result in an error state. If not, briefly explain why not.
Not possible

# Program 4

 oddOrPos
```Java
// oddOrPos()

public static int oddOrPos (int[] x)
   {  // Effects:  if x is null throw NullPointerException
      // else return the number of elements in x that
      //      are either odd or positive (or both)
      int count = 0;

      for (int i = 0; i < x.length; i++)
      {
         if (x[i]%2 == 1 || x[i] > 0)
         {
            count++;
         }
      }
      return count;
   }
```

a, Explain what is wrong with the given code. Describe the fault precisely by proposing a modification to the code.
This program intended to count positive and odd elements of an array x. However, it also counts 0.  
A modification to the code:  
```java
if (x[i] > 0)
{
  count++;
}
else
{
  if (x[i]%2 ==1 ) count++;
}
b, If possible, give a test case that does not execute the fault. If not, briefly explain why not.
x = [1, 2, 3]

c, If possible, give a test case that executes the fault, but does not result in an error state. If not, briefly explain why not.
x = [1, 2, 3]
