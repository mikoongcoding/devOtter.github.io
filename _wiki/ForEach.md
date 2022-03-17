---
layout  : wiki
title   : 
summary : 
date    : 2022-03-17 22:10:49 +0900
updated : 2022-03-17 22:46:59 +0900
tags    : 
toc     : true
public  : true
parent  : 
latex   : false
---
* TOC
{:toc}

## ForEach를 사용해야 할 때

>
Create a nested ForEach group to transform the landmarks into rows.

To combine static and dynamic views in a list, or to combine two or more different groups of dynamic views, use the ForEach type instead of passing your collection of data to List.
>

```swift
var body: some View {
        NavigationView {
            List(filteredLandmarks) { landmark in
                NavigationLink {
                    LandmarkDetail(landmark: landmark)
                } label: {
                    LandmarkRow(landmark: landmark)
                }
            }
            .navigationTitle("Landmarks")
        }
    }
```

Use the ForEach type

```swift
var body: some View {
        NavigationView {
            List {
                ForEach(filteredLandmarks) { landmark in
                    NavigationLink {
                        LandmarkDetail(landmark: landmark)
                    } label: {
                        LandmarkRow(landmark: landmark)
                    }
                }
            }
            .navigationTitle("Landmarks")
        }
    }
```
