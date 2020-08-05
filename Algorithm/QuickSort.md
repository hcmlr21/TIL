# Quick Sort
### 시간복잡도
Best, Average :O(n^2)
Worst: O(n^2)

### 특징 
Divide And Conquer

### CODE
```
func partition(_ arr: inout [Int], _ l: Int, _ r: Int) -> Int {
    //마지막 인덱스 기준
    let pivot = arr[r]
    
    var i = l - 1
    for j in l..<r {
        if arr[j] < pivot {
            i += 1
            arr.swapAt(i, j)
        }
    }
    arr.swapAt(i + 1, r)
    return i + 1
}

func quickSort(_ arr: inout [Int], _ l: Int, _ r: Int) {
    if(l < r) {
        let pivotIndex = partition(&arr, l, r)
        
        quickSort(&arr, l, pivotIndex - 1)
        quickSort(&arr, pivotIndex + 1, r)
    }
}
```
