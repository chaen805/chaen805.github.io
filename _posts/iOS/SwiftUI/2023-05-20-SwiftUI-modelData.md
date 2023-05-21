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
앱에서는 일반적으로 UI 혹은 다른 로직들과 분리된 데이터 모델을 이용하여 데이터를 저장하고 처리한다.  

전통적으로 모델과 UI 사이 데이터 이동을 위해서는 뷰 컨트롤러를 사용한다. 그러나 SwiftUI는 이러한 동기화의 대부분을 처리한다. 데이터가 변경될 때 뷰를 업데이트 하려면 데이터 모델 클래스를 observable object로 만들고 프로퍼티들을 publish하고, special attribuetes를 이용해 해당 인스턴스를 선언한다.  
이러한 기능을 함께 사용하면 데이터에 대한 단일 source of truth를 유지하는데 도움이 된다.  

## @StateObject

A property wrapper type that instantiates an observable object.

- 뷰 계층 구조에 저장하는 참조 타입의 단일 source of truth로써 state object를 사용한다.
  ObservableObject 프로토콜을 준수하는 state object를 생성한다.
  
- ~~SwiftUI가 제공하는 스토리지 관리와 충돌할 수 있는 memberwise initializer에서 이 변수를 설정하는 것을 방지하기 위해(아직 이해 못함..)~~ State object는 private로 선언해야 한다.

## @ObservedObject
A property wrapper type that subscribes to an observable object and invalidates a view whenever the observable object changes.  

- 매개변수에 대해 입력이 ObservableObject이고 객체의 속성이 변경될 때 뷰가 업데이트 되기를 원하는 경우 ObservedObject로 속성을 추가한다.
    
    일반적으로 StateObject를 하위 뷰로 전달하기 위해 사용된다.
    
- ObservableObject의 속성 중 하나가 변경되면 객체에 종속된 모든 뷰를 업데이트한다.

## : ObservableObject (protocol)

A type of object with a publisher that emits before the object has changed.   

- 기본적으로 ObservableObject는 @Published 프로퍼티가 변경되기 전에 변경된 값을 내보내는 objectWillChange 퍼블리셔를 자동으로 생성한다.
