---
title: "Sorting Algorithms: Insertion Sort | Data Structures and Algorithms Day #24"
seoTitle: "Sorting Algorithms: Insertion Sort | Day #24"
datePublished: Fri Oct 25 2024 21:00:36 GMT+0000 (Coordinated Universal Time)
cuid: cm2p7v2im000109l50yoy2odi
slug: sorting-algorithms-insertion-sort-data-structures-and-algorithms-day-24
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728415827446/a64d57a0-f3dd-43ab-b259-17ae4250d1f7.png
tags: software-development, programming-blogs, programming, java, javascript, python, web-development, webdev, developer, devops, software-engineering, programming-languages, web3, devops-articles, wemakedevs

---

Sorting algorithms are fundamental to computer science and play a crucial role in organizing data. They arrange elements in a specific order—either ascending or descending—making it easier to search, process, or analyze datasets efficiently.

**Insertion Sort** is one of the simplest and most intuitive sorting algorithms. While it isn’t as efficient for large datasets as some advanced algorithms like Quick Sort or Merge Sort, it’s a great introduction to sorting logic. Insertion Sort shines in situations where datasets are small or nearly sorted.

---

%[https://youtu.be/hmHegN_yy_s?si=m12ioZfJn06kQ5MS] 

## **Understanding Insertion Sort**

At its core, Insertion Sort works just like sorting a **hand of playing cards**. Imagine you pick up cards one by one and insert each into its correct position in an already sorted section of the hand. Similarly, Insertion Sort builds the sorted list one element at a time by repeatedly **inserting elements into their appropriate positions**.

### **How it Works:**

1. Start with the second element in the list (since a single-element list is already sorted).
    
2. Compare the current element with elements to its left.
    
3. Shift elements to the right if they are larger than the current element.
    
4. Insert the current element into the correct position.
    
5. Repeat the process for all elements in the list.
    

---

## **Algorithm Walkthrough**

Let’s take a sample array:  
`[8, 4, 2, 10, 6]`

### **Step-by-Step Example:**

1. **Initial array:** `[8, 4, 2, 10, 6]`
    
    * Start with the second element, `4`. Compare it with `8`.
        
    * Since `4 < 8`, shift `8` to the right and insert `4` in the first position.  
        **Array after first step:** `[4, 8, 2, 10, 6]`
        
2. **Next element:** `2`
    
    * Compare `2` with `8` and `4`. Shift both elements to the right.
        
    * Insert `2` at the first position.  
        **Array after second step:** `[2, 4, 8, 10, 6]`
        
3. **Next element:** `10`
    
    * No need to shift since `10` is larger than `8`.  
        **Array after third step:** `[2, 4, 8, 10, 6]`
        
4. **Next element:** `6`
    
    * Compare `6` with `10` and `8`. Shift both elements right and insert `6` in its correct position.  
        **Final sorted array:** `[2, 4, 6, 8, 10]`
        

Using this approach, each element is placed exactly where it belongs by the time the algorithm completes.

---

## **Code Implementation**

Here’s how you can implement Insertion Sort in both Python and JavaScript.

### **Python Code:**

```python
def insertion_sort(arr):
    # Traverse from the second element to the end
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        # Shift elements greater than the key to the right
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        # Insert the key in its correct position
        arr[j + 1] = key
    return arr

# Example usage
sample_array = [8, 4, 2, 10, 6]
sorted_array = insertion_sort(sample_array)
print("Sorted array:", sorted_array)  # Output: [2, 4, 6, 8, 10]
```

### **JavaScript Code:**

```javascript
function insertionSort(arr) {
    // Traverse from the second element to the end
    for (let i = 1; i < arr.length; i++) {
        let key = arr[i];
        let j = i - 1;
        // Shift elements greater than the key to the right
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        // Insert the key in its correct position
        arr[j + 1] = key;
    }
    return arr;
}

// Example usage
const sampleArray = [8, 4, 2, 10, 6];
const sortedArray = insertionSort(sampleArray);
console.log("Sorted array:", sortedArray);  // Output: [2, 4, 6, 8, 10]
```

---

## **Time and Space Complexity**

* **Best Case:** O(n) – If the array is already sorted.
    
* **Average Case:** O(n²) – When elements are in random order.
    
* **Worst Case:** O(n²) – When the array is sorted in reverse order.
    
* **Space Complexity:** O(1) – Insertion Sort is an **in-place algorithm**, meaning it requires only a constant amount of extra memory.
    

---

## **Advantages and Disadvantages**

### **Advantages:**

1. **Simple and easy to implement.**
    
2. **Stable sort:** Maintains the relative order of equal elements.
    
3. **Efficient for small or partially sorted datasets.**
    
4. Requires minimal memory as it sorts the array in place.
    

### **Disadvantages:**

1. **Inefficient for large datasets** due to its O(n²) time complexity.
    
2. **Slower than advanced algorithms** like Merge Sort or Quick Sort.
    

---

## **Real-World Applications**

1. **Educational Purposes:** Often used to teach the fundamentals of sorting due to its simplicity.
    
2. **Partially Sorted Data:** Ideal for cases where only a few elements are unsorted.
    
3. **Small Data Sets:** Insertion Sort is practical for smaller datasets where more advanced algorithms would introduce unnecessary overhead.
    

---

## **Conclusion**

While **Insertion Sort** isn’t the most efficient algorithm for large datasets, it plays a critical role in understanding sorting logic. It demonstrates how elements can be shifted and inserted in place, making it a valuable foundation for more advanced algorithms like **Merge Sort** or **Quick Sort**.

Understanding the mechanics of Insertion Sort helps build a solid foundation in algorithm design and analysis, making it easier to grasp more complex algorithms down the line.

---

## **Call to Action**

Now that you’ve learned about Insertion Sort, try implementing it in various programming languages and experiment with different datasets. Challenge yourself to compare it with other sorting algorithms like [**Selection Sort**](https://hojaleaks.com/sorting-algorithms-selection-sort-data-structures-and-algorithms-day-23) and [**Bubble Sort**](https://hojaleaks.com/sorting-algorithms-bubble-sort-data-structures-and-algorithms-day-22), and analyze their performance. Happy coding!