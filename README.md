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
        .tabItem()
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

```
A guard statement is as simple as using an if..else statement and has its own benefits and uses. Swift guard is defined as a statement that is used to transfer program control out of a scope if one or more conditions aren’t met.
Guard works like a reverse if..else, so it works like guard based on [condition] if it’s true then move on and continue the loop, else do something to catch possible error.

//Using guard

for i in 1...20{
    guard i.isMultiple(of: 2) else {
       //don’t run anymore codes and  just continue to the next index
        continue
    }
    print(i)
}

 // BOTH codes will print even numbers (2,4,6,8,10,12,14,16,18,20)
 for i in 1...20{
    if(i.isMultiple(of: 2)){
        print(i)
    }
}

guard let name = passwordField.text where password.characters.count > 7 else {
    print("password must be at least 8 characters long")
    return
}

```
