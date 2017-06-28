# unity-space++

This is a comprehensive walk through tutorial to build a VR game in Unity and publish to IOS and Android devices. This project is intended for beginner/intermediate students that have not had any experience with Unity or C#. The goal of this game is to introduce students to the world of VR development through Unity. Through this tutorial, students will understand the total build cycle of a game, best coding practices, and cross platform builds for IOS and Android devices.

- **NOTE** all scripts can be found in Wiki.

### Requirements
 - Unity 5.6.2f1 https://unity3d.com/get-unity/download
 - Xcode Version 8.3.3 https://developer.apple.com/xcode/
 - Android Studio https://developer.android.com/studio/index.html
 - Java Jdk version 8U131 http://www.oracle.com/technetwork/java/javase/downloads/index.html
 - Google VR SDK for Unity version 1.60.0 https://developers.google.com/vr/unity/download
 
 ### Install Notes
 - **Note** file paths are based on OSX, windows users will need find equivalent paths.
  #### Unity 
   - Make sure to install IOS and Android platform.
  ##### Linking Android SDK & Java JDK with Unity
   - Navigate to unity **preferences => External tools => Android**. Click on browse to add file path to SDK & JDK. SDK will be located under User/library folder. If folder isn't visable, you need to right click in finder **show view options** and enable show library. JDK will be located in **Root/Library/Java/JavaVirtualMachines/**. By default Unity doesn't have root access so you will have to ensure the  path is correct.
 
 #### Xcode
  - Navigate to **preferences => accounts** click + by apple Id. Enter apple id and password. Xcode will automatically assign you a personal development team. You will use this team to sign your game before publishing to device.
  
#### Android Studio
 - You will need to walk through set up after downloading to install actual android SDK and associated tools.
        

### Crossplatform Build Notes
 - Ensure that you are running the latest version of IOS on your device.
 - Android device is at least running minimum of **4.4 kitkat**
