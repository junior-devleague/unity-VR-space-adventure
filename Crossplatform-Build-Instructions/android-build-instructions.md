# Android Build Instructions

## Requirements
- Make sure device is running minimum SDK version of **4.4 KitKat**.

#### Device Steps

1. In device navigate to **Settings => About** and tap **Build #** 7 times until notified that developer mode has been turned on.

2. In device navigate to **Settings => Developer Options** and turn **Developer Options** on. Scroll down to **Debugging** and turn on **USB Debugging**. Click **Ok** when prompted on screen.

3. Plug phone in and follow steps below for Unity.

#### Steps Unity

1. Make sure you have no errors present in your Unity project.

2. Navigate to **File => Build Settings** and select **Android** as the platform. Click **Switch Platform** and wait for Unity to re-compile the files.

3. At the top of the **Build Settings** window, click **Add Open Scenes**. This will add all scenes from your game. Double check to that all scenes were added as fail safe.

4. Click on **Player Settings** in Build Settings window. This will open up preferences in the Inspector window.
- At top of window, add a **Company Name** and **Product Name** of your choosing. You also have the option to select a **Default Icon** which will serve as app icon on your device.

![](http://i.imgur.com/6bVAMsT.png)

5. Open up **Other Settings** tab.
- Under **Rendering** Select **Virtual Reality Supported**. This will allow you to add a VR device. Click + and select **Cardboard**.
- Scroll down to **Identification** and add a **Bundle Identifier**. This follows the structure of **com.CompanyName.ProductName**. 
- Also select **4.4 KitKat** as **Minimal API Level**

![](http://i.imgur.com/GFhuYRX.png)

7. Make sure device is plugged into computer and click **Build And Run**. Unity will test/package all your files and publish the Application on the device. Once complete, Unity will launch the Application. 



#### Known Errors 
- **Win32 Exception Error** can be resolved by ensuring that Unity has the correct path to your Java JDK. If this path is incorrect, will fail to build application. Remeber, on OSX this file will be found at **Root/Library/Java/JavaVirtualMachines/jdk1.8.0_133/Contents/Home**.
