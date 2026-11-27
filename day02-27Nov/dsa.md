# Day 2 — DSA

**Topic:** Arrays

---

## 1. Remove duplicates from a sorted array.

### Answer

### Explanation

  

 

**Approach**

- Keep one pointer on the last unique number.
- Move a second pointer through the rest of the sorted array.
- When a new number appears, write it next to the unique numbers and move the first pointer forward.

**Pattern:** The two pointers pattern is used.

**Time complexity:** O(n)

**Space complexity:** O(1)

### Code

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

    vector<int> arr = {1, 1, 2, 2, 3, 4, 4, 5};
    int i = 0;

    for (int j = 1; j < arr.size(); j++) {
        if (arr[j] == arr[i]) {
            continue;
        } else {
            i++;
            arr[i] = arr[j];
        }
    }

    for (int k = 0; k <= i; k++) {
        cout << arr[k] << " ";
    }

    return 0;
}
```

---

## 2. Find the missing number from an array containing numbers from 1 to N.

### Answer

### Explanation

  

 

**Approach**

- Add up every number that is present in the array.
- The full sum from 1 to N is N times (N + 1), divided by 2.
- Subtract the array sum from that full sum. The difference is the missing number.

**Pattern:** The sum formula pattern is used.

**Time complexity:** O(n)

**Space complexity:** O(1)

### Code

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

    vector<int> arr = {1, 2, 4, 5};
    int N = 5;

    int actualSum = 0;
    for (int num : arr) {
        actualSum += num;
    }

    int expectedSum = N * (N + 1) / 2;

    int missingNumber = expectedSum - actualSum;

    cout << "Missing Number: " << missingNumber << endl;

    return 0;
}
```

---
