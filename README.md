### Welcome to the complete DSA guide by Mihraz Hossain (for batch 2023)
If you can finish this, I would like to congratulate you cause you will be ready to take the exam!

SO Best wishes and we will be **starting with:**

# 📘 LECTURE 2 — Math Foundations (Sets, Relations, Recursion)

👉 **Reality check:**
This lecture is **easy marks**. No proofs in exam. Mostly definitions + logic.

## 1️⃣ SETS (VERY IMPORTANT)

### What is a set?

A **set** is a collection of **distinct** elements.

Examples:

* `{1, 2, 3}`
* `{apple, pear}`
* `{(1,2), (3,4)}`

📌 **Order does NOT matter**
`{1,2,3} = {3,2,1}`


### Membership symbol (∈)

* `x ∈ A` → x is an element of A
* `x ∉ A` → x is NOT an element of A

Example:

* `2 ∈ {1,2,3}` ✅
* `5 ∉ {1,2,3}` ❌


### Subset (⊆) ⭐ EXAM FAVORITE

A is a subset of B if **every element of A is in B**

Example:

* `{1,2} ⊆ {1,2,3}` ✅
* `{1,4} ⊆ {1,2,3}` ❌

### Proper Subset (⊂)

* A ⊂ B means:

  * A ⊆ B **and**
  * A ≠ B

Example:

* `{1,2} ⊂ {1,2,3}` ✅
* `{1,2,3} ⊂ {1,2,3}` ❌


## 2️⃣ VERY IMPORTANT DIFFERENCE: ∈ vs ⊆

This **will** be tested.

Let:

* `A = {1,2}`

| Statement | True/False |
|  | - |
| `1 ∈ A`   | ✅          |
| `{1} ⊆ A` | ✅          |
| `1 ⊆ A`   | ❌          |
| `{1} ∈ A` | ❌          |

👉 **Rule to remember**:

* `∈` → element
* `⊆` → set


## 3️⃣ EMPTY SET (∅)

* Empty set has **no elements**
* `{}` or `∅`

Important facts:

* `∅ ⊆ A` → ALWAYS true
* `∅ ∈ A` → usually false (unless A contains ∅)


## 4️⃣ POWER SET P(S) ⭐⭐⭐

### Definition:

Power set = **set of all subsets**

If:

* `S = {1,2}`

Then:

```
P(S) = { ∅, {1}, {2}, {1,2} }
```

### GOLDEN RULE (MEMORIZE):

If a set has **n elements**,
👉 **Power set has `2^n` elements**

Example:

* `{1,2,3}` → `2³ = 8` subsets



## 5️⃣ RELATIONS & FUNCTIONS (LIGHT EXAM WEIGHT)

### Relation:

A relation is a **set of ordered pairs**

Example:

```
R = {(1,2), (2,3)}
```

No heavy theory required.



### Function:

A function maps **each input to exactly ONE output**

Example:

```
f(x) = x + 1
```


## 6️⃣ RECURSION (NO PROOFS)

### What is recursion?

A function that **calls itself**

Example:

```
Factorial(n):
if n == 0 return 1
else return n * factorial(n-1)
```

### What exam may ask:

* Trace recursion
* Count calls
* Understand base case


## 📝 EXAM-STYLE QUESTIONS (FROM THIS LECTURE)

1. Is `{1,2} ⊆ {1,2,3}`? Explain.
2. How many subsets does `{a,b,c}` have?
3. Is `{1}` ∈ `{1,2,3}`?
4. What is the difference between ∈ and ⊆?
5. Write the power set of `{1,2}`.



## ✅ QUICK SELF-CHECK (ANSWER IN YOUR HEAD)

* Is `∅ ⊆ {1,2}`? → YES
* Is `{1} ∈ {1,2}`? → NO
* Power set size of `{a,b,c,d}`? → 16


# 📘 LECTURE 3 — Algorithm Analysis (Big-O, Time Complexity)

👉 **Why this lecture matters**

* Comes in **theory questions**
* Comes in **coding questions**
* Comes in **project explanations**
* Easy marks if you know the patterns

## 1️⃣ Why do we analyze algorithms?

### Core idea (exam sentence)

> Algorithm analysis estimates how an algorithm’s **time or memory usage grows as input size increases**, independent of machine or language.

We care about:

* **Time complexity**
* **Space complexity**

In CS311, **time complexity is more important**.



## 2️⃣ Input size (n)

* `n` = number of elements
* Could be:

  * array size
  * number of nodes
  * number of inputs

📌 **Almost every formula uses n**



## 3️⃣ What is Big-O notation? ⭐⭐⭐

### Big-O = **upper bound**

It tells us the **worst-case growth rate**.

👉 Exam sentence:

> Big-O describes the maximum running time of an algorithm as input size grows.



### The three notations (know names + meaning)

| Notation    | Meaning                    |
| -- | -- |
| **O(f(n))** | Upper bound (worst case)   |
| **Θ(f(n))** | Tight bound (exact growth) |
| **Ω(f(n))** | Lower bound (best case)    |

📌 If confused → **Big-O is the most important**



## 4️⃣ Growth rates (MEMORIZE THIS TABLE)

| Name         | Complexity |
|  | - |
| Constant     | O(1)       |
| Logarithmic  | O(log n)   |
| Linear       | O(n)       |
| Linearithmic | O(n log n) |
| Quadratic    | O(n²)      |
| Cubic        | O(n³)      |
| Exponential  | O(2ⁿ)      |

