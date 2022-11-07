---
title: "SwiftUI - Add Settings View for APP"
date: 2022-11-07T21:40:10+08:00
categories: ['SwiftUI']
tags: ['']
draft: false
---

To add a settings/preferences view for a SwiftUI project is really straightforward and easy.

First define a view for preferences

```swift
struct SettingsView: View {
    var body: some View {
        TabView {
            Text("General")
                .tabItem {
                    Label("General", systemImage: "gear")
                }
            Text("Advanced")
                .tabItem() {
                    Label("Advanced", systemImage: "pencil")
                }
        }
        .frame(width: 300, height: 150)
    }
}
```

Then add this view to the app.

```swift
@main
struct testApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        #if os(macOS)
        Settings {
            SettingsView()
        }
        #endif
    }
}
```

Result

![2022-11-07-pZnCps](https://raw.githubusercontent.com/yistc/images-for-blog-1/main/blog/2022-11-07-pZnCps.png)

![2022-11-07-J77tkJ](https://raw.githubusercontent.com/yistc/images-for-blog-1/main/blog/2022-11-07-J77tkJ.png)

