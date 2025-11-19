Question 1

What is the C++11 meaning of the term &&?

In C++11, && denotes an rvalue reference, which enables move semantics.



Question 2

What is the C++11 meaning of the term nullptr?

nullptr is a type-safe null pointer constant, replacing the old NULL macro.



Question 3

What is the C++11 meaning of the term auto?

The auto keyword lets the compiler deduce the variable’s type automatically.




Question 4

What is the C++11 meaning of the term explicit?

The explicit keyword prevents implicit (automatic) conversions or copy initialization.




Question 5

What is the C++11 meaning of the term noexcept?

noexcept specifies that a function does not throw exceptions.




Question 6

The header <future> in C++11 is used for:

<future> supports asynchronous operations, including std::async, std::promise, and std::future.




Question 7

L. Euler invented:

Leonhard Euler is credited with founding graph theory, starting with the Königsberg bridge problem.




Question 8

D. Knuth analyzed or invented:

Donald Knuth helped analyze and develop the alpha-beta pruning algorithm for search trees.




Question 9

A new keyword in C++11 is:

nullptr was introduced in C++11 as a new keyword for null pointer constants.




Question 10

A try block in C++:

try { ... } catch(...) { ... } handles exceptions.




Question 11

C++11 STL:

C++11 introduced unordered_map and unordered_set, which are hash-based containers.





Question 12

HEX as a graph has its internal nodes:

In the Hex board game, each internal cell (hexagon) touches 6 neighbors — hence degree 6.




Question 13

True or False: When you rethrow an exception, its type and value is convertible to int.

Rethrowing preserves the original exception type, not int.




Question 14

True or False: Overloaded operators are always defined using static functions.

Operator overloads are usually non-static member or non-member functions.




Question 15

True or False: All exceptions in C++ have as their base type std::exception.

You can throw any type (even an int or std::string), not just classes derived from std::exception.




Question 16

True or False: Writeln is a new keyword in C++11.

writeln does not exist in C++; it’s from Pascal, not C++.




Question 17

True or False: In f(1) || (!g(2)), f(1) will always be evaluated before g(2) (which may not get evaluated).

|| uses short-circuit evaluation — f(1) runs first; if it’s true, g(2) is skipped.





Question 18

Using alpha-beta, can any LEAF nodes not be evaluated in the above tree?

Alpha-beta pruning skips some leaf evaluations when they can’t affect the final minimax decision.




Question 19

When using =0 as the body of a function you are:

= 0 marks a pure virtual function, making the class abstract.




Question 20

The catch signature ... means:

catch(...) is a catch-all handler that matches any exception type.





Question 21

Code:

list<int> data = {0, 2, 5, 7, 9};
auto foobar = data.begin();
for (; foobar != data.end(); )
    if (*foobar % 2 == 1)
        foobar = data.erase(foobar);
    else
        ++foobar;

Step 1: What is the type of foobar?

data.begin() returns a bidirectional iterator of the same type as the container.

Here the container is std::list<int>.

So:

auto foobar = data.begin();


means

std::list<int>::iterator foobar;


==> Answer 21: list<int>::iterator






Question 22
Step 2: What does the loop do?

The code removes all odd numbers from the list.

Let’s trace it:

data = {0, 2, 5, 7, 9}

Loop removes items where *foobar % 2 == 1 (odd).

0 → even → keep

2 → even → keep

5 → odd → erase

7 → odd → erase

9 → odd → erase

Remaining elements: {0, 2}

Answer 22: Having 2 elements







Let's carefully analyze your Minimax / Alpha-Beta tree step by step.

Given tree structure
                      Max
                     /   \
                 Min       Min
                /   \     /   \
              Max   Max  Max  Max
             / \   / \  / \   / \
           15  6  7 13  3  5 24  8


Leaf Nodes: 15, 6, 7, 13, 3, 5, 24, 8

Question 23

The four Max values on the ply above the leaf nodes (from left to right).

These are the immediate parents of the leaf nodes.

