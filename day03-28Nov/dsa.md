# Day 3 — DSA

**Topic:** Arrays

---

## 1. Find duplicate elements in an array.

### Answer

### Explanation

  

 

**Approach**

- Compare each number with every number that comes after it.
- When two numbers match, that value is a duplicate.
- Only the original array is read, so no extra array is used.

**Pattern:** The nested loop pattern is used.

**Time complexity:** O(n²)

**Space complexity:** O(1)

### Code

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

    vector<int> arr = {1, 2, 3, 2, 4, 5, 1};

    for(int i=0; i<arr.size(); i++){
        for(int j=i+1; j<arr.size(); j++){
            if(arr[i]==arr[j]){
                cout<<arr[j];
            }
        }
    }

    return 0;
}
```

---

## 2. Move all zeros to the end of an array.

### Answer

### Explanation

  

 

**Approach**

- Keep one pointer on the next spot that should hold a non-zero number.
- Walk through the array and swap each non-zero into that spot, then move the pointer forward.
- Zeros stay behind in the same array, so they end up at the end.

**Pattern:** The two pointers pattern is used.

**Time complexity:** O(n)

**Space complexity:** O(1)

### Code

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

    vector<int> arr = {0, 1, 0, 3, 12};

    int j = 0;

    for (int i = 0; i < arr.size(); i++) {
        if (arr[i] != 0) {
            swap(arr[i], arr[j]);
            j++;
        }
    }

    for (int num : arr) {
        cout << num << " ";
    }

    return 0;
}
```

---
