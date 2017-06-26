# Lesson Day 2

Today will be setting up the unity environment for VR, explore VR simulator, and start building the game.

### Setting up our environment
- Create a new unity game ensuring 3D is selected.
- Navigate to **File => Build Settings**. From here click on either IOS or Android depending on personal device and click **Switch Platform**.
- Click on **Player Settings**. Click **Other Settings** and enable **Virtual Reality Supported**. Add **Cardboard** as device. 

##### Installing assets
 - Navigate to **Assets => import package => custom package** select the **starter package**. It can be downloaded from this repo if don't have it. This will import all the assets needed to start building the game.
 
### Testing VR simulator
 - Add a 3D object **cube** to your game. Position your cube so that has distance from main camera.
 - In **project** window, select **Google VR** folder and open up **Prefabs** folder. Click and drag **GvrEditorEmulator** to the Hierarchy window. This will allow us to simulate what the game will look/behave in VR without having to build it each time.
 - In **Prefabs** still, open up **UI** folder and click and drag **GvrRectilePointer** into the Hierarchy window as a child of **Main Camera**. In **Inspector** window give the pointer the **Position** of **X = 0, Y = -1, z = 6**, and **Scale** of **x = 1, y = 1, z =17**. This will act as our pointer in the game.
 - Save the game and click **Play**. You should now see the pointer and the cube. To move up/down/left/right hold **option/alt** key and move mouse. 
 
### Building the game

  #### Steps
  1. 
 


