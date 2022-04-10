---
layout  : wiki
title   : 
summary : 
date    : 2022-04-10 17:21:13 +0900
updated : 2022-04-10 17:28:38 +0900
tags    : 
toc     : true
public  : true
parent  : 
latex   : false
---
* TOC
{:toc}

## guard
조건이 `true`인지 아닌지 체크하는 Swift 문법이다.

`true`가 아니라면(`false`이면) 강제적으로 즉시 현재 범위를 exit해준다.

### guard let
보통 `guard let`으로 사용된다. optional이 값을 갖고 있는지 체크한다.

값을 갖고 있으면 안전하게 사용되도록 상수를 생성한다.

optional에 값이 없으면 `guard`가 해당 범위를 exit하도록 만든다.

```swift
    guard let fileUrl = Bundle.main.url(forResource: filename, withExtension: nil)
    else {
        fatalError("Couldn't find \(filename) in main bundle")
    }

```

## Links
[Hacking With Swift](https://www.hackingwithswift.com/glossary)

