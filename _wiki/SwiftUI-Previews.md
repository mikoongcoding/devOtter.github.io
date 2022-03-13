---
layout  : wiki
title   : 
summary : 
date    : 2022-03-13 14:07:46 +0900
updated : 2022-03-13 14:14:45 +0900
tags    : 
toc     : true
public  : true
parent  : 
latex   : false
---
* TOC
{:toc}

## When you add the landmark property, the preview stops working
because the LandmarkRow type needs a landmark instance during initialization.

<img width="1512" alt="Screen Shot 2022-03-13 at 13 30 18" src="https://user-images.githubusercontent.com/50915397/158045570-ee3a25dc-f5e1-4478-8d52-d92532ff4623.png">

To fix the preview, you’ll need to modify the preview provider.

In the previews static property of LandmarkRow_Previews, add the landmark parameter to the LandmarkRow initializer, specifying the first element of the landmarks array.

```swift
struct LandmarkRow_Previews: PreviewProvider {
    static var previews: some View {
        LandmarkRow(landmark: landmarks[0])
    }
}
```

## Customize the Row Preview

```swift
struct LandmarkRow_Previews: PreviewProvider {
    static var previews: some View {
        Group {
            LandmarkRow(landmark: landmarks[0])
            LandmarkRow(landmark: landmarks[1])
        }
        .previewLayout(.fixed(width: 300, height: 70))
    }
}
```

The code you write in a preview provider only changes what Xcode displays in the canvas.

## Links
[SwiftUI Tutorials] (https://developer.apple.com/tutorials/swiftui/building-lists-and-navigation#Customize-the-Row-Preview)


