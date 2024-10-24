---
title: "Sorting Algorithms: Bubble Sort | Data Structures and Algorithms Day #22"
seoTitle: "Sorting Algorithms: Bubble Sort | Day #22"
datePublished: Wed Oct 23 2024 21:00:14 GMT+0000 (Coordinated Universal Time)
cuid: cm2mcyw6k000008l73fmngsc4
slug: sorting-algorithms-bubble-sort-data-structures-and-algorithms-day-22
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728415609722/33cd6b68-3332-469a-95a8-ff263039eb1f.png
tags: algorithms, programming-blogs, programming, java, javascript, python, development, web-development, data-structures, webdev, beginner, developer, beginners, programming-languages, wemakedevs

---

Sorting algorithms are fundamental tools in computer science, essential for organizing data in a specified order. Among these algorithms, **Bubble Sort** stands out as one of the simplest and most intuitive methods. While it may not be the most efficient for large datasets, understanding Bubble Sort provides a solid foundation for grasping more complex sorting techniques. This article will delve into the principles, implementation, advantages, disadvantages, and practical applications of Bubble Sort.

%[https://youtu.be/QOOLb8LGnJM?si=RfquirfwnJUD1K6d] 

## Understanding Bubble Sort

### What is Bubble Sort?

Bubble Sort is a straightforward sorting algorithm that repeatedly steps through the list to be sorted. It compares adjacent elements and swaps them if they are in the wrong order. This process continues until no swaps are needed, indicating that the list is sorted. The basic idea behind Bubble Sort is to "bubble" the largest (or smallest) elements to the end of the list with each pass.

### How Bubble Sort Works

1. Start at the beginning of the array.
    
2. Compare the first two adjacent elements.
    
3. If the first element is greater than the second, swap them.
    
4. Move to the next pair of adjacent elements and repeat step 3.
    
5. Continue this process until the end of the array is reached.
    
6. Repeat the entire process for the remaining unsorted elements until no swaps are needed.
    

## Algorithm Walkthrough

Let's visualize the Bubble Sort process using a simple example array: `[64, 34, 25, 12, 22, 11, 90]`.

### Step-by-Step Example

* **Pass 1:**
    
    * Compare 64 and 34 → Swap: `[34, 64, 25, 12, 22, 11, 90]`
        
    * Compare 64 and 25 → Swap: `[34, 25, 64, 12, 22, 11, 90]`
        
    * Compare 64 and 12 → Swap: `[34, 25, 12, 64, 22, 11, 90]`
        
    * Compare 64 and 22 → Swap: `[34, 25, 12, 22, 64, 11, 90]`
        
    * Compare 64 and 11 → Swap: `[34, 25, 12, 22, 11, 64, 90]`
        
    * Compare 64 and 90 → No swap: `[34, 25, 12, 22, 11, 64, 90]`
        
* **Pass 2:**
    
    * Repeat the process until the entire array is sorted.
        

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729779582968/f16dffa8-38cb-48cc-90e9-de3399a8e644.png align="center")

## Code Implementation

Below are the implementations of Bubble Sort in both Python and JavaScript.

### Python Example

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr

# Example usage
sample_array = [64, 34, 25, 12, 22, 11, 90]
sorted_array = bubble_sort(sample_array)
print("Sorted array:", sorted_array)  # Output: Sorted array: [11, 12, 22, 25, 34, 64, 90]
```

### JavaScript Example

```javascript
function bubbleSort(arr) {
    let n = arr.length;
    for (let i = 0; i < n; i++) {
        for (let j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
            }
        }
    }
    return arr;
}

// Example usage
const sampleArray = [64, 34, 25, 12, 22, 11, 90];
const sortedArray = bubbleSort(sampleArray);
console.log("Sorted array:", sortedArray);  // Output: Sorted array: [11, 12, 22, 25, 34, 64, 90]
```

## Time and Space Complexity

### Time Complexity

* **Best Case:** O(n) - When the array is already sorted.
    
* **Average Case:** O(n²) - For random order arrays.
    
* **Worst Case:** O(n²) - When the array is sorted in reverse order.
    

### Space Complexity

The space complexity of Bubble Sort is O(1) since it only requires a constant amount of additional space for temporary storage.

## Advantages and Disadvantages

### Advantages

* **Simplicity:** Easy to understand and implement, making it suitable for beginners.
    
* **No Extra Space Required:** It sorts in place, requiring minimal additional memory.
    

### Disadvantages

* **Inefficiency for Large Datasets:** The O(n²) time complexity makes it unsuitable for large arrays.
    
* **Better Alternatives Exist:** More efficient sorting algorithms, such as Quick Sort and Merge Sort, outperform Bubble Sort.
    

## Real-World Applications

While Bubble Sort is not commonly used in production environments due to its inefficiency, it can be beneficial in specific scenarios:

* **Educational Purposes:** Often used to teach sorting algorithms and fundamental programming concepts.
    
* **Small Datasets:** For small or nearly sorted datasets, Bubble Sort may be sufficient.
    

## Conclusion

Bubble Sort is a simple yet essential algorithm that lays the groundwork for understanding more complex sorting techniques. Its straightforward approach to sorting helps beginners grasp fundamental concepts in algorithm design and analysis.

## Call to Action

We encourage you to implement Bubble Sort in your preferred programming language and experiment with sorting different datasets. As you become more comfortable with sorting algorithms, consider exploring more efficient options like Quick Sort and Merge Sort to deepen your understanding of algorithmic design.