Exercise 3.10

Replace each occurrence of a set with a list in the JUnit theory removeThenAddDoesNotChangeSet. Is the resulting theory valid or invalid? How many of the tests that pass the precondition also pass the postcondition? Explain

The resulting theory is not valid because order matters in lists. When we remove then add an element back, its position in the list could have been changed and therefore, the list is different.

The the three test cases, only one can pass the test.

Conclusion: The JUnit theory fails.

```Java

import org.junit.*;
import org.junit.runner.RunWith;
import static org.junit.Assert.*;
import static org.junit.Assume.*;

import org.junit.experimental.theories.DataPoint;
import org.junit.experimental.theories.DataPoints;
import org.junit.experimental.theories.Theories;
import org.junit.experimental.theories.Theory;

import java.util.*;

@RunWith (Theories.class)
public class ListTheoryTest
{
   @DataPoints
   public static String[] string = {"huong", "long", "huy", "minh"};

   @DataPoints
   public static List[] lists = {
      Arrays.asList ("huong", "long", "huy"),
      Arrays.asList ("huy", "minh", "dinh anh"),
      Arrays.asList ("dinh anh")
   };


   @Theory
   public void removeThenAddDoesNotChangeList
                   (List<String> list, String string)  // Parameters!
   {
      assumeTrue (list != null);            // Assume
      assumeTrue (list.contains (string));  // Assume
      List<String> copy = new ArrayList<String>(list);   // Act
      copy.remove (string);                       
      copy.add (string);
      assertTrue (list.equals (copy));      // Assert
    }
}
```
