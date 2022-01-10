---
layout  : wiki
title   : 
summary : 
date    : 2021-12-30 22:00:36 +0900
updated : 2021-12-31 19:40:27 +0900
tags    : 
toc     : true
public  : true
parent  : [[Swift]]
latex   : false
---
* TOC
{:toc}

# Associated Types

CaseIterable protocol을 확인하다가 associatedtype이라는 처음 보는게 나왔다.

``` Swift
public protocol CaseIterable {

    /// A type that can represent a collection of all values of this type.
    associatedtype AllCases : Collection = [Self] where Self == Self.AllCases.Element

    /// A collection of all values of this type.
    static var allCases: Self.AllCases { get }
}
```

휴 vimwiki 사용하기 꽤나 어렵네 ㅎㅎ
