Exercise 6.4.1

The restriction on interleaving next() and remove() calls is quite complex. The JUnit tests in IteratorTest.java only devote onetest for this situation, which may not be enough. Refine the input domain model with one or more additional characteristics to probe this behavior, and implement these tests in JUnit.


Firstly, we must determine the characteristics to generate test cases, each of which is paritioned by a boolean. They include:

- C1: iterator has more values 
- C2: iterator returns a non-null object reference 
- C3: remove() is supported
- C4: remove() precondition is satisfied
- C5: collection in consistent state while iterator in use 

After that, the condition for the tests is set up.

```Java
import static org.junit.Assert.*;
import org.junit.*;
import java.util.*;

public class IteratorTest {
	
   private List<String> list;      
   private Iterator<String> itr;   

   @Before public void setUp()  
   {
      list = new ArrayList<String>();
      list.add ("cat");
      list.add ("dog");
      itr = list.iterator();
   }
   
```

## Tests for the remove() method
  
The remove() method is tested using the "Base Choice" criterion. All 5 characteristics above are associated with the remove() method and each characteristic is removed while keeping the other 4. Warning: in the second test case where C1 is False, C2 also has to be False because if the iterator does not have anymore value, the return value has to be null.
   
```Java
   // C1-T, C2-T, C3-T, C4-T, C5-T
   @Test public void testRemove_BaseCase()
   {
      itr.next();
      itr.remove();
      assertFalse (list.contains ("cat"));
   }
   
   // C1-F, C2-F, C3-T, C4-T, C5-T
   @Test public void testRemove_C1()
   {
      itr.next(); itr.next();        // consume the cat and the dog
      itr.remove();                  // remove dog from list.
      assertFalse (list.contains ("dog"));
   }
   
   // C1-T, C2-F, C3-T, C4-T, C5-T
   @Test public void testRemove_C2()
   {
      list.add (null);
      list.add ("elephant");
      itr = list.iterator();
      itr.next(); itr.next();        // consume the cat and the dog
      itr.next();        // consume null; iterator not empty
      itr.remove();      // remove null from list
      assertFalse (list.contains (null));
   }
   
   // C1-T, C2-T, C3-F, C4-T, C5-T
   @Test(expected=UnsupportedOperationException.class)
   public void testRemove_C3()
   {
      list = Collections.unmodifiableList (list);
      itr = list.iterator();
      itr.next();   // consume first element to make C4 true
      itr.remove();
   }
   
   // C1-T, C2-T, C3-T, C4-F, C5-T
   @Test (expected=IllegalStateException.class)
   public void testRemove_C4()
   {
      itr.remove();
   }
      
      
   // C1-T, C2-T, C3-T, C4-T, C5-F
   @Test (expected=ConcurrentModificationException.class)
   public void testRemove_C5()
   {
      itr.next();
      list.add ("elephant");
      itr.remove();
   }

```

## Tests for the next() method

Since this is only for the next() method, C3 and C4 characteristics are not associated. Warning: in the second test case where C1 is removed, C2 is also not satisfied since the next value must be null. In the last test case where the iterator is changed while in use, C2 is not satisfied because there are inconsistencies.

```Java

   // C1-T, C2-T, C5-T
   @Test public void testNext_BaseCase()
   {
      assertEquals ("cat", itr.next());
   }
   
   // C1-F, C2-F, C5-T
   @Test(expected=NoSuchElementException.class)
   public void testNext_C1()
   {
      itr.next(); itr.next();        // consume the cat and the dog
      itr.next();                    // now empty
   }
   
   // C1-T, C2-F, C5-T
   @Test public void testNext_C2()
   {
      list = new ArrayList<String>();
      list.add (null);
      itr = list.iterator();
      assertNull (itr.next());
   }
   
   // C1-T, C2-F, C5-F
   @Test(expected=ConcurrentModificationException.class)
   public void testNext_C5()  
   {
      list.add ("elephant");
      itr.next();      
   }
   
```