👉 **Order from fastest to slowest**:

```
O(1) < O(log n) < O(n) < O(n log n) < O(n²) < O(2ⁿ)
```



## 5️⃣ How to find Big-O of code (EXAM CORE)

### Rule 1: Ignore constants

```
O(2n + 5) → O(n)
```



### Rule 2: Ignore smaller terms

```
O(n² + n) → O(n²)
```



### Rule 3: Loops

#### Single loop

```c
for(i = 0; i < n; i++)
```

➡ **O(n)**



#### Nested loops

```c
for(i = 0; i < n; i++)
  for(j = 0; j < n; j++)
```

➡ **O(n²)**



#### Nested but dependent

```c
for(i = 0; i < n; i++)
  for(j = 0; j < i; j++)
```

➡ still **O(n²)**



## 6️⃣ Logarithmic time ⭐ VERY IMPORTANT

### Binary Search

* Each step halves input
* Number of steps ≈ log₂(n)

👉 **O(log n)**

Example:

```
n = 16 → 4 steps
n = 32 → 5 steps
```

📌 Exam sentence:

> Binary search is faster than linear search because it reduces the search space by half each step.



## 7️⃣ Recursive algorithms

### Example: Factorial

```
T(n) = T(n-1) + c
```

➡ **O(n)**



### Fibonacci (naive recursion)

```
F(n) = F(n-1) + F(n-2)
```

➡ **O(2ⁿ)** ❌ slow

👉 Why?

* Repeated calculations
* Overlapping subproblems

(This connects to **Lecture 12 – Dynamic Programming**)



## 8️⃣ Typical exam Big-O questions (VERY LIKELY)

### Example 1

```c
for(i = 0; i < n; i++)
  printf("Hello");
```

✔ **O(n)**



### Example 2

```c
for(i = 0; i < n; i++)
  for(j = 0; j < n; j++)
    printf("Hello");
```

✔ **O(n²)**



### Example 3

```c
while(n > 1)
  n = n / 2;
```

✔ **O(log n)**



### Example 4

```c
for(i = 0; i < n; i++)
  for(j = 0; j < i; j++)
    for(k = 0; k < 10; k++)
```

✔ **O(n²)**
(10 is constant → ignored)



## 9️⃣ Why faster algorithms matter (THEORY QUESTION)

Example:

* Linear search → O(n)
* Binary search → O(log n)

For large n:

* O(log n) is **much faster**
* That’s why sorting + binary search is useful



## 📝 EXAM-STYLE QUESTIONS FROM THIS LECTURE

1. Define Big-O notation.
2. Find time complexity of a given code.
3. Why binary search is faster than linear search?
4. What is the time complexity of merge sort?
5. Why naive Fibonacci recursion is inefficient?



## ✅ QUICK SELF-CHECK (IMPORTANT)

Answer in your head:

* Single loop → ?
* Nested loop → ?
* Binary search → ?
* Ignore constants? (Yes/No)
* O(n² + n)? → ?

Answers:

> O(n), O(n²), O(log n), Yes, O(n²)


# 📘 LECTURE 4 — Lists & Abstract Data Types (ADT)

👉 **Big idea**
Lecture 4 teaches you **how data is organized** and **why ADTs matter**.



## 1️⃣ What is a Data Structure?

### Simple definition (exam sentence):

> A data structure is a way to store and organize data so that it can be used efficiently.

Examples:

* Array
* List
* Stack
* Queue
* Tree



## 2️⃣ Abstract Data Type (ADT) ⭐⭐⭐

### Definition (VERY IMPORTANT):

> An ADT defines **what operations can be performed**, not **how they are implemented**.

📌 Think of it like a **remote control**:

* You know what buttons do
* You don’t care how TV works internally



### Why ADT is useful?

* Hides implementation details
* Easier to change implementation later
* Reduces program complexity

👉 **Exam question**:
“Why ADT is important in software design?”



## 3️⃣ What is a List?

### Definition:

> A list is a **finite ordered sequence** of elements.

Example:

```
<10, 20, 30, 40>
```

Important:

* Order **matters**
* Each element has a **position**



## 4️⃣ Basic List Operations (MEMORIZE)

Common operations:

* Create
* Insert
* Delete
* Find/Search
* Get length
* Traverse (move next / previous)

👉 These operations are the **list ADT interface**



## 5️⃣ Two Types of List Implementations ⭐⭐⭐

### 1. Array-Based List

Stored in **continuous memory**

#### Advantages:

* Fast access by index → **O(1)**
* Simple

#### Disadvantages:

* Fixed size
* Insert/delete in middle → **O(n)**



### 2. Linked List

Stored as **nodes connected by pointers**

Each node:

```
[data | next]
```

#### Advantages:

* Dynamic size
* Insert/delete → **O(1)** (if position known)

#### Disadvantages:

* Slow access → **O(n)**
* Extra memory for pointers



## 6️⃣ Array vs Linked List (VERY IMPORTANT TABLE)

| Feature       | Array List | Linked List    |
| - | - | -- |
| Memory        | Contiguous | Non-contiguous |
| Access        | O(1)       | O(n)           |
| Insert/Delete | O(n)       | O(1)           |
| Size          | Fixed      | Dynamic        |
| Extra Memory  | No         | Yes (pointers) |

👉 **Exam loves comparison questions**



## 7️⃣ When to use which?

