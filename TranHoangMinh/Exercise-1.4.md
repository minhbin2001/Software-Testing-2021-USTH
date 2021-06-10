xercise 1.4

The following exercise is intended to encourage you to think of testing in a more rigorous way than you may be used to. The exercisealso hints at the strong relationship between specification clarity, faults, and test cases

(a) Write a Java method with the signature public static Vector union (Vector a, Vector b) The method should return a Vector of objects that are in either of the two argument Vectors.

(b) Upon reflection, you may discover a variety of defects and ambiguities in the given assignment. In other words, ample opportunities for faults exist. Describe as many possible faults as you can. (Note: Vector is a Java Collection class. If you are using another language, interpret Vector as a list.)

(c) Create a set of test cases that you think would have a reasonable chance of revealing the faults you identified above. Document a rationale for each test in your test set. If possible, characterize all of your rationales in some concise summary. Run your tests against your implementation.

(d) Rewrite the method signature to be precise enough to clarify the defects and ambiguities identified earlier. You might wish to illustrate your specification with examples drawn from your test cases.
a,

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
b,

Lack of verification statements such as checking v1 or v2 is empty or not.

c,

Test case[1]

Vector v1 = new Vector();
Vector v2 = new Vector();
Test case[2]

Vector v1 = new Vector();
v1.add(2)
Vector v2 = new Vector();
Test case[3]

Vector v1 = new Vector();
Vector v2 = new Vector();
v3.add(2)
d,

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
