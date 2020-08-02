# Insertion Sort
### 시간복잡도: O(n^2)

시간 복잡도가 O(n^2) 인 정렬 중에 가장 빠른 정렬.

```
var array: [Int] = []

let N: Int = Int(readLine()!)!

for _ in 0..<N {
    let num = Int(readLine()!)!
    array.append(num)
}

for i in 1..<N {
    for j in (1...i).reversed() {
        if array[j - 1] > array[j] {
            array.swapAt(j, j - 1)
        } else {
            break
        }
    }
}
```
