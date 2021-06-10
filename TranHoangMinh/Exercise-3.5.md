Exercise 3.5

The following JUnit test method for the sort() method has a nonsyntactic flaw. Find the flaw and describe it in terms of the RIPR model. Be as precise, specific, and concise as you can. For full credit, you must use the terminology introduced in the book. In the test method, names is an instance of an object that stores strings and has methods add(), sort(), and getFirst(), which do exactly what you would expect from their names. You can assume that the object names has been properly instantiated and the add() and sort() methods have already been tested and work correctly.

```Java
@Test
public void testSort()
{

	names.add("Laura");
	names.add("Han");
	names.add("Alex");
	names.add("Ashley");
	names.sort();
	asserTrue("Sort method", names.getFirst().equals("Alex"));
}

```

This test only examines if the first element is correctly sorted. As for the other 4 elements, the test has no way of finding out if they are in the correct order.

In the RIPR model:

- Reachability: If there is a fault with the first element then it is reached. For the other elements, it is not reached.
- Infection: Yes. The incorrect state can totally happen. 
- Propagation: No. The whole list can be sorted incorrectly but the first element can still be "Alex". The test condition would still be satified and return correct while the infected state is still not dectected.
- Revealability: No. The test assertion cannot reveal the fault.
