---
layout  : wiki
title   : 
summary : 
date    : 2022-03-16 22:01:00 +0900
updated : 2022-03-17 22:46:59 +0900
tags    : 
toc     : true
public  : true
parent  : [[iOS]]
latex   : false
---
* TOC
{:toc}

## ObservableObject

```swift
final class ModelData: ObservableObject {

}
```

>
SwiftUI subscribes to your observable object, and updates any views that need refreshing when the data changes.
>

## Add the @Published attribute

```swift
final class ModelData: ObservableObject {
    @Published var landmarks: [Landmark] = load("landmarkData.json")
}
```

>
An observable object needs to publish any changes to its data, so that its subscribers can pick up the change.
>

## Adopt the Model Object in Your Views

add an `@EnvironmentObject` property declaration to the view, and an `environmentObject(_:)` modifier to the preview.

```swift
struct LandmarkList: View {
    @EnvironmentObject var modelData: ModelData
```

## Update the ContentView.swift

Update the ContentView preview to add the model object to the environment, which makes the object available to any subview.

```swift
struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
            .environmentObject(ModelData())
    }
}
```

## Update the app instance

you’ll update the app instance to put the model object in the environment when you run the app in the simulator or on a device.

Update the LandmarksApp to create a model instance and supply it to ContentView using the environmentObject(_:) modifier.

### StateObject

>
Use the @StateObject attribute to initialize a model object for a given property only once during the life time of the app. This is true when you use the attribute in an app instance, as shown here, as well as when you use it in a view.
>

```swift
import SwiftUI

@main
struct LandmarksApp: App {
    @StateObject private var modelData = ModelData()

    var body: some Scene {
        WindowGroup {
            ContentView()
                .environmentObject(modelData)
        }
    }
}
```


## Which of the following passes data downward in the view hierarchy?

The environmentObject(_:) modifier.

You apply this modifier so that views further down in the view hierarchy can read data objects passed down through the environment.

The @EnvironmentObject attribute.

You use this attribute in views that are lower down in the view hierarchy to receive data from views that are higher up.
