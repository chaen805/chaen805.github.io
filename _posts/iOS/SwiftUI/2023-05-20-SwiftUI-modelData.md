---
title: "SwiftUI 공식 문서 - Model data"
date: 2023-05-20 18:13:00 +0900
categories: [iOS, SwiftUI]
tags: [iOS, swift, SwiftUI]
---

아카데미에서의 MC1, MC2 기간 동안 만나본 property wrapper들을 알아보기위해 공식 문서 살펴보기  

SwiftUI 공식 문서 - [Model data](https://developer.apple.com/documentation/swiftui/model-data)

# Creating and sharing view state

![](https://docs-assets.developer.apple.com/published/d98251c2fac9fc4f6843be1e4836cb93/Managing-User-Interface-State-1@2x.png)

## @State

A property wrapper type that can read and write a value managed by SwiftUI.

- ~~SwiftUI가 제공하는 스토리지 관리와 충돌할 수 있는 memberwise initializer에서 이 변수를 설정하는 것을 방지하기 위해(아직 이해 못함..)~~ State property는 private로 선언해야 한다.
- State로 선언된 변수가 변경되면 뷰를 새로 그리게 된다
- 값에 접근해야 하는 최상위 뷰에서 State property를 private로 선언하고 하위 뷰와 공유한다.
    
    읽기 전용 - 직접
    
    읽기 및 수정 - 바인딩
    

## @Binding

A property wrapper type that can read and write a value owned by a source of truth.

- 바인딩은 데이터를 직접 저장하는 대신 프로퍼티를 Source of Truth와 양방향 연결한다.
    
    상위 뷰에 있는 데이터 저장 프로퍼티(State property) - 데이터를 표시하고 변경하는 하위뷰
    
- 부모뷰에서 Source of Truth인 State property 앞에 $를 붙여 하위 뷰에 넘겨줄 수 있다

---

# Creating model data


# Distributing model data throughout your app
