# Merge Sort
### 시간복잡도
Best, Average, Worst: O(nlog n)  
  
### 과정
입력받은 Elements의 Array를 길이가 1이 될 때 까지 반으로 나눔.  
두 배열의 값들을 비교하여 작은 값을 앞으로 배치하며 하나의 배열로 만듬, 원래 길이가 될 때까지 반복.  
  
입력받은 Elements를 길이가 1이 될 때까지 반으로 나눈 후 병합할 때 크기 비교를 하여 새로운 배열을 만든다.  
새로만든 배열은 오름차순으로 정렬된 상태이므로 두 배열을 비교할 때 본인 배열을 신경쓸 필요없다.  

### CODE
```
func merge(arr: inout [Int], l: Int, m: Int, r: Int) {
    let n1: Int = m - l + 1
    let n2: Int = r - m
    
    var L = [Int](repeating: 0, count: n1)
    var R = [Int](repeating: 0, count: n2)
    
    for i in 0..<n1 {
        L[i] = arr[l + i]
    }
    
    for j in 0..<n2 {
        R[j] = arr[m + 1 + j]
    }
    
    var i: Int = 0
    var j: Int = 0
    var k: Int = l
    
    while(i < n1 && j < n2) {
        if(L[i] < R[j]) {
            arr[k] = L[i]
            i += 1
        } else {
            arr[k] = R[j]
            j += 1
        }
        k += 1
    }
    
    while(i < n1) {
        arr[k] = L[i]
        i += 1
        k += 1
    }
    
    while(j < n2) {
        arr[k] = R[j]
        j += 1
        k += 1
    }
}

func divide(arr: inout [Int], l: Int, r: Int) {
    if l < r {
        let m: Int = l + (r - l) / 2
        
        divide(arr: &arr, l: l, r: m)
        divide(arr: &arr, l: m + 1, r: r)
        
        merge(arr: &arr, l: l, m: m, r: r)
    }
}

func mergeSort(arr: inout [Int], l: Int, r: Int) {
    divide(arr: &arr, l: l, r: r)
}

var array: [Int] = []

let N: Int = Int(readLine()!)!

for _ in 0..<N {
    let num = Int(readLine()!)!
    array.append(num)
}

mergeSort(arr: &array, l: 0, r: N - 1)
```
