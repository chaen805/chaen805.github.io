---
title: "[Swift] 프로그래머스 Lv.0 문제 - 2"
date: 2023-01-31 15:33:00 +0900
categories: [Problem Solving, swift]
tags: [swift, problem solving, programmers]
---

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
func solution(_ my_string:String, _ letter:String) -> String {
    return my_string.components(separatedBy: letter).joined()
    //return my_string.replacingOccurrences(of: letter, with: "")
    //return my_string.filter{String($0) != letter}
}
```
문자열 관련 메서드들 더 공부하기!!

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
func solution(_ age:Int) -> String {
    var ageStr = String(age).map{ Int(UnicodeScalar(String($0))!.value) }
    
//     print(UnicodeScalar("a").value) // 97
//     print(UnicodeScalar("0").value) // 48
                                  
    return ageStr.map{ String(UnicodeScalar($0+49)!) }.joined()
}
```
숫자 10개밖에 없는데 그냥 Array 만들어서 풀 걸.. 이라는 후회를 해봅니다.

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
func solution(_ n:Int) -> Int {
    var answer = 0
    var rt = Int(sqrt(Double(n)))
    for i in 1...rt {
        if n % i == 0 {
            answer += 1
        }
    }
    answer *= 2
    if rt * rt == n {
        answer -= 1
    }
    return answer
}
```

## 개미 군단
```swift
func solution(_ hp:Int) -> Int {
    var hp = hp
    var answer = 0
    // // 장군개미
    // answer += hp / 5
    // hp %= 5
    // // 병정개미
    // answer += hp / 3
    // hp %= 3
    // // 일개미
    // answer += hp
    
    for p in [5, 3, 1] {
        answer += hp / p
        hp %= p
    }

    return answer
}
```

## 모스부호 (1)
```swift
func solution(_ letter:String) -> String {
    let morse = [".-": "a", "-...": "b", "-.-.": "c", "-..": "d",
                 ".": "e", "..-.": "f", "--.": "g", "....": "h",
                 "..": "i", ".---": "j", "-.-": "k", ".-..": "l",
                 "--": "m", "-.": "n", "---": "o", ".--.": "p",
                 "--.-": "q", ".-.": "r", "...": "s", "-": "t",
                 "..-": "u","...-": "v", ".--": "w", "-..-": "x",
                 "-.--": "y", "--..": "z"]

    // var temp = letter.split(separator: " ").map{ String($0) }
    var temp = letter.components(separatedBy: " ")      //components를 사용하면 반환형이 String
    var answer = ""
    for m in temp {
        answer += morse[m]!
    }
    
    return answer
}
```

## 가위 바위 보
```swift
func solution(_ rsp:String) -> String {
    var win = ["2": "0", "0": "5", "5": "2"]
    return rsp.map{ win[String($0)]! }.joined()
}
```

## 구슬을 나누는 경우의 수
```swift
func solution(_ balls:Int, _ share:Int) -> Int {
    // var a = (balls - share + 1...balls).reduce(1, *)
    // var b = (1...share).reduce(1, *)
    
    var answer: Double = 1.0
    
    var a = Array((balls - share + 1...balls).map{ Double($0) }.reversed())
    var b = (1...share).map{ Double($0) }
    
    for i in 0..<share {
        answer *= a[i]
        answer /= b[i]
    }
    
    return Int(answer)
}
```
이게 제일 어려웠다.  
곱하기라 숫자 범위도 커지고 나눗셈에서 부동소수점도 고려해야해서 한 번에 모아서 계산하는 방식이 아닌,  
하나씩 꺼내서 누적 결과에 분자 부분 먼저 곱하고 분모를 그 뒤에 나누는 방식으로 계산해주었다.

## 점의 위치 구하기
```swift
func solution(_ dot:[Int]) -> Int {
    let x = dot[0]
    let y = dot[1]
    
    if x * y > 0 {
        guard x > 0 else { return 3 }
        return 1
    } else {
        guard x > 0 else { return 2 }
        return 4
    }
}
```

## 2차원으로 만들기
```swift
func solution(_ num_list:[Int], _ n:Int) -> [[Int]] {
    var answer: [[Int]] = []
    for i in 0..<(num_list.count / n) {
        answer.append(Array(num_list[n*i..<n*(i+1)]))
    }
    return answer
}
```
