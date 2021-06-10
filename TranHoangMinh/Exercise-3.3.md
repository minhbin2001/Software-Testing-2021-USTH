Exercise 3.3

Develop JUnit tests for the BoundedQueue class. A compilable version is available on the book website in the file BoundedQueue.java. Make sure your tests check every method, but we will not evaluate the quality of your test designs and do not expect you to satisfy any test criteria. Turn in a printout of your JUnit tests and either a printout or a screen shot showing the results of each tests

## enQueue(n) method

```Java
    @Test
    public void testEnQueue() {
    Object a = 1;
    BoundedQueue instance = new BoundedQueue(2);
    instance.enQueue(a);
    
    Assert.assertEquals(instance.toString(), "[1]");
    }
```

## deQueue() method

```Java
   @Test
    public void testDeQueue() {       
        Object a = 4;
        Object b = 5;
        BoundedQueue instance = new BoundedQueue(2);
        instance.enQueue(a);
        instance.enQueue(b);
        instance.deQueue();
        
        Assert.assertEquals(instance.toString(), "[2]");
    }
```

## isEmpty() method

```Java
    @Test
    public void testIsEmpty() {        
        BoundedQueue instance = new BoundedQueue(2);
        assertEquals(instance.isEmpty(), true);
    }
```

## isFull() method

```Java
	@Test
	public void testIsFull() {  
        Object a = 1;
        BoundedQueue instance = new BoundedQueue(2);
        instance.enQueue(a);
        instance.enQueue(a);
        assertEquals(instance.isFull(), true);
    }
```

## toString() method

```Java
    @Test
    public void testToString() {    
        Object a = 3;
        Object b = 4;
        Object c = 5;
        BoundedQueue instance = new BoundedQueue(3);
        instance.enQueue(a);
        instance.enQueue(b);
        instance.enQueue(c);
        Assert.assertEquals(instance.toString(), "[3, 4, 5]");
    }
```
