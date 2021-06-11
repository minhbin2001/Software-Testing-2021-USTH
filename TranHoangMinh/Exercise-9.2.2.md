Exercise 9.2.2 

 Original

```Java
public static int findVal(int numbers[], int val)       
   {                                                       
      int findVal = -1;                                    

      for (int i=0; i<numbers.length; i++)                 
         if (numbers [i] == val)                         
            findVal = i;                                  
         return (findVal);                                    
   }
```

 Mutant

```Java
public static int findVal(int numbers[], int val)       
   {                                                       
      int findVal = -1;                                    

      for (int i=1; i<numbers.length; i++)                 
         if (numbers [i] == val)                         
            findVal = i;                                  
         return (findVal);                                    
   }
```

### a)

Impossible

### b)

Impossible

### c)

[-1, 1], 1

### d)

[1, 0], 1
