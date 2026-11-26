# Day 1 — DSA

**Topic:** Arrays

---

## 1. Find the largest and smallest element in an array.

### Answer

### Explanation

  

 

**Approach**

- Start one pointer at the beginning of the array and one at the end.
- Compare those two values and keep the biggest and the smallest seen so far.
- Move both pointers toward the middle and stop when they meet.

**Pattern:** The two pointers pattern is used.

**Time complexity:** O(n)

**Space complexity:** O(1)

### Code

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

    vector<int> arr = {10, 5, 20, 8, 15};

    int larg = arr[0];
    int smal = arr[0];

    int left = 0;
    int right = arr.size() - 1;

    for (left = 0; left <= right; left++) {

        if (arr[left] > arr[right]) {
            if (arr[left] > larg)
                larg = arr[left];
        } else {
            if (arr[right] > larg)
                larg = arr[right];
        }

        if (arr[left] < arr[right]) {
            if (arr[left] < smal)
                smal = arr[left];
        } else {
            if (arr[right] < smal)
                smal = arr[right];
        }

        right--;
    }

    cout << "Largest = " << larg << endl;
    cout << "Smallest = " << smal << endl;

    return 0;
}
```

---

## 2. Find the second-largest element without sorting.

### Answer

### Explanation

**Approach**

- Go through the array once and remember the biggest number.
- Also remember the next biggest number, as long as it is not the same as the biggest.
- If every number is the same, there is no second largest.

**Pattern:** The single pass pattern is used.

**Time complexity:** O(n)

**Space complexity:** O(1)

### Code

```cpp
#include <iostream>
#include <vector>
#include <climits>
using namespace std;

int main() {

    vector<int> arr = {10, 10, 10};

    int largest = INT_MIN;
    int secLarge = INT_MIN;

    for (int i = 0; i < arr.size(); i++) {
        if (secLarge < arr[i] && largest != arr[i]) {
            secLarge = arr[i];
            if (largest < secLarge) {
                secLarge = largest;
                largest = arr[i];
            }
        }
    }

    cout << "Largest = " << largest << endl;

    if (secLarge == INT_MIN) {
        cout << "Second Largest = Does not exist" << endl;
    }
    else {
        cout << "Second Largest = " << secLarge << endl;
    }

    return 0;
}
```

---

## 3. Reverse an array without using another array.

### Answer

### Explanation

**Approach**

- Start one pointer at the first element and one at the last element.
- Swap those two values, then move both pointers toward the middle.
- Stop when the pointers meet. The same array is reversed, so no extra array is used.

**Pattern:** The two pointers pattern is used.

**Time complexity:** O(n)

**Space complexity:** O(1)

### Code

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

    vector<int> arr = {10, 20, 30, 40, 50};
    int swap = 0;
    int j = arr.size() - 1;

    for (int i = 0; i <= j; i++) {
        swap = arr[j];
        arr[j] = arr[i];
        arr[i] = swap;
        j--;
    }

    for (int num : arr) {
        cout << num << " ";
    }

    return 0;
}
```

---
