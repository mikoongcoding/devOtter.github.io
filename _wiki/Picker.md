---
layout  : wiki
title   : 
summary : 
date    : 2022-02-23 20:52:21 +0900
updated : 2022-02-23 22:03:12 +0900
tags    : 
toc     : true
public  : true
parent  : 
latex   : false
---
* TOC
{:toc}

## Picker 예시코드
```swift
		Picker("Pick Input Unit", selection: $inputUnit){
                        ForEach(0..<lengthUnits.count) {
                            Text(self.lengthUnits[$0])
                        }
                        .pickerStyle(.segmented)
                }
```
