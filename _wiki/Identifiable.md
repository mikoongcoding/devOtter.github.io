---
layout  : wiki
title   : 
summary : 
date    : 2022-03-13 14:57:51 +0900
updated : 2022-03-13 16:08:00 +0900
tags    : 
toc     : true
public  : true
parent  : 
latex   : false
---
* TOC
{:toc}

## You can make your data identifiable

>
Lists work with identifiable data. You can make your data identifiable in one of two ways: by passing along with your data a key path to a property that uniquely identifies each element, or by making your data type conform to the Identifiable protocol.
>

### id 사용

>
Passing a key path along with the data to List(_:id:).
Pass the key path to a uniquely identifying property for your collection’s elements as the second parameter when creating a List.
>

```swift
// LandmarkList.swift
var body: some View {
        List(landmarks, id: \.id) { landmark in
            LandmarkRow(landmark: landmark)
        }
}
```


### Identifiable protocol 사용

```swift
// Model > Landmark.swift
struct Landmark: Hashable, Codable, Identifiable {
...
```

```swift
// LandmarkList.swift
var body: some View {
    List(landmarks) { landmark in
        LandmarkRow(landmark: landmark)
    }
}
```