### Use Array List when:

* Frequent access
* Size known
* Few insertions

### Use Linked List when:

* Frequent insert/delete
* Size changes
* Order matters but random access doesn’t



## 8️⃣ Traversing a List

Example (pseudo):

```c
for (moveToStart; currPos < length; next)
  process(currentElement)
```

👉 Time complexity: **O(n)**



## 9️⃣ Typical Exam Questions (Lecture 4)

1. What is an ADT?
2. Difference between list and array?
3. Compare array-based list and linked list.
4. What operations does a list ADT support?
5. Why linked list insertion is faster?



## ✅ QUICK SELF-CHECK

Answer quickly:

* Does list allow duplicates? → YES
* Does order matter? → YES
* Random access in linked list? → NO
* Insert in array list cost? → O(n)


# 📘 LECTURE 5 — Stacks & Queues

👉 **Big idea**
Stacks and Queues are **restricted lists** — fewer operations, easier logic, very useful.


## 1️⃣ STACK ⭐⭐⭐ (VERY IMPORTANT)

### Definition (EXAM SENTENCE)

> A stack is a linear data structure where insertion and deletion occur only at one end called the **top**.

### Rule:

**LIFO — Last In, First Out**



## 2️⃣ Stack Operations (MEMORIZE)

| Operation  | Meaning         |
| - |  |
| PUSH       | Insert element  |
| POP        | Remove element  |
| TOP / PEEK | See top element |
| isEmpty    | Check empty     |

Example:

```
PUSH 10
PUSH 20
PUSH 30
POP → 30
```



## 3️⃣ Stack Implementation

### Using Array

* Simple
* Fixed size
* Possible overflow

### Using Linked List

* Dynamic
* No overflow (until memory ends)

👉 **Exam question**:
“Implement stack using array or linked list (conceptually)”



## 4️⃣ Stack Applications ⭐⭐⭐ (EXAM FAVORITE)

### 1. Function calls (Recursion)

* Each function call is pushed onto stack
* Return pops it



### 2. Expression evaluation

* Infix → Postfix
* Postfix evaluation



### 3. Bracket Matching ⭐⭐⭐ (VERY LIKELY)

Example:

```
{ [ ( ) ] }
```

Algorithm (memorize):

1. Create empty stack
2. Read characters one by one
3. If opening bracket → PUSH
4. If closing bracket → POP and match
5. Stack empty at end → Balanced

👉 **Coding question possible**



## 5️⃣ QUEUE ⭐⭐⭐

### Definition (EXAM SENTENCE)

> A queue is a linear data structure where insertion occurs at the **rear** and deletion occurs at the **front**.

### Rule:

**FIFO — First In, First Out**



## 6️⃣ Queue Operations

| Operation | Meaning       |
|  | - |
| Enqueue   | Insert        |
| Dequeue   | Remove        |
| Front     | First element |
| Rear      | Last element  |

Example:

```
Enqueue 10
Enqueue 20
Dequeue → 10
```



## 7️⃣ Queue Implementation

### Array Queue

* Simple
* Wasted space issue

### Circular Queue ⭐

* Rear wraps around
* Efficient memory usage



### Linked List Queue

* Dynamic
* Efficient enqueue/dequeue



## 8️⃣ Queue Applications

* CPU scheduling
* Printer queue
* BFS traversal (Graphs — later)



## 9️⃣ Stack vs Queue (VERY IMPORTANT)

| Feature    | Stack   | Queue    |
| - | - | -- |
| Rule       | LIFO    | FIFO     |
| Insert     | PUSH    | Enqueue  |
| Remove     | POP     | Dequeue  |
| Access end | One end | Two ends |

👉 **Guaranteed comparison question**



## 🔢 Time Complexity (Easy Marks)

| Operation | Stack | Queue |
|  | -- | -- |
| Insert    | O(1)  | O(1)  |
| Delete    | O(1)  | O(1)  |



## 📝 EXAM-STYLE QUESTIONS

1. Define stack and queue.
2. Explain LIFO and FIFO.
3. Stack vs Queue.
4. Explain bracket matching using stack.
5. Applications of stack and queue.



## 💻 VERY LIKELY CODING QUESTION

### Bracket Matching (Pseudo-code idea)

```c
for each char in string:
  if opening bracket:
    push
  else if closing bracket:
    if stack empty → unbalanced
    pop
end
if stack empty → balanced
```



## ✅ QUICK SELF-CHECK

Answer in your head:

* Stack rule? → LIFO
* Queue rule? → FIFO
* Which uses recursion? → Stack
* BFS uses? → Queue

# 🌳 LECTURE 7 — TREES

👉 **Big idea**
Trees are used when we want **fast searching + structured data** (better than lists).


## 1️⃣ What is a Tree?

### Definition (EXAM SENTENCE)

> A tree is a hierarchical data structure consisting of **nodes** connected by **edges**, with one node designated as the **root**.



## 2️⃣ Tree Terminology ⭐⭐⭐ (MEMORIZE)

| Term          | Meaning                  |
| - |  |
| Node          | Data element             |
| Edge          | Connection between nodes |
| Root          | Top node                 |
| Parent        | Node above               |
| Child         | Node below               |
| Leaf          | Node with no children    |
| Internal node | Node with children       |
| Subtree       | Tree formed from a node  |

👉 **Exam loves terminology questions**



## 3️⃣ Depth, Level, Height (VERY IMPORTANT)

