# Sorting Algorithms

Sorting algorithms are used to **arrange data in a specific order**, usually ascending or descending.

Examples of where sorting is useful:

* Showing products by price
* Ordering scores on a leaderboard
* Organizing dates or names

In this section, we focus on **two simple, beginner-friendly sorting algorithms** to understand *how algorithms manipulate data step by step*.

---

## Bubble Sort

### Core Idea

Bubble Sort works by **repeatedly comparing neighboring elements** and swapping them if they are in the wrong order.

Over multiple passes:

* Larger values slowly **bubble up** to the end of the array
* The array becomes more sorted after each pass

Think of bubbles rising to the surface — the biggest values end up at the top (end).

---

### Bubble Sort – Simple Explanation

1. Start at the beginning of the array
2. Compare the current element with the next one
3. Swap them if they are out of order
4. Continue until you reach the end
5. Repeat the process for multiple passes

After each pass, the **largest unsorted element is placed at the end**.

---

### Bubble Sort – Pseudocode

```
repeat until array is sorted:
    set swapped = false
    for each index i from 0 to length - 2:
        if array[i] > array[i + 1]:
            swap array[i] and array[i + 1]
            set swapped = true
    if swapped is false:
        stop early (array is already sorted)
```

---

### Early Stop Optimization (Why It Matters)

If a full pass happens **without any swaps**, the array is already sorted.

Instead of continuing unnecessary passes, the algorithm can **stop early**.

This teaches an important idea:

> Algorithms can often be improved by observing what is happening during execution.

---

### Bubble Sort – Key Characteristics

* Simple to understand
* Uses many comparisons and swaps
* Worst-case time complexity: **O(n²)**
* Best-case (with early stop): **O(n)**

---

## Selection Sort

### Core Idea

Selection Sort works by **selecting the largest value** in the unsorted part of the array and placing it in its correct position.

Instead of bubbling values step by step, selection sort:

* Finds the correct value first
* Then places it where it belongs

---

### Selection Sort – Simple Explanation

1. Look at the entire array
2. Find the **largest element**
3. Swap it with the element at the last unsorted position
4. Reduce the unsorted portion of the array
5. Repeat until the array is sorted

After each pass, the **largest remaining value is locked into its final position**.

---

### Selection Sort – Pseudocode (Largest to End)

```
for lastIndex from length - 1 down to 1:
    set maxIndex = 0
    for i from 1 to lastIndex:
        if array[i] > array[maxIndex]:
            maxIndex = i
    swap array[maxIndex] and array[lastIndex]
```

---

### Selection Sort – Key Characteristics

* Fewer swaps than bubble sort
* Still compares every element in each pass
* Time complexity: **O(n²)** (best, average, and worst cases)
* Easy to reason about

---

## Comparing the Two

| Bubble Sort          | Selection Sort              |
| -------------------- | --------------------------- |
| Swaps frequently     | Swaps once per pass         |
| Can stop early       | Always completes all passes |
| Simpler to visualize | Simpler to control          |
| O(n²) worst case     | O(n²) always                |

---

## Key Takeaways

* Sorting algorithms solve the same problem in different ways
* Simple algorithms help build intuition
* Understanding *how* an algorithm works is more important than memorizing it
* These ideas prepare you for more advanced algorithms later

## More Practice Scenarios

In class, we have tried to find the largest element in each iteration and put it as the last element of an array. Now, try these two:
 * Find the smallest element and put it in the beginning of the array (both bubble and merge sorts). Reverse methodology of what we did in class. 
 * Try to sort the elements now in descending order, instead of ascending !