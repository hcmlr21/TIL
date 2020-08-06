# Selection Sort
### 시간 복잡도 
Best, Average, Worst: O(n^2)  

### 특징
배열을 처음부터 끝까지 돌며 가장 큰 값을 찾고, 
배열의 가장 큰 값과 배열의 마지막 값을 바꿔준다.  

### CODE
```
func swap(a: inout Int, b: inout Int) {
    let temp: Int = a
    a = b
    b = temp
}

var array: [Int] = []

let N: Int = Int(readLine()!)!
var maxIndex: Int

for _ in 0..<N {
    let num: Int = Int(readLine()!)!
    array.append(num)
}

for i in 0..<(N - 1) {
    maxIndex = 0
    for j in 0..<(N - 1 - i) {
        if array[maxIndex] < array[j + 1] {
            maxIndex = j + 1
        }
    }
    array.swapAt(N - 1 - i, maxIndex)
}
```
