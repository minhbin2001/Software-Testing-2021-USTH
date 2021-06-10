Exercise 5.1

Suppose that coverage criterion C1 subsumes coverage criterion C2. Further suppose that test set T1 satisfies C1 on program P, and test set T2 satisfies C2, also on P. (a) Does T1 necessarily satisfy C2? Explain. (b) Does T2 necessarily satisfy C1? Explain. (c) If P contains a fault, and T2 reveals the fault, T1 does not necessarily also reveal the fault. Explain.

a)

Yes, T1 necessarily satisfy C2 because of pure definition of Criterion Subsumption.
Criterion Subsumption: A test criterion C1 subsumes C2 if and only if every set of test cases that satisfies criterion C1 also satisfies C2.

b)

No because the task did NOT mention that C2 subsumes C1.
c)

T2 can have different/special test case from T1. Therefore, that different/special one reveal the fault, despite the fact that it (test case) must satisfy criterion.
