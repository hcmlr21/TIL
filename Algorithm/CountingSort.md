# Counting Sort
### 시간복잡도: O(n)
  
### 원소간 비교없이 정렬

1. inputArray 배열 생성
2. inputArray 에 Element 입력
3. N = inputArray 배열의 크기
4. sortedArray 배열 N 크기로 생성
5. max = inputArray Element 의 최대 값 
6. countingArray 배열 max + 1 크기로 생성
7. countingArray 배열에 inputArray 배열의 Element 의 count 값 저장
8. countingArray[i] 에 counting[i - 1] 값 을 더해서 저장
9. inputArray 배열의 마지막 원소부터 시작 해서 인덱스 값이 작아지는 방향으로 안정정렬
10. x = inputArray[N - 1]
11. countingArray[x] -= 1
12. sortedArray[countingArray[x]] = x
13. inputArray 배열의 모든 값을 방문하여 위 과정 반복 

### CODE
```
var array:[Int] = []
var MAX = 0

let N: Int  = Int(readLine()!)!

for _ in 0..<N { // 입력
    let num: Int = Int(readLine()!)!
    array.append(num)
    if num > MAX {
        MAX = num
    }
}

var sortedArray = [Int](repeating: 0, count: N)
var countingArray = [Int](repeating: 0, count: MAX + 1)

for num in array { // 카운팅
    countingArray[num] += 1
}

for i in 1..<countingArray.count { // 누적 합
    countingArray[i] += countingArray[i - 1]
}

for i in (0..<N).reversed() { // 안정정렬
    let index = array[i]
    countingArray[index] -= 1
    let newIndex = countingArray[index]
    sortedArray[newIndex] = index
}
```
