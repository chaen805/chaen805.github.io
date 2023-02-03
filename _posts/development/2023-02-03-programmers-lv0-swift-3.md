---
title: "[Swift] 프로그래머스 Lv.0 문제 - 3"
date: 2023-02-03 17:10:00 +0900
categories: [Problem Solving, swift]
tags: [swift, problem solving, programmers]
---

### ~~수정중~~

> ❤️‍🔥 프로그래머스 Lv. 0 문제로 Swift와 친해지기!

**```import Foundation``` 생략**

## 공 던지기
```swift
func solution(_ numbers:[Int], _ k:Int) -> Int {
    var temp = 2 * k - 1
    var n = numbers.count
    
    return temp % n == 0 ? n : temp % n
}
```

## 배열 회전시키기
```swift
func solution(_ numbers:[Int], _ direction:String) -> [Int] {
    var answer = numbers
    if direction == "right" {
        answer.insert(answer.popLast()!, at: 0)
    } else {
        answer.append(answer.removeFirst())
    }
    return answer
}
```

## 주사위의 개수
```swift

```

## 합성수 찾기
```swift

```

## 최댓값 만들기(1)
```swift
func solution(_ numbers:[Int]) -> Int {
    let temp = numbers.sorted(by: { $0 > $1 })
    
    return temp[0] * temp[1]
}
```

## 팩토리얼
```swift
func solution(_ n:Int) -> Int {
    var temp = 1
    for i in 1...10 {
        temp *= i
        if temp > n { return i - 1 }
    }
    return 10
}
```

## 모음 제거
```swift
func solution(_ my_string:String) -> String {
    let vowels = ["a", "e", "i", "o", "u"]
    /* var answer = ""
    for c in my_string.map{ String($0) } {
        if vowels.contains(c) { continue }
        else { answer += c }
    }
    return answer */
    return my_string.filter{ !vowels.contains(String($0)) }

}
```

## 문자열 정렬하기 (1)
```swift
func solution(_ my_string:String) -> [Int] {
    return my_string.compactMap{ Int(String($0)) }.sorted()
}
```

## 숨어있는 숫자의 덧셈 (1)
```swift
func solution(_ my_string:String) -> Int {
    // 내가 쓴 답
    return my_string.filter({ $0.isNumber }).map({ Int(String($0))! }).reduce(0, +)
    // 다른 사람 풀이
    return my_string.compactMap{ Int(String($0)) }.reduce(0,+)
}
```
compactMap을 사용하면  
1. nil 제거  
2. 옵셔널 바인딩  
한 번에 가능!!

## 소인수분해
```swift
 
```

## 컨드롤 제트
```swift
 
```

## 배열 원소의 길이
```swift
 
```

## 직사각형 넓이 구하기
```swift
 
```

## 캐릭터의 좌표
```swift
 
```

## 최댓값 만들기 (2)
```swift
func solution(_ numbers:[Int]) -> Int {
    let temp = numbers.sorted()
    let maxIdx = numbers.count - 1
    return max(temp[0] * temp[1], temp[maxIdx] * temp[maxIdx - 1])
}
```

## 다항식 더하기
```swift
 
```

## 숨어있는 숫자의 덧셈 (2)
```swift
 
```

## 안전지대
```swift
 
```

## 삼각형의 완성조건 (2)
```swift
 
```

## 외계어 사전
```swift
 
```