Each “Max” node selects the maximum of its two leaf children:

Max(15, 6) → 15

Max(7, 13) → 13

Max(3, 5) → 5

Max(24, 8) → 24

Answer 23:

15 13 5 24





Question 24

The two Min values on the second ply (from left to right).

Each “Min” node selects the minimum of its two Max children (from Q23):

Min(15, 13) → 13

Min(5, 24) → 5

Answer 24:

13 5






Question 25

Max value for the root of the tree.

Root = Max of its two Min children (from Q24):

Max(13, 5) → 13

Answer 25:

13





Question 26

Leaf node(s) that need not be evaluated with alpha-beta pruning.

Alpha-beta pruning allows us to skip evaluation when a branch cannot improve the current best value.

Trace left to right, top-down:

Left Min subtree

Left Max: Max(15, 6) → 15

Right Max: Max(7, 13) → 13

Min(15, 13) → 13 → both leaves evaluated. Nothing skipped.

Right Min subtree

Left Max: Max(3, 5) → 5

Right Max: Max(24, 8) → 24

Min(5, 24) → 5

During evaluation of Right Max(24, 8):

Min parent already knows 5 from Left Max.

Max(24, …) ≥ 24 → Min(…, 24) ≥ 5 → cannot improve, but careful: here alpha-beta skips the 8 because after checking 24, Min already knows 5 is smaller, so 8 does not need evaluation.

Answer 26:

8


(The other skipped leaf could have been 24 if evaluation order were reversed, but 8 is one valid answer.)







Given code (completed properly):
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    int data[5] = {1, 7, 46, 9, 6};
    vector<int> data_vec(data, data + 5);
    int modulus = 3;

    // use of lambdas for predicates in find_if
    auto q = find_if(data_vec.begin(), data_vec.end(),
                     [modulus](int x) { return x % modulus == 0; });
    cout << "first *q = " << *q << endl;

    q = find_if(++q, data_vec.end(),
                [modulus](int x) { return x % modulus == 0; });
    cout << "second *q = " << *q << endl;
}

Step-by-step explanation

data_vec = {1, 7, 46, 9, 6}
modulus = 3

We are looking for numbers that are divisible by 3 (x % 3 == 0).

First find_if:

Check each number:

1 % 3 = 1 → no

7 % 3 = 1 → no

46 % 3 = 1 → no

9 % 3 = 0 → match!

So the first find_if stops at 9.

Answer 27: *q = 9

Second find_if:

Starts from after the first q (++q), i.e., after 9.

Remaining elements: {6}

Check:

6 % 3 = 0 → match!

Answer 28: *q = 6






Question 27

Predicate: i % modulus == 0, where modulus = 3

Check each element of data_vec = {1, 7, 46, 9, 6}:

1 % 3 = 1 → no

7 % 3 = 1 → no

46 % 3 = 1 → no

9 % 3 = 0 → yes!

Answer 27:

9

Question 28

Predicate: i % modulus == 1, modulus = 3

Check data_vec = {1, 7, 46, 9, 6}:

1 % 3 = 1 → yes!

Answer 28:

1


Previous mistake: swapped or misread the % values.





Full Code
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main()
{
    vector<int> data(5, 1);
    int sum {0};

    cout << sum << endl;   // (Q29)

    for (auto element : data)    // (Q30–?)
    {
        sum += element;
        cout << sum << endl;
    }

    for (auto p = ++data.begin(); p != --data.end(); ++p)
    {
        sum += *p;
        cout << sum << endl;
    }

    sum = 0;
    data.push_back(2);
    data.push_back(3);

    for (auto element : data)
    {
        sum += element;
        cout << sum << endl;
    }

    cout << accumulate(data.begin(), data.end(), data[0]) << endl;
}

Step-by-step trace
Initial data

data = {1, 1, 1, 1, 1}
sum = 0

Line 1
cout << sum << endl;


→ prints 0

Q29 → 0

First for-loop
for (auto element : data)


Each element = 1
(sum starts at 0)

