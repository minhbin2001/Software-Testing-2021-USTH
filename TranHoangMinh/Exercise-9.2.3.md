Exercise 9.2.3

Answer questions (a) through (d) for the mutant on line 6 in the method sum().<br>

(a) If possible, find test inputs that do not reach the mutant.<br>

(b) If possible, find test inputs that satisfy reachability but not infection for the mutant.<br>

(c) If possible, find test inputs that satisfy infection, but not propagation for the mutant.<br>

(d) If possible, find test inputs that strongly kill the mutants.<br>

## Original

```Java
public static int sum(int[] x)
   {
      int s = 0;
      for (int i=0; i < x.length; i++)
      {
         s = s + x[i];
      }
      return s;
   }
```

## Mutant

```Java
public static int sum(int[] x)
   {
      int s = 0;
      for (int i=0; i < x.length; i++)
      {
         s = s - x[i];
      }
      return s;
   }
```

### a)

Impossible

### b)

Impossible

### c)

All zeros

### d)

All ones