### Depth of a node

* Number of edges from **root to node**

### Level of a node

* Root is **level 0**

### Height of a tree

* Maximum level in the tree

📌 **Key relationship**:

> Height measures the **longest path** from root to a leaf.



## 4️⃣ Binary Tree ⭐⭐⭐

### Definition:

> A binary tree is a tree in which **each node has at most two children**.

Children are:

* Left child
* Right child



## 5️⃣ Types of Binary Trees (EXAM FAVORITE)

### 1. Full Binary Tree

* Every node has **0 or 2 children**



### 2. Complete Binary Tree

* All levels filled **except possibly last**
* Last level filled **from left to right**



### 3. Perfect Binary Tree

* Full + Complete
* All levels completely filled

👉 **Exam question**:
“Differentiate full, complete, and perfect binary trees.”



## 6️⃣ Binary Tree Properties ⭐⭐⭐

For a **perfect binary tree** of height `h`:

* Number of nodes = `2^h − 1`

👉 This formula is often asked.



## 7️⃣ Tree Traversals ⭐⭐⭐⭐⭐ (VERY IMPORTANT)

Traversal = visiting all nodes **once**.

### 1. Preorder

```
Root → Left → Right
```



### 2. Inorder

```
Left → Root → Right
```



### 3. Postorder

```
Left → Right → Root
```



### 4. Level Order

* Visit level by level
* Uses **queue**



### Example (mentally visualize):

```
      A
     / \
    B   C
   / \
  D   E
```

| Traversal   | Result    |
| -- |  |
| Preorder    | A B D E C |
| Inorder     | D B E A C |
| Postorder   | D E B C A |
| Level order | A B C D E |

👉 **Guaranteed exam question**



## 8️⃣ Binary Search Tree (BST) ⭐⭐⭐

### Definition (EXAM SENTENCE)

> A Binary Search Tree is a binary tree where:

* Left subtree values < root
* Right subtree values ≥ root



### BST Properties

* Inorder traversal → **sorted order**
* Average search → **O(log n)**
* Worst case (skewed) → **O(n)**



### Why BST is better than list?

* Faster search
* Structured insertion



## 9️⃣ Relationship Between Height & Performance ⭐⭐⭐

| Tree shape | Height | Performance |
| - |  | -- |
| Balanced   | log n  | Fast        |
| Skewed     | n      | Slow        |

👉 This explains **why balancing matters** (AVL, B-tree later).



## 🔁 Tree Traversal (Recursive Pseudo-code)

### Inorder traversal

```c
inorder(node):
  if node == NULL return
  inorder(node->left)
  visit(node)
  inorder(node->right)
```

👉 Very likely **coding question**



## 📝 EXAM-STYLE QUESTIONS

1. Define tree and binary tree.
2. Difference between full and complete binary tree.
3. Find inorder / preorder traversal of a given tree.
4. Why inorder traversal of BST is sorted?
5. What is height of a tree?



## ✅ QUICK SELF-CHECK

Answer in your head:

* Max children in binary tree? → 2
* Traversal that gives sorted BST? → Inorder
* Which traversal uses queue? → Level order
* Height of skewed tree with n nodes? → n

If you got these → excellent.

Excellent — **Lecture 8 (Sorting)** is one of the **most important lectures for your exam**, especially because:

* Sorting appears in **HWs**
* Sorting appears in **projects**
* Sorting is **very likely one of the 2 coding questions**

We’ll make this **clear, structured, and exam-safe**.



# 🔀 LECTURE 8 — SORTING ALGORITHMS

👉 **Big idea**
Sorting = arranging data in **non-decreasing order** based on a **key**.



## 1️⃣ Why Sorting Matters?

* Makes searching faster (binary search)
* Organizes data
* Used everywhere (databases, OS, algorithms)



## 2️⃣ Important Sorting Terms ⭐

### Stable Sort

> A sorting algorithm is **stable** if it preserves the relative order of equal elements.

Example:

```
(5,a) (3,b) (5,c)
```

After stable sort:

```
(3,b) (5,a) (5,c)
```



### Internal vs External Sorting

* **Internal**: data fits in memory
* **External**: data too large → disk-based

(Exam focus: **internal sorting**)



## 3️⃣ Three Simple Sorting Algorithms (O(n²)) ⭐⭐⭐

### 1. Insertion Sort ⭐⭐⭐ (VERY LIKELY CODE)

#### Idea:

* Insert element into already sorted part

Example:

```
[27 53] 36 → [27 36 53]
```

#### Pseudo-code:

```c
for i = 1 to n-1
  for j = i down to 1
    if A[j] < A[j-1]
      swap
```

#### Time Complexity:

* Best: **O(n)** (already sorted)
* Avg/Worst: **O(n²)**

✔ Stable
✔ Simple
✔ Good for small datasets



### 2. Bubble Sort

#### Idea:

* Repeatedly swap adjacent elements

#### Time Complexity:

* Best: **O(n²)**
* Worst: **O(n²)**

❌ Slow
✔ Simple



### 3. Selection Sort

#### Idea:

* Select smallest element and place at front

#### Time Complexity:

* Best/Worst: **O(n²)**

❌ Not stable
✔ Few swaps



## 4️⃣ Fast Sorting Algorithms ⭐⭐⭐⭐⭐

### 4. Merge Sort ⭐⭐⭐

#### Strategy:

**Divide and Conquer**

Steps:

