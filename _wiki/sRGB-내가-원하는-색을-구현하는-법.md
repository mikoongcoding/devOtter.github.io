---
layout  : wiki
title   : 
summary : 
date    : 2022-01-17 21:43:12 +0900
updated : 2022-03-10 21:38:22 +0900
tags    : 
toc     : true
public  : true
parent  : [[iOS]]
latex   : false
---
* TOC
{:toc}

# Digital Color Meter 이용하여 sRGB 퍼센트값 추출하기
## mac OS 내장 프로그램인 Digital Color Meter 디지털 컬러 측정기를 사용하여 RGB 색상값을 추출한다.

1. Spotlight Search에서 Digital Color Meter를 검색하여 프로그램을 실행한다.

2. Digital Color Meter를 실행한 상태에서 상단 메뉴 중 View > Display Values > as Percentage로 변경한다.

3. 해당 값을 코드에 적용한 것 :
```
LinearGradient(colors: [Color(red:0.83, green: 0.98, blue: 0.96)], startPoint: .top, endPoint: .bottom)
                .ignoresSafeArea()
```