Iteration	element	sum after add	Printed
1	1	1	1
2	1	2	2
3	1	3	3
4	1	4	4
5	1	5	5

After loop → sum = 5

Lines printed: 1, 2, 3, 4, 5

Second for-loop
for (auto p = ++data.begin(); p != --data.end(); ++p)


data.begin() → first element
++data.begin() → points to second element
--data.end() → points to second-to-last element
So we iterate over the middle 3 elements (2nd, 3rd, 4th).

All are 1’s.
Current sum = 5

Iteration	*p	sum after add	Printed
1	1	6	6
2	1	7	7
3	1	8	8

After loop → sum = 8

Lines printed: 6, 7, 8

Reset & Extend
sum = 0;
data.push_back(2);
data.push_back(3);


data now = {1, 1, 1, 1, 1, 2, 3}
sum = 0

Third for-loop

Adds all elements again.

Iteration	element	sum after add	Printed
1	1	1	1
2	1	2	2
3	1	3	3
4	1	4	4
5	1	5	5
6	2	7	7
7	3	10	10

Lines printed: 1, 2, 3, 4, 5, 7, 10

Final line
cout << accumulate(data.begin(), data.end(), data[0]) << endl;


data[0] = 1
sum of data = 1+1+1+1+1+2+3 = 10
Accumulate starts at 1 → 1 + 10 = 11

Final line: 11

Summary of outputs (in order)
0          ← Q29
1
2
3
4
5
6
7
8
1
2
3
4
5
7
10
11

Question	What it prints	Explanation
29	0	initial value of sum
31	2	second addition in first loop
32	3	third addition in first loop
33	4	fourth addition in first loop
34	5	fifth addition in first loop







Code 
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void speak() = 0; 
    virtual void purr() { cout << "Purr\n"; } 
};

class Cat : public Animal {
public:
    void speak() override { 
        cout << "Meow\n"; 
        purr(); 
    }
};

class Lion : public Cat {
public:
    void speak() override { cout << "ROAR\n"; } 
    void purr() override { cout << "ROAR\n"; }  
};

int main() {
    Animal* c = new Cat(); 
    Cat napster;
    Lion googly;

    c->speak();        
    napster.speak();   
    googly.speak();    

    return 0;
}

🔍 Step-by-step Execution
1️⃣ c->speak();

c is an Animal* pointing to a Cat object.

Calls Cat::speak() (virtual dispatch).

Cat::speak() prints:

Meow


and then calls purr().

Since purr() is not overridden in Cat, it calls Animal::purr(), printing:

Purr


🖨️ Output:

Meow
Purr


That’s two lines printed here.

2️⃣ napster.speak();

napster is a Cat object.

Same as before — calls Cat::speak().

🖨️ Output:

Meow
Purr


Another two lines printed.

3️⃣ googly.speak();

googly is a Lion object.

Lion overrides speak(), so this calls Lion::speak().

🖨️ Output:

ROAR


Total Printed Lines (in order)

1️⃣ Meow
2️⃣ Purr
3️⃣ Meow
4️⃣ Purr
5️⃣ ROAR


Question	Printed Text	Explanation
35	Meow	from c->speak()
36	Purr	from c->purr()
37	Meow	from napster.speak()
38	Purr	from napster.purr()
39	ROAR	from googly.speak() (Lion override)





Question 40

The safest cast in C++ is considered:

static_cast performs type-checked conversions at compile time and is safer than C-style (type) casts or reinterpret_cast.

reinterpret_cast can produce unsafe, low-level conversions, and (void*) is from old C-style casting.




Question 41

The MST for an undirected connected graph of N nodes where all weights are cost C has:
A value of (N − 1) × C

A Minimum Spanning Tree (MST) connects all N nodes with exactly N − 1 edges.

If each edge costs C, the total MST cost is (N − 1) × C.



Question 42

True or false? Overloaded operators are always defined using static functions.

Operator overloads are usually non-static member functions or non-member functions.

For example:

Complex operator+(const Complex& rhs) const;  // non-static member




