# Overlapping IntervalsSolved

- **Platform:** GeeksforGeeks
- **Difficulty:** `Medium`
- **Solved Date:** Sep 14, 2026

---

## 💻 Solution Code
```cpp
class Solution {
    public ArrayList<ArrayList<Integer>> mergeOverlap(int[][] arr) {
        
        // sorting the array
        Arrays.sort(arr, (a,b) -> Integer.compare(a[0], b[0]));
        
        // logic to find overlap
        
        
        ArrayList<ArrayList<Integer>> list = new ArrayList<>();
        int low = arr[0][0];
        int high = arr[0][1];
        
        for(int i = 1; i < arr.length; i++){
            
            int a = arr[i][0];
            int b = arr[i][1];
            
            if(a <= high){
                low = Math.min(low, a);
                high = Math.max(high, b);
            }else{
                list.add(new ArrayList<>(Arrays.asList(low, high)));
                low = a;
                high = b;
            }
            
        }
        list.add(new ArrayList<>(Arrays.asList(low, high)));
        
        return list;
    }
}
```

---
*Auto-synced by [SyncTool](https://github.com).*
