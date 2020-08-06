# Bubble Sort
### 시간복잡도 
Best: O(n)  
Average: O(n^2)  
Worst: O(n^2)  

### CODE
```
var array: [Int] = []

let N: Int = Int(readLine()!)!

for _ in 0..<N {
    let num: Int = Int(readLine()!)!
    array.append(num)
}
var swapped: Bool
for i in 0..<(N - 1) {
    swapped = false
    for j in 0..<(N - 1 - i) {
        if array[j] > array[j + 1] {
            array.swapAt(j, j + 1)
            swapped = true
        }
    }
    
    if(!swapped) {
        break
    }
}
```
