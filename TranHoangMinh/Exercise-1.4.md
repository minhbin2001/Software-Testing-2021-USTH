Exercise 1.4

a,
```Java
import java.util.Vector;
class Vector_demo {
  public static Vector union(Vector v1, Vector v2)
  {
    Vector v3 = new Vector();
    v3.addAll(v1);
    v3.addAll(v2);
    return v3;
  }
  public static void main(String[] arg)
  {
    Vector v1 = new Vector();
    v1.add(1);
    Vector v2 = new Vector();
    v2.add(2);
    Vector v3 = union(v1, v2);
  }
}
```

b,

Lack of verification statements such as checking `v1` or `v2` is empty or not.

c,

Test case[1]
```Java
Vector v1 = new Vector();
Vector v2 = new Vector();
```

Test case[2]
```Java
Vector v1 = new Vector();
v1.add(2)
Vector v2 = new Vector();
```

Test case[3]
```Java
Vector v1 = new Vector();
Vector v2 = new Vector();
v3.add(2)
```

d,
```Java
public static Vector union(Vector v1, Vector v2, boolean inv = False)
{
  if (v1.isEmpty() && v2.isEmpty()) return Null;
  else
  {
    if (inv)
    {
      Vector v3 = new Vector();
      v3.addAll(v2);
      v3.addAll(v1);
      return v3;
    }
    else
    {
      Vector v3 = new Vector();
      v3.addAll(v1);
      v3.addAll(v2);
      return v3;
    }
  }
}
```
