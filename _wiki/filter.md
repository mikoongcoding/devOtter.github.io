---
layout  : wiki
title   : 
summary : 
date    : 2022-03-17 22:07:10 +0900
updated : 2022-03-17 22:46:59 +0900
tags    : 
toc     : true
public  : true
parent  : 
latex   : false
---
* TOC
{:toc}

## filter 예시 코드

```swift
struct LandmarkList: View {
    @State private var showFavoritesOnly = false

    var filteredLandmarks: [Landmark] {
        landmarks.filter { landmark in
            (!showFavoritesOnly || landmark.isFavorite)
        }
    }
```

예제 : [SwiftUI Tutorials](https://developer.apple.com/tutorials/swiftui/handling-user-input)
