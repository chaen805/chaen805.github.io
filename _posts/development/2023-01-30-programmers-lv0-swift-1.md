---
title: "[Swift] 프로그래머스 Lv.0 문제 - 1"
date: 2023-01-30 00:40:00 +0900
categories: [Problem Solving, swift]
tags: [swift, problem solving, programmers]
---

> ❤️‍🔥 프로그래머스 Lv. 0 문제로 Swift와 친해지기!

코딩테스트 입문 100제를 푸는 포스팅입니다.  
20문제씩 총 5개의 게시글이 올라갈 예정입니다.

**```import Foundation``` 생략**

## 중복된 숫자 개수
```swift
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
func gcd(_ x:Int, _ y:Int) -> Int {
    var a = x
    var b = y
    while b != 0 {
        var r = a % b
        a = b
        b = r
    }
    return a
}
func solution(_ numer1:Int, _ denom1:Int, _ numer2:Int, _ denom2:Int) -> [Int] {
    var numer = (numer1 * denom2) + (numer2 * denom1)
    var denom = denom1 * denom2
    var d = gcd(numer, denom)
    
    return [numer / d, denom / d]
}
```

## 배열 두 배 만들기
```swift
func solution(_ numbers:[Int]) -> [Int] {
    return numbers.map{ $0 * 2 }
}
```

## 나머지 구하기
```swift
func solution(_ num1:Int, _ num2:Int) -> Int {
    return num1 % num2
}
```

## 중앙값 구하기
```swift
func solution(_ array:[Int]) -> Int {
    var mid: Int = array.count / 2
    var temp = array.sorted()
    
    return temp[mid]
}
```

## 최빈값 구하기
```swift
func solution(_ array:[Int]) -> Int {
    var check: [Int: Int] = [:]
    for i in array {
        check[i, default: 0] += 1
    }
    var maxCount = check.max(by: {$0.value < $1.value})!.value
    var temp = check.filter({ $0.value == maxCount}).keys
    
    guard temp.count == 1 else { return -1 }
    return temp.first!
}
```

## 짝수는 싫어요
```swift
// where절 사용
func solution(_ n:Int) -> [Int] {
    var odd: [Int] = []
    for i in 1...n where i % 2 == 1 { odd.append(i) }
    return odd
}
//filter 사용
func solution(_ n:Int) -> [Int] {
    return odd
}
```

## 피자 나눠 먹기 (1)
```swift
func solution(_ n:Int) -> Int {
    return n % 7 == 0 ? n / 7 : n / 7 + 1
}
```

## 피자 나눠 먹기 (2)
```swift
func gcd(_ x:Int, _ y:Int) -> Int {
    var a = x
    var b = y
    while b != 0 {
        var r = a % b
        a = b
        b = r
    }
    return a
}

func lmc(_ a:Int, _ b:Int) -> Int {
    return a * b / gcd(a,b)
}


func solution(_ n:Int) -> Int {
    return lmc(n, 6) / 6
}
```

## 피자 나눠 먹기 (3)
```swift
func solution(_ slice:Int, _ n:Int) -> Int {
    return n / slice + (n % slice == 0 ? 0 : 1)
}
```

## 배열의 평균값
```swift
func solution(_ numbers:[Int]) -> Double {
    let sum: Int = numbers.reduce(0){ return $0 + $1 }
    return Double(sum) / Double(numbers.count)
}
```

## 옷가게 할인 받기
```swift
func solution(_ price:Int) -> Int {
    var answer: Double = 0.0
    if price >= 500000 {
        answer = Double(price) * 0.8
    } else if price >= 300000 {
        answer = Double(price) * 0.9
    } else if price >= 100000 {
        answer = Double(price) * 0.95
    } else { return price }
    return Int(answer)
}
```

## 아이스 아메리카노
```swift
func solution(_ money:Int) -> [Int] {
    let price = 5500
    return [money / price, money % price]
}
```
