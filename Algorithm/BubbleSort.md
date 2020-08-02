# Bubble Sort
### 시간복잡도: O(n^2)

1. array 에 Element 입력

```
var array: [Int] = []

let N: Int = Int(readLine()!)!

for _ in 0..<N {
    let num: Int = Int(readLine()!)!
    array.append(num)
}

for i in 0..<(N - 1) {
    for j in 0..<(N - 1 - i) {
        if array[j] > array[j + 1] {
            array.swapAt(j, j + 1)
        }
    }
}
```
