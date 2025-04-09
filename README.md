<h1>Bubble Sort Algorithm</h1>
 <h2>Bubble Sort is the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they are in the wrong order. This algorithm is not suitable for large data sets as its average and worst-case time complexity are quite high.
 </h2>

- We sort the array using multiple passes. After the first pass, the maximum element goes to end (its correct position). Same way, after second pass, the second largest element goes to second last position and so on.
- In every pass, we process only those elements that have already not moved to correct position. After k passes, the largest k elements must have been moved to the last k positions.
- In a pass, we consider remaining elements and compare all adjacent and swap if larger element is before a smaller element. If we keep doing this, we get the largest (among the remaining elements) at its correct 
  position.


## How does Bubble Sort Work?
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20240925153535/bubble-sort-1.webp">
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20240925153536/bubble-sort-2.webp">
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20240925153536/bubble-sort-3.webp">

```
#include <bits/stdc++.h>
using namespace std;

// An optimized version of Bubble Sort 
void bubbleSort(vector<int>& arr) {
    int n = arr.size();
    bool swapped;
  
    for (int i = 0; i < n - 1; i++) {
        swapped = false;
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
                swapped = true;
            }
        }
      
        // If no two elements were swapped, then break
        if (!swapped)
            break;
    }
}

// Function to print a vector
void printVector(const vector<int>& arr) {
    for (int num : arr)
        cout << " " << num;
}

int main() {
    vector<int> arr = { 64, 34, 25, 12, 22, 11, 90 };
    bubbleSort(arr);
    cout << "Sorted array: \n";
    printVector(arr);
    return 0;
}

```

<h2>Output</h2>

```
Sorted array: 
 11 12 22 25 34 64 90
```
<h2>Complexity Analysis of Bubble Sort:</h2>
Time Complexity: O(n2)
<br>
Auxiliary Space: O(1)
