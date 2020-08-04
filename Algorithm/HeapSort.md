# Heap Sort
### 시간복잡도: O(nlog n)

#### Definition
힙(Heap)을 이용한 정렬 
  
### 힙(Heap) 이란?  
아래 두 가지 성질을 만족하는 자료구조
1. 구조적 성질: 완전이진트리
2. 순서적 성질: 부모와 자식 노드간의 대소관계(최대 힙, 최소 힙)  

### 순서(최소 힙 기준)
1. Insert Elements
2. Delete로 인해 반환 된 Element를 배열에 추가 


### CODE
```
class HeapNode {
    var parent: HeapNode?
    var leftChild: HeapNode?
    var rightChild: HeapNode?
    var elemnet: Int
    
    init(element: Int) {
        self.elemnet = element
    }
}

class Heap {//최소 힙
    var array: [HeapNode] = [HeapNode(element: 0)] // index가 1부터 시작하기 위함
    var rootNode: HeapNode?
    
    func swapElement(arr: inout [HeapNode], index1: Int, index2: Int) {
        let tempElement = arr[index1].elemnet
        arr[index1].elemnet = arr[index2].elemnet
        arr[index2].elemnet = tempElement
    }
    
    func insertion(newNode: HeapNode) {
        if self.array.count == 1 {
            self.array.append(newNode)
            self.array[self.array.count - 1] = newNode
            self.rootNode = newNode
        } else {
            self.array.append(newNode)
            self.array[self.array.count - 1] = newNode
            
            //업 힙
            var index = array.count - 1 //index가 1부터시작하기 때문
            while(index > 1) {
                let parentIndex: Int = index / 2
                if(array[parentIndex].elemnet > array[index].elemnet) {
                    self.swapElement(arr: &self.array, index1: parentIndex, index2: index)
                    index = parentIndex
                } else {
                    break
                }
            }
        }
    }
    
    func deletion() -> HeapNode {
        self.swapElement(arr: &self.array, index1: 1, index2: self.array.endIndex - 1)
        let deletedNode = self.array.remove(at: self.array.endIndex - 1)
        
        //다운 힙
        var index = 1
        while(index < self.array.count) {
            let leftChildIndex = index * 2
            let rightChildIndex = index * 2 + 1
            var smallerChildIndex: Int?
            
            if rightChildIndex < self.array.count {
                smallerChildIndex = self.array[leftChildIndex].elemnet < self.array[rightChildIndex].elemnet ? leftChildIndex : rightChildIndex
            } else if leftChildIndex < self.array.count {
                smallerChildIndex = leftChildIndex
            }
            
            guard let childIndex = smallerChildIndex else {
                break
            }
            
            if(array[childIndex].elemnet < array[index].elemnet) {
                self.swapElement(arr: &self.array, index1: childIndex, index2: index)
                index = childIndex
            } else {
                break
            }
        }
        
        return deletedNode
    }
}
```
