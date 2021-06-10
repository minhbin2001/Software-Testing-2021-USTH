Ex7.2.2.5

Answer questions a–g for the graph defined by the following sets:
N = {1, 2, 3, 4, 5, 6, 7}
N0 = {1}
Nf = {7}
E = {(1, 2), (1, 7), (2, 3), (2, 4), (3, 2), (4, 5), (4, 6), (5, 6), (6, 1)}
Also consider the following (candidate) test paths:
p1 = [1, 2, 4, 5, 6, 1, 7]
p2 = [1, 2, 3, 2, 4, 6, 1, 7]
p3 = [1, 2, 3, 2, 4, 5, 6, 1, 7]
(a) Draw the graph.
(b) List the test requirements for Edge-Pair Coverage. (Hint: You should get 12 requirements of length 2.)
(c) Does the given set of test paths satisfy Edge-Pair Coverage? If not, state what is missing.
(d) Consider the simple path [3, 2, 4, 5, 6] and test path [1, 2, 3, 2, 4, 6, 1, 2, 4, 5, 6, 1, 7]. Does the test path tour the simple path directly? With a sidetrip? If so, write down the sidetrip.
(e) List the test requirements for Node Coverage, Edge Coverage, and Prime Path Coverage on the graph.
(f) List test paths from the given set that achieve Node Coverage but not Edge Coverage on the graph.
(g) List test paths from the given set that achieve Edge Coverage but not Prime Path Coverage on the graph

### a)

[The link of the graph](https://cs.gmu.edu:8443/offutt/coverage/GraphCoverage?edges=1+2%0D%0A1+7%0D%0A2+3%0D%0A2+4%0D%0A3+2%0D%0A4+5%0D%0A4+6%0D%0A5+6%0D%0A6+1%0D%0A&initialNode=1&endNode=7&action=Nodes)

### b)

|Test Paths|	Test Requirements that are toured by test paths directly|
|---|---|
|[1,2,4,6,1,7]|	[1,2,4], [1,7], [2,4,6], [4,6,1], [6,1,7]|
|[1,2,4,5,6,1,7]|	[1,2,4], [1,7], [2,4,5], [4,5,6], [5,6,1], [6,1,7]|
|[1,2,3,2,3,2,4,6,1,7]|	[1,2,3], [1,7], [2,3,2], [2,4,6], [3,2,3], [3,2,4], [4,6,1], [6,1,7]|
|[1,2,4,6,1,2,4,6,1,7]|	[1,2,4], [1,7], [2,4,6], [4,6,1], [6,1,2], [6,1,7]|

### c)

From the b), p3 does NOT satisfy Edge-Pair Coverage.

### d)

No

With a sidetrip: [6, 1, 2, 4, 5, 6]

### e)

TR node coverage: [1] [2] [7] [3] [4] [5] [6]

TR edge coverage: [1,2] [1,7] [2,3] [2,4] [3,2] [4,5] [4,6] [5,6] [6,1]

TR prime paths: [3,2,4,5,6,1,7] [2,4,5,6,1,2] [1,2,4,5,6,1] [3,2,4,6,1,7] [5,6,1,2,4,5] [6,1,2,4,5,6] [4,5,6,1,2,4] [4,5,6,1,2,3] [2,4,6,1,2] [1,2,4,6,1] [6,1,2,4,6] [4,6,1,2,3] [4,6,1,2,4] [3,2,3] [2,3,2]

### f)

Not possible

[1,2,3,2,4,6,1,7]
[1,2,4,5,6,1,7]

### g)

Not possible

[1,2,3,2,4,6,1,7]
[1,2,4,5,6,1,7]
