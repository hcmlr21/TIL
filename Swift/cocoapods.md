# cocoapods

0. Open terminal.
1. Install cocoapods
```
sudo gem install cocoapods
```
2. Go to Directory where you start cocoapods
3. Make Podfile
```
pod init
```
4. Open Podfile in your Directory
5. Add dependency in Podfile
```
EX)

# Uncomment the next line to define a global platform for your project
# platform :ios, '9.0'

target 'YOURPROJECT' do
  # Comment the next line if you don't want to use dynamic frameworks
  use_frameworks!
  
  pod 'Alamofire', '4.9.1' <<< ADD THIS LINE!

  # Pods for Wednesday

end
```
6. Install dependency
```
pod install
```
7. Import dependency in your Project
```
import Alamofire
```
8. Now you can use it
