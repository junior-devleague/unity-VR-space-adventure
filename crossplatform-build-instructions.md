# Crossplatform Build Instructions

### IOS

##### Requirements
- Make sure you are running the lastest version of IOS on your device for compatability reasons.
- IOS minimum device model of Iphone 5

#### Steps Unity

1. Make sure you have no errors present in your Unity project.

2. Navigate to **File => Build Settings** and select **IOS** as the platform. Click **Switch Platform** and wait for Unity to re-compile your files.

3. At the top of the **Build Settings** window, click **Add Open Scenes**. This will add all scenes from your game. Double check to that all scenes were added as fail safe.

4. Click on **Player Settings** in Build Settings window. This will open up preferences in the Inspector window.
- At top of window, add a **Company Name** and **Product Name** of your choosing. You also have to option to select a **Default Icon** which will serve as app icon on your device.
  ![](http://i.imgur.com/6bVAMsT.png)

5. Open up **Resolution and Presentation** tab.
- Under **Allowed Orientations for Auto Rotation** uncheck all boxes EXCEPT **Landscape Left**.
![](http://i.imgur.com/c19GFKD.png)

6. Open up **Other Settings** tab.
- Under **Rendering** Select **Virtual Reality Supported**. This will allow you to add a VR device. Click + and select **Cardboard**.
- Scroll down to **Identification** and add a **Bundle Identifier**. This follows the structure of **com.CompanyName.ProductName**. Leave all other fields as is.
![](http://i.imgur.com/v1hSu8g.png)

7. Plug your device into your computer and click **Build And Run**. Unity will test/package all your files and ship it off to Xcode. 

#### Steps Xcode

1. Make sure that you filled in your appleId and Password in **Preferences => Accounts**. You need this for signing your app certificate and generating your personal dev team.

2. Make sure that Xcode recognizes your device is plugged in. 

3. Xcode will initially fail the build because you need to select your dev team to sign the certificate. Select your **Team** from the drop down menu. Xcode will try to compile your app again.

![](http://i.imgur.com/nYbcarP.png)

4. Once you see the **Build Successful** notification, Unlock your iphone and navigate to **Settings => General => Profiles & Device Management**. Click on your **Developer App** Id and select **Trust**. This will allow your device to run apps by this developer.

5. Xcode will now launch your app on the phone. You can now unplug your device and test the app. You also can keep it plugged in to run live tests on the app.

#### Known Errors 
- **Match-O Linker Error** can be resolved by exporting your game in Unity, creating new project and import your game package. Follow the Unity steps again and Build and Run. This should push to Xcode and build successfully. Dont mind the yellow warnings, as this shouldn't result in an unsuccessful build.


