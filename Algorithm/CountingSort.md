# Counting Sort

### 원소간 비교없이 정렬

1. inputArray 배열 생성
2. inputArray 에 Element 입력
3. N = inputArray 배열의 크기
4. sortedArray 배열 N 크기로 생성
5. max = inputArray Element 의 최대 값 
6. countingArray 배열 max + 1 크기로 생성
7. countingArray 배열에 inputArray 배열의 Element 의 count 값 저장
8. inputArray 배열의 마지막 원소부터 시작 해서 인덱스 값이 작아지는 방향으로 안정정렬
9. x = inputArray[N - 1]
10. countingArray[x] -= 1
11. sortedArray[countingArray[x]] = x
12. inputArray 배열의 모든 값을 방문하여 위 과정 반복 
