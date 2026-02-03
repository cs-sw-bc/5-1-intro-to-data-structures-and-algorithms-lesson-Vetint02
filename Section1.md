# Section 1: Data Structures

**Duration:** ~50 minutes

In this section, you’ll build a foundational understanding of **what data structures are**, **why they exist**, and **how they impact the way software behaves**.

This section is about *thinking*, not memorizing.

---

## Learning Goals

By the end of this section, you should be able to:

* Explain what a data structure is in your own words
* Describe why choosing the right data structure matters
* Understand how data structures relate to **algorithms**, **memory**, and **performance**

---

## 1. What Are Data Structures?

A **data structure** is a way of organizing and storing data so it can be used efficiently.

In software development, we rarely deal with just one or two values. We deal with:

* Lists of users
* Collections of messages
* Sets of transactions
* Streams of sensor data

Data structures help us answer questions like:

* How do we store this data?
* How do we access it quickly?
* How do we update it safely?

> The same data can be stored in multiple ways — but not all ways are equally efficient.

### Think About This

* Would you store **5 items** the same way as **5,000 items**?
* What would happen if your app suddenly had **10× more users**?

---

## 2. Data Structures and Algorithms

Data structures and algorithms always work **together**.

* A **data structure** defines *how data is organized*
* An **algorithm** defines *the steps used to work with that data*

You can think of it like this:

* The data structure is the *layout*
* The algorithm is the *process*

Different combinations of data structures and algorithms can solve the **same problem**, but with very different performance.

### An Important Skill You’re Practicing in This Unit

You are **not** expected to learn every possible algorithm.

Instead, you are learning how to:

* Search for solutions
* Read documentation and examples
* Compare different approaches
* Try, test, and fix your code

---

## 3. How Data Lives in Memory

Computers store data in **memory**, which you can imagine as a large collection of numbered storage cells.

Different data structures:

* Use memory differently
* Take up different amounts of space
* Require different operations to read or modify data

Some structures prioritize:

* Fast access
* Low memory usage
* Easy insertion or removal

There is no single “best” choice — only trade-offs.

---

## 4. Common Data Structures (Conceptual Overview)

Below is a **high-level introduction** to some of the most common data structures you’ll encounter in software development. At this stage, the goal is **conceptual understanding**, not implementation details.

### Arrays

An **array** stores elements in a fixed, ordered sequence.

**Key characteristics:**

* Elements are accessed using an index (position)
* Very fast access when you know the index
* Inserting or removing elements in the middle can be costly

**Common uses:**

* Lists of items
* Data that needs fast, direct access
* Situations where order matters

---

### Stacks

A **stack** follows the principle **Last In, First Out (LIFO)**.

Think of a stack like a pile of plates — you add and remove from the top.

**Key characteristics:**

* Only the top element is accessible
* Operations are usually limited to push (add) and pop (remove)

**Common uses:**

* Undo/redo functionality
* Call stacks in programming languages
* Tracking history or temporary state

---

### Queues

A **queue** follows the principle **First In, First Out (FIFO)**.

Think of a lineup at a store — the first person in line is served first.

**Key characteristics:**

* Elements are added at the back and removed from the front
* Preserves processing order

**Common uses:**

* Task scheduling
* Message processing systems
* Print queues and background jobs

---

### Trees

A **tree** organizes data in a hierarchical structure using nodes.

Each node can have one or more child nodes, forming parent–child relationships.

**Key characteristics:**

* Represents hierarchy naturally
* No cycles (you don’t loop back upward)
* Often used for fast searching and organization

**Common uses:**

* File systems
* HTML / DOM structure
* Organizational charts

---

### Binary Trees (A Special Type of Tree)

A **binary tree** is a specific kind of tree where **each node can have at most two children**, commonly referred to as the *left* and *right* child.

Binary trees introduce more structure compared to general trees, which makes certain operations more efficient and predictable.

**Key characteristics:**

* Each node has **0, 1, or 2 children**
* Naturally recursive structure
* Often used as a foundation for more advanced tree-based structures

**Why Binary Trees Matter**
Binary trees are especially important because they form the basis of:

* Binary Search Trees (BSTs)
* Heaps
* Many efficient searching and sorting strategies

When structured correctly, binary trees can significantly reduce the time required to search, insert, or delete data.

