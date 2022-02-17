```
Info => LaunchScreen => launch-screen-image ( Image Name )
Info => LaunchScreen => launch-screen-color ( Background Color )
```

```
Bundle version string (short) => Appearance => Dark
```

```
Bundle.main.url
Bundle.main.decode
```

```
TabView
NavigationView
ScrollView
List
Group
GroupBox
VideoPlayer
NavigationLink
AVKit
UIKit

.edgesIgnoringSafeArea(.all)

```


```
 TabView {
            ForEach(coverImages) { item in
                Image(item.name)
                    .resizable()
                    .scaledToFill()
            }
        }
        .tabViewStyle(PageTabViewStyle())
```

```
import Foundation

extension Bundle {
    func decode<T: Codable>(_ file: String) -> T {
        guard let url = self.url(forResource: file, withExtension: nil) else {
            fatalError("Failed to locate \(file) in bundle")
        }
        
        guard let data = try? Data(contentsOf: url) else {
            fatalError("Failed to load \(file) from bundle")
        }
        
        let decoder = JSONDecoder()        
        guard let loaded = try? decoder.decode(T.self, from: data) else {
            fatalError("Failed to decode \(file) from bundle")
        }
        
        return loaded
    }
}

```