1. Divide array into halves
2. Sort halves recursively
3. Merge sorted halves

#### Time Complexity:

* Best/Average/Worst: **O(n log n)**

✔ Stable
❌ Extra memory needed



### 5. Quick Sort ⭐⭐⭐ (PROJECT RELEVANT)

#### Strategy:

* Choose pivot
* Partition array
* Recursively sort

#### Time Complexity:

* Average: **O(n log n)**
* Worst: **O(n²)** (bad pivot)

✔ Fast in practice
❌ Not stable

👉 Your **Project 2** is from here.



## 5️⃣ Comparison Table (MEMORIZE THIS)

| Algorithm | Best       | Avg        | Worst      | Stable |
|  | - | - | - |  |
| Insertion | O(n)       | O(n²)      | O(n²)      | ✔      |
| Bubble    | O(n²)      | O(n²)      | O(n²)      | ✔      |
| Selection | O(n²)      | O(n²)      | O(n²)      | ❌      |
| Merge     | O(n log n) | O(n log n) | O(n log n) | ✔      |
| Quick     | O(n log n) | O(n log n) | O(n²)      | ❌      |



## 6️⃣ When to Use Which? (THEORY QUESTION)

* Small input → **Insertion sort**
* Large input → **Merge / Quick**
* Need stability → **Merge / Insertion**
* Memory limited → **Quick**



## 7️⃣ VERY LIKELY CODING QUESTIONS

### A. Insertion Sort (WRITE THIS)

```c
void insertionSort(int A[], int n) {
  for(int i = 1; i < n; i++) {
    int key = A[i];
    int j = i - 1;
    while(j >= 0 && A[j] > key) {
      A[j + 1] = A[j];
      j--;
    }
    A[j + 1] = key;
  }
}
```



### B. Merge Sort (STRUCTURE)

```c
mergeSort(A, l, r):
  if l < r:
    m = (l + r) / 2
    mergeSort(A, l, m)
    mergeSort(A, m+1, r)
    merge(A, l, m, r)
```



## 📝 EXAM-STYLE QUESTIONS

1. Compare insertion and selection sort.
2. Why quick sort is fast in practice?
3. Which sorting algorithm is stable?
4. Explain merge sort.
5. Write insertion sort code.



## ✅ QUICK SELF-CHECK

Answer mentally:

* Best case of insertion sort? → O(n)
* Stable fast algorithm? → Merge sort
* Worst case of quick sort? → O(n²)
* Sorting used in Project 2? → Quick sort



# 🔍 LECTURE 9 — SEARCHING & HASHING

👉 **Big idea**
Searching = finding a record with a given key.
Hashing = **direct access** using a hash function.



## PART A — SEARCHING



## 1️⃣ What is Searching?

### Definition (EXAM SENTENCE)

> Searching is the process of locating a record with a specified key in a collection of data.



## 2️⃣ Linear (Sequential) Search ⭐

### Idea:

* Check elements **one by one**

### Time Complexity:

* Best case: **O(1)**
* Worst case: **O(n)**
* Average case: **O(n)**

### Pseudo-code:

```c
for i = 0 to n-1
  if A[i] == key
    return i
return -1
```

✔ Works on **unsorted data**
❌ Slow for large n



## 3️⃣ Binary Search ⭐⭐⭐ (VERY IMPORTANT)

### Condition:

⚠️ **Array must be sorted**

### Idea:

* Compare with middle element
* Eliminate half of data each step

### Time Complexity:

* **O(log n)**

### Pseudo-code (iterative):

```c
low = 0, high = n-1
while low <= high:
  mid = (low + high)/2
  if A[mid] == key → found
  else if key < A[mid] → high = mid-1
  else → low = mid+1
```

👉 **Exam sentence**:

> Binary search is faster than linear search because it reduces the search space by half at each step.



## 4️⃣ Comparing Linear vs Binary Search ⭐⭐⭐

| Feature         | Linear     | Binary           |
|  | - | - |
| Sorted required | ❌          | ✔                |
| Time            | O(n)       | O(log n)         |
| Method          | Sequential | Divide & conquer |



## PART B — HASHING (VERY IMPORTANT)



## 5️⃣ What is Hashing?

### Definition (EXAM SENTENCE)

> Hashing is a technique that maps a key directly to an index in a hash table using a hash function.



## 6️⃣ Hash Table

* Array-like structure
* Stores key-value pairs
* Index computed using **hash function**

Example:

```
index = key % table_size
```



## 7️⃣ Why Hashing is Fast?

* Direct access
* Average time complexity:

  * Search: **O(1)**
  * Insert: **O(1)**
  * Delete: **O(1)**

👉 **Exam question**:
“Why hashing is faster than searching?”



## 8️⃣ Collision ⭐⭐⭐

### What is collision?

> When two different keys produce the same hash value.

Example:

```
h(12) = 2
h(22) = 2
```



## 9️⃣ Collision Handling Techniques ⭐⭐⭐

### 1. Chaining

* Each table index has a linked list
* All collided elements go there

✔ Simple
❌ Extra memory



### 2. Open Addressing

Store elements in the table itself.

Types:

* Linear probing
* Quadratic probing
* Double hashing

Example (Linear Probing):

```
h(key) = index
if occupied → try index+1, index+2, ...
```



## 1️⃣0️⃣ Limitations of Hashing (EXAM THEORY)

* No range queries
* No order
* Depends on good hash function

