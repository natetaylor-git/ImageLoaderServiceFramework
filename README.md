# ImageLoaderServiceFramework

**ImageLoaderServiceFramework** is a simple framework that allows you to *download image* and *save it to cache*.

### Installing

First, you need to install [Carthage](https://github.com/Carthage/Carthage/blob/master/README.md) package manager if you haven't done this before.

After it was installed follow next steps:
1. Go to your project directory and create a `Cartfile` that lists the frameworks you’d like to use in your project:
```
$ touch Cartfile
```

2. Edit Cartfile by adding ImageLoaderServiceFramework dependency:
```
github "natetaylor-git/ImageLoaderServiceFramework" >= 1.0
```

3. Then, fetch and build all dependencies from Cartfile for iOS platform with following command: 
```
$ carthage update --platform iOS
```
When you run this, Carthage creates a couple of files and directories. Leave the directory `Carthage\Build\iOS` open.

4. Now go to your **Xcode project** and choose **<YourApp> target** in Project Navigator. Select **General** tab at the top, and scroll down to the **Linked Frameworks and Libraries** section at the bottom.
  
5. Drag **ImageLoaderService.framework** from `Carthage\Build\iOS` into the **Linked Frameworks and Libraries** section in Xcode.

6. Switch to **Build Phases** tab and add a **New Run Script Phase** by clicking the **+** in the top left of the editor. Under `Shell` statement add the following :
```
/usr/local/bin/carthage copy-frameworks
```

7. Also click **+** under `Input Files` and add:
```
$(SRCROOT)/Carthage/Build/iOS/ImageLoaderService.framework
```

Installation finished.

### How to use

In order to use **ImageLoaderService** simply add *import* statement to your code:
```
import ImageLoaderService
```

Now you are able to use all framework components.
