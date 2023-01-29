---
title: "[Swift] 프로그래머스 Lv.0 문제 - 1"
date: 2023-01-30 00:40:00 +0900
categories: [Problem Solving, swift]
tags: [swift, problem solving, programmers]
---

~~수정중~~

> ❤️‍🔥 프로그래머스 Lv. 0 문제로 Swift와 친해지기!

코딩테스트 입문 100제를 푸는 포스팅입니다.
20문제씩 총 5개의 게시글이 올라갈 예정입니다.

**```import Foundation``` 생략**

## 중복된 숫자 개수
```swift
import Foundation

// where절 사용
func solution(_ array:[Int], _ n:Int) -> Int {
    var result = 0
    
    for i in array where i == n { result += 1 }
    
    return result
}
// filter 사용
func solution(_ array:[Int], _ n:Int) -> Int {
    return array.filter{ $0 == n }.count
}
```

## 머쓱이보다 키 큰 사람
```swift
import Foundation

// where절 사용
func solution(_ array:[Int], _ height:Int) -> Int {
    var result = 0
    
    for h in array where h > height { result += 1 }
    
    return result   
}
// filter 사용
func solution(_ array:[Int], _ height:Int) -> Int {
    return array.filter{ $0 > height }.count
}
```

## 두 수의 차
```swift
import Foundation

func solution(_ num1:Int, _ num2:Int) -> Int {
    return num1 - num2
}
```

## 두 수의 곱
```swift
func solution(_ num1:Int, _ num2:Int) -> Int {
    return num1 * num2
}
```

## 몫 구하기
```swift
func solution(_ num1:Int, _ num2:Int) -> Int {
    return  num1 / num2
}
```

## 두 수의 나눗셈
```swift
func solution(_ num1:Int, _ num2:Int) -> Int {
    return num1 * 1000 / num2
}
```

## 숫자 비교하기
```swift
// guard문 이용
func solution(_ num1:Int, _ num2:Int) -> Int {
    guard num1 == num2 else { return -1 }
    return 1
}
// 삼항연산자 이용
func solution(_ num1:Int, _ num2:Int) -> Int {
    return num1 == num2 ? 1 : -1
}
```

## 분수의 덧셈
```swift

```

## 배열 두 배 만들기
```swift

```

## 나머지 구하기
```swift

```

## 중앙값 구하기
```swift

```

## 최빈값 구하기
```swift

```

## 짝수는 싫어요
```swift

```

## 피자 나눠 먹기 (1)
```swift

```

## 피자 나눠 먹기 (2)
```swift

```

## 피자 나눠 먹기 (3)
```swift

```

## 배열의 평균값
```swift

```

## 웃기게 할인 받기
```swift

```

## 아이스 아메리카노
```swift

```