👉 That’s why **trees & indexing** are needed (Lecture 10).



## 📝 EXAM-STYLE QUESTIONS

1. Define searching.
2. Difference between linear and binary search.
3. Why binary search requires sorted array?
4. What is hashing?
5. What is collision? How is it handled?
6. Compare chaining and open addressing.



## 💻 LIKELY CODING QUESTION

### Binary Search (WRITE THIS)

```c
int binarySearch(int A[], int n, int key) {
  int low = 0, high = n - 1;
  while(low <= high) {
    int mid = (low + high) / 2;
    if(A[mid] == key) return mid;
    else if(key < A[mid]) high = mid - 1;
    else low = mid + 1;
  }
  return -1;
}
```



## ✅ QUICK SELF-CHECK

Answer mentally:

* Binary search time? → O(log n)
* Hashing average time? → O(1)
* Collision meaning? → Same hash index
* Chaining uses? → Linked list


# 📘 LECTURE 10 — Indexing & Advanced Trees

👉 **Big idea**
Hashing is fast, but limited.
Indexing and advanced trees solve **searching large data efficiently**, especially on disk.



## 1️⃣ Why Hashing is NOT Enough (EXAM FAVORITE)

Even though hashing is fast (**O(1)** average), it has **limitations**.

### Limitations of Hashing:

1. ❌ Cannot handle **range queries**

   * Example: find students with marks between 70–80
2. ❌ Cannot easily find **minimum / maximum**
3. ❌ No sorted order
4. ❌ Performance depends on hash function

👉 **Exam sentence**:

> Hashing supports only exact-match queries and does not preserve order.



## 2️⃣ What is Indexing? ⭐⭐⭐

### Definition (EXAM SENTENCE)

> An index is a data structure that improves the speed of data retrieval operations on large datasets.

Think of:

* **Book index**
* **Database index**



## 3️⃣ What Operations Does an Index Support?

| Operation    | Time      |
|  |  |
| Insert       | O(log n)  |
| Delete       | O(log n)  |
| Exact search | O(log n)  |
| Range search | Efficient |
| Min / Max    | O(log n)  |

👉 Indexing is **better than hashing** for many applications.



## 4️⃣ Linear Index

### Idea:

* Sorted list of keys
* Each key points to data location

### Problem:

* Index becomes **too large**
* Slow disk access



## 5️⃣ Why Not Use a Simple BST? ⭐⭐⭐

### Problems with BST:

1. May become **unbalanced**
2. Height can be **O(n)**
3. Too many disk accesses

👉 Disk access is **VERY slow** → we want **short trees**



## 6️⃣ B-Trees ⭐⭐⭐ (IMPORTANT)

### What is a B-tree?

> A B-tree is a **height-balanced multi-way tree** designed for disk storage.



### Key Properties (MEMORIZE):

* Always **balanced**
* All leaves at **same level**
* Each node can have **many children**
* Keys inside node are **sorted**

Example:

* Order `m`
* Each node has between `⌈m/2⌉` and `m` children



## 7️⃣ Why B-Trees Are Used in Databases?

* Very **short height**
* Fewer disk accesses
* Efficient for large datasets

👉 **Exam sentence**:

> B-trees reduce disk access by storing multiple keys in a single node.



## 8️⃣ B+ Trees (Mention Only)

Difference from B-tree:

* Data stored only in **leaf nodes**
* Internal nodes store keys only
* Leaves linked for range queries

📌 You usually just **explain idea**, not details.



## 9️⃣ Advanced Trees (Know Names + Purpose)

You don’t code these — just **recognize** them.

| Tree           | Purpose                       |
| -- | -- |
| AVL Tree       | Self-balancing BST            |
| Red-Black Tree | Balanced, faster inserts      |
| Splay Tree     | Recently used nodes near root |
| Trie           | String searching              |
| KD-tree        | Multidimensional data         |

👉 **Exam question**:
“Name some balanced trees and their use.”



## 📝 EXAM-STYLE QUESTIONS

1. Why hashing is not suitable for range queries?
2. What is indexing?
3. Why BST is not ideal for disk-based data?
4. What is a B-tree and why it is used?
5. Difference between B-tree and B+ tree.



## ✅ QUICK SELF-CHECK

Answer in your head:

* Hashing supports range queries? → NO
* B-tree height? → Always balanced
* Why multi-way tree? → Fewer disk access
* Data in B+ tree stored where? → Leaf nodes


# 📘 LECTURE 10 — Indexing & Advanced Trees

👉 **Big idea**
Hashing is fast, but limited.
Indexing and advanced trees solve **searching large data efficiently**, especially on disk.



## 1️⃣ Why Hashing is NOT Enough (EXAM FAVORITE)

Even though hashing is fast (**O(1)** average), it has **limitations**.

### Limitations of Hashing:

1. ❌ Cannot handle **range queries**

   * Example: find students with marks between 70–80
2. ❌ Cannot easily find **minimum / maximum**
3. ❌ No sorted order
4. ❌ Performance depends on hash function

👉 **Exam sentence**:

> Hashing supports only exact-match queries and does not preserve order.



## 2️⃣ What is Indexing? ⭐⭐⭐

### Definition (EXAM SENTENCE)

> An index is a data structure that improves the speed of data retrieval operations on large datasets.

Think of:

* **Book index**
* **Database index**



## 3️⃣ What Operations Does an Index Support?