**Common uses:**

* Searching and sorting data
* Representing decision processes
* Building efficient lookup structures

---

### Hash Tables (Maps / Dictionaries)

A **hash table** stores data as key–value pairs.

Instead of using indexes, data is accessed using a unique key.

**Key characteristics:**

* Very fast lookup on average
* No guaranteed order
* Keys must be unique

**Common uses:**

* Looking up users by ID
* Caching data
* Counting occurrences (frequency maps)

---

## 5. Big O Notation: Time & Space Complexity

This handout focuses specifically on **Big O notation** — how we reason about the *efficiency* of code in terms of **time** and **memory** as input size grows.

---

### What Big O Is (and What It Is Not)

Big O notation describes **growth**, not exact measurements.

* ❌ Not how fast code runs in seconds
* ❌ Not tied to a specific machine
* ✅ How work or memory grows relatively as input size grows

---

### 5a. Time Complexity

**Time complexity** measures how the *number of operations* grows as input size increases.

We ask:

> If the input gets bigger, how much more work does the algorithm do?

---

#### O(1) — Constant Time

The number of operations stays the same, regardless of input size.

```js
function getFirstItem(arr) {
  return arr[0];
}
```

* Runs in constant time
* Input size does not matter

---

#### O(n) — Linear Time

The number of operations grows in direct proportion to input size.

```js
function printAll(items) {
  for (let i = 0; i < items.length; i++) {
    console.log(items[i]);
  }
}
```

* One loop over the data
* Doubling the input roughly doubles the work

---

#### O(n²) — Quadratic Time

The number of operations grows very quickly as input size increases.

```js
function printPairs(items) {
  for (let i = 0; i < items.length; i++) {
    for (let j = 0; j < items.length; j++) {
      console.log(items[i], items[j]);
    }
  }
}
```

* Loop inside another loop
* Doubling input roughly quadruples the work
* Common in simple sorting algorithms (e.g., bubble sort)

---

#### O(log n) — Logarithmic Time

The number of operations increases very slowly as input size grows.

This happens when the problem space is repeatedly divided in half.

```js
// Conceptual example (binary search idea)
while (start <= end) {
  mid = Math.floor((start + end) / 2);
  // discard half the remaining data
}
```

* Extremely efficient
* Common in binary search and balanced trees

---

#### O(n log n) — Linearithmic Time

A combination of linear and logarithmic growth.

* Common in efficient sorting algorithms
* Scales much better than O(n²)

---

### 5b. Space Complexity

**Space complexity** measures how much **extra memory** an algorithm uses as input size grows.

Like time complexity, it is described using **Big O notation**.

---

#### O(1) — Constant Space

The algorithm uses a fixed amount of extra memory.

```js
function sum(a, b) {
  return a + b;
}
```

* No additional data structures created
* Memory usage does not grow with input

---

#### O(n) — Linear Space

The algorithm allocates memory proportional to input size.

```js
function copyArray(arr) {
  let copy = [];
  for (let i = 0; i < arr.length; i++) {
    copy.push(arr[i]);
  }
  return copy;
}
```

* New array grows as input grows
* Memory usage increases linearly

---

### Time vs Space Trade-Offs

Some algorithms:

* Use **more memory** to run faster
* Use **less memory** but take longer

There is no universally best choice.

The right decision depends on:

* Problem constraints
* Available memory
* Performance requirements

---

### Key Takeaways

* Big O describes **growth**, not exact values
* Time complexity measures *work*
* Space complexity measures *extra memory*
* Both use **Big O notation**
* Understanding patterns matters more than memorizing formulas

This handout will be referenced throughout the unit, especially when discussing sorting and searching algorithms.


---

### Important Reminder

There is no universally “best” data structure.

Each one exists because it solves a **specific type of problem well**. Choosing the right data structure depends on:

* How you access data
* How often you insert or remove items
* Whether order or hierarchy matters
* Performance and memory trade-offs

---

## Key Takeaways

* Data structures organize data in different ways for different needs
* Algorithms depend heavily on how data is structured
* Performance is affected by both **time** and **space** complexity
* Good developers choose data structures based on **trade-offs**, not habit

You’ll revisit these structures throughout this unit and gradually learn how and when to use them effectively.
