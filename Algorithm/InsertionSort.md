# Insertion Sort
### 시간복잡도: O(n^2)

시간 복잡도가 O(n^2) 인 정렬 중에 가장 빠른 정렬.  
  
배열의 1번 인덱스부터 시작  
시작 인덱스에서 인덱스 값이 작아지는 방향으로 반복  
인접한 값 중 인덱스 값이 큰 배열의 값이 작을 경우 두 값을 바꾸어줌  
그렇지않을경우 반복문 break


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