| Operation    | Time      |
|  |  |
| Insert       | O(log n)  |
| Delete       | O(log n)  |
| Exact search | O(log n)  |
| Range search | Efficient |
| Min / Max    | O(log n)  |

👉 Indexing is **better than hashing** for many applications.



## 4️⃣ Linear Index

### Idea:

* Sorted list of keys
* Each key points to data location

### Problem:

* Index becomes **too large**
* Slow disk access



## 5️⃣ Why Not Use a Simple BST? ⭐⭐⭐

### Problems with BST:

1. May become **unbalanced**
2. Height can be **O(n)**
3. Too many disk accesses

👉 Disk access is **VERY slow** → we want **short trees**



## 6️⃣ B-Trees ⭐⭐⭐ (IMPORTANT)

### What is a B-tree?

> A B-tree is a **height-balanced multi-way tree** designed for disk storage.



### Key Properties (MEMORIZE):

* Always **balanced**
* All leaves at **same level**
* Each node can have **many children**
* Keys inside node are **sorted**

Example:

* Order `m`
* Each node has between `⌈m/2⌉` and `m` children



## 7️⃣ Why B-Trees Are Used in Databases?

* Very **short height**
* Fewer disk accesses
* Efficient for large datasets

👉 **Exam sentence**:

> B-trees reduce disk access by storing multiple keys in a single node.



## 8️⃣ B+ Trees (Mention Only)

Difference from B-tree:

* Data stored only in **leaf nodes**
* Internal nodes store keys only
* Leaves linked for range queries

📌 You usually just **explain idea**, not details.



## 9️⃣ Advanced Trees (Know Names + Purpose)

You don’t code these — just **recognize** them.

| Tree           | Purpose                       |
| -- | -- |
| AVL Tree       | Self-balancing BST            |
| Red-Black Tree | Balanced, faster inserts      |
| Splay Tree     | Recently used nodes near root |
| Trie           | String searching              |
| KD-tree        | Multidimensional data         |

👉 **Exam question**:
“Name some balanced trees and their use.”



## 📝 EXAM-STYLE QUESTIONS

1. Why hashing is not suitable for range queries?
2. What is indexing?
3. Why BST is not ideal for disk-based data?
4. What is a B-tree and why it is used?
5. Difference between B-tree and B+ tree.



## ✅ QUICK SELF-CHECK

Answer in your head:

* Hashing supports range queries? → NO
* B-tree height? → Always balanced
* Why multi-way tree? → Fewer disk access
* Data in B+ tree stored where? → Leaf nodes


# 🧠 LECTURE 12 — ALGORITHM DESIGN TECHNIQUES

👉 **Big idea**
Instead of memorizing algorithms, we learn **how to design them**.

The exam will test:

* Which technique to use
* Why it works
* Where it fails



## 1️⃣ Why Algorithm Design Matters

### Exam-ready sentence:

> Algorithm design techniques provide systematic approaches to solve problems efficiently.



## 2️⃣ Three Core Design Techniques ⭐⭐⭐⭐⭐

You **must know all three**:

1. **Greedy**
2. **Divide and Conquer**
3. **Dynamic Programming**



# 1️⃣ GREEDY ALGORITHMS ⭐⭐⭐⭐⭐



## What is a Greedy Algorithm?

### Definition (EXAM SENTENCE)

> A greedy algorithm builds a solution step by step by always choosing the locally optimal choice.

📌 Makes the **best choice now**, hopes for global optimum.



## Characteristics

* Simple
* Fast
* Easy to implement
* ❌ Not always optimal



## Examples (MEMORIZE)

| Problem                  | Greedy? |
|  | - |
| Kruskal’s MST            | ✔       |
| Prim’s MST               | ✔       |
| Dijkstra                 | ✔       |
| Huffman coding           | ✔       |
| Coin change (some cases) | ❌       |



## When Greedy Works

* Problem has **greedy-choice property**
* Optimal substructure

👉 **Exam question**:
“Why greedy works for MST but not for all problems?”



## Example: Coin Change (WHY IT FAILS)

Coins: `{1, 3, 4}`
Make `6`

Greedy:

```
4 + 1 + 1 → 3 coins
```

Optimal:

```
3 + 3 → 2 coins
```

❌ Greedy fails



# 2️⃣ DIVIDE AND CONQUER ⭐⭐⭐⭐



## Definition

> Divide the problem into smaller subproblems, solve them recursively, and combine results.



## Steps:

1. Divide
2. Conquer
3. Combine



## Examples (MEMORIZE)

| Algorithm     | Technique        |
| - | - |
| Merge Sort    | Divide & Conquer |
| Quick Sort    | Divide & Conquer |
| Binary Search | Divide & Conquer |



## Time Complexity Pattern

Often:

```
T(n) = 2T(n/2) + O(n)
```

➡ **O(n log n)**



## Exam Question:

“Explain merge sort using divide and conquer.”



# 3️⃣ DYNAMIC PROGRAMMING (DP) ⭐⭐⭐⭐⭐



## Why DP?

Used when:

* Overlapping subproblems
* Optimal substructure



## Definition (EXAM SENTENCE)

> Dynamic programming solves a problem by storing results of subproblems to avoid repeated computation.



## DP vs Greedy

| Feature    | Greedy         | DP         |
| - | -- | - |
| Choice     | Local          | Global     |
| Optimal    | Not guaranteed | Guaranteed |
| Complexity | Low            | Higher     |



## Examples (MEMORIZE)

