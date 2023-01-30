---
title: "[Swift] 프로그래머스 Lv.0 문제 - 2"
date: 2023-01-30 16:08:00 +0900
categories: [Problem Solving, swift]
tags: [swift, problem solving, programmers]
---

### ~~수정중~~

> ❤️‍🔥 프로그래머스 Lv. 0 문제로 Swift와 친해지기!

**```import Foundation``` 생략**

## 나이 출력
```swift
func solution(_ age:Int) -> Int {
    return 2023 - age
}
```

## 배열 뒤집기
```swift
func solution(_ num_list:[Int]) -> [Int] {
    return num_list.reversed()
}
```

## 문자열 뒤집기
```swift
func solution(_ my_string:String) -> String {
    return String(my_string.reversed())
}
```

## 직각삼각형 출력하기
```swift
let n = readLine()!.components(separatedBy: [" "]).map { Int($0)! }

for i in 1...n[0] {
    print(String(repeating: "*", count: i))
}
```

## 짝수 홀수 개수
```swift
func solution(_ num_list:[Int]) -> [Int] {
    var evenCount = num_list.filter{ $0 % 2 == 0 }.count
    return [evenCount, num_list.count - evenCount]
}
```

## 문자 반복 출력하기
```swift
func solution(_ my_string:String, _ n:Int) -> String {
    var answer: String = ""
    my_string.forEach { char in
        answer.append(String(repeating: char, count: n))
    }
    return answer
}
```

## 특정 문자 제거하기
```swift

```

## 각도기
```swift
func solution(_ angle:Int) -> Int {
    if angle < 90 {
        return 1
    } else if angle == 90 {
        return 2
    } else if angle < 180 {
        return 3
    } else { return 4}
}
```

## 양꼬치
```swift
func solution(_ n:Int, _ k:Int) -> Int {
    var price = n * 12000 + (k - n / 10) * 2000
    return price
}
```

## 짝수의 합
```swift
func solution(_ n:Int) -> Int {
    var list = Array(1...n)
    return list.filter{ $0 % 2 == 0 }.reduce(0, +)
}
```

## 배열 자르기
```swift
func solution(_ numbers:[Int], _ num1:Int, _ num2:Int) -> [Int] {
    return Array(numbers[num1...num2])
}
```

## 외계행성의 나이
```swift

```

## 진료순서 정하기
```swift
func solution(_ emergency:[Int]) -> [Int] {
    var turn = emergency.sorted(by: {$0 > $1})
    var answer: [Int] = []
    for e in emergency {
        answer.append(turn.index(of: e)! + 1)
    }
    return answer
}
```

## 순서쌍의 개수
```swift

```

## 개미 군단
```swift

```

## 모스부호 (1)
```swift

```

## 가위 바위 보
```swift

```

## 구슬을 나누는 경우의 수
```swift

```

## 점의 위치 구하기
```swift

```

## 2차원으로 만들기
```swift

```