| Problem                      | Technique |
| - |  |
| Fibonacci                    | DP        |
| Knapsack                     | DP        |
| Matrix chain                 | DP        |
| Shortest path (Bellman-Ford) | DP        |



## Fibonacci Example (KEY IDEA)

### Recursive (BAD):

* O(2ⁿ)
* Repeated work

### DP (GOOD):

* O(n)
* Store results



## Exam Question:

“Why dynamic programming is better than naive recursion?”



## 4️⃣ HOW TO CHOOSE THE RIGHT TECHNIQUE ⭐⭐⭐

### Exam-style reasoning:

* Need fastest, simple? → Greedy
* Problem naturally splits? → Divide & Conquer
* Repeated subproblems? → DP



## 5️⃣ CONNECTION TO YOUR COURSE ⭐⭐⭐

| Topic          | Technique        |
| -- | - |
| Sorting        | Divide & Conquer |
| Graph MST      | Greedy           |
| Shortest path  | Greedy / DP      |
| Huffman coding | Greedy           |

👉 **Teacher loves these connections**



## 📝 EXAM-STYLE QUESTIONS (VERY LIKELY)

1. Define greedy algorithm.
2. When does greedy fail?
3. Explain divide and conquer with example.
4. What is dynamic programming?
5. Greedy vs DP comparison.
6. Which design technique is used in Kruskal’s algorithm?



## ✅ FINAL SELF-CHECK (IMPORTANT)

Answer in your head:

* Greedy chooses? → Local optimum
* DP stores? → Subproblem results
* Merge sort technique? → Divide & Conquer
* Kruskal uses? → Greedy

# 2 full exam-style coding questions (with answers)

Teacher said “2 codes” so these two are the most likely because they match our **projects** (Peak + MST).

## Coding Q1 (Peak Finding — Project 1 style)

**Problem:** Given an integer array `A` of length `n`, find an index `i` such that `A[i]` is a **peak** (A[i] ≥ neighbors). Return any peak index.
**Requirement:** O(log n) solution.

### Answer (C++ — binary-search peak)

```cpp
#include <bits/stdc++.h>
using namespace std;

// Returns any peak index. Peak: A[i] >= neighbors (when they exist).
int findPeakIndex(const vector<long long>& A) {
    int n = (int)A.size();
    if (n == 0) return -1;
    if (n == 1) return 0;

    int l = 0, r = n - 1;
    while (l < r) {
        int mid = l + (r - l) / 2;

        // Compare mid with mid+1 to decide which side must contain a peak.
        if (A[mid] < A[mid + 1]) {
            // Peak must be on the right side.
            l = mid + 1;
        } else {
            // Peak is at mid or on the left side.
            r = mid;
        }
    }
    return l; // l == r is a peak index
}

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int n;
    cin >> n;
    vector<long long> A(n);
    for (int i = 0; i < n; i++) cin >> A[i];

    int idx = findPeakIndex(A);
    cout << "Peak index: " << idx << "\n";
    if (idx != -1) cout << "Peak value: " << A[idx] << "\n";
    return 0;
}
```

**Why it works (one line to write in exam):**
If `A[mid] < A[mid+1]`, slope goes up so a peak exists to the right; else peak exists at mid or left. This halves search each step → **O(log n)**.



## Coding Q2 (Minimum Spanning Tree — Kruskal, Project 3 style)

**Problem:** Given an undirected connected weighted graph (V vertices, E edges), output MST total weight and chosen edges using **Kruskal**.

### Answer (C++ — DSU + sort edges)

```cpp
#include <bits/stdc++.h>
using namespace std;

struct DSU {
    vector<int> p, r;
    DSU(int n=0){ init(n); }
    void init(int n){
        p.resize(n);
        r.assign(n, 0);
        iota(p.begin(), p.end(), 0);
    }
    int find(int x){
        if(p[x]==x) return x;
        return p[x] = find(p[x]);
    }
    bool unite(int a, int b){
        a = find(a); b = find(b);
        if(a==b) return false;
        if(r[a] < r[b]) swap(a,b);
        p[b] = a;
        if(r[a]==r[b]) r[a]++;
        return true;
    }
};

struct Edge {
    int u, v;
    long long w;
};

int main(){
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int V, E;
    cin >> V >> E;
    vector<Edge> edges(E);
    for(int i=0;i<E;i++){
        cin >> edges[i].u >> edges[i].v >> edges[i].w;
    }

    sort(edges.begin(), edges.end(),
         [](const Edge& a, const Edge& b){ return a.w < b.w; });

    DSU dsu(V);
    long long total = 0;
    vector<Edge> mst;

    for(const auto& e: edges){
        if(dsu.unite(e.u, e.v)){
            mst.push_back(e);
            total += e.w;
            if((int)mst.size() == V-1) break;
        }
    }

    cout << "MST total weight = " << total << "\n";
    cout << "Edges in MST:\n";
    for(const auto& e: mst){
        cout << e.u << " " << e.v << " " << e.w << "\n";
    }
    return 0;
}
```

**One-paragraph exam explanation:**
Kruskal sorts edges by weight, then scans from smallest to largest, adding an edge only if it connects two different components (checked using DSU). Stop after `V-1` edges. Time: sorting `O(E log E)`.

### What? Oh I see, you must be a Seeker from Quidditch but unfortunately I dont have nothing more to offer you.

Anyways, many many **Congratulations**, you are good to go!
