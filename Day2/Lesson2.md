# Lesson Day 2

Today will be setting up the unity environment for VR, explore VR simulator, and start building some objects needed for the game.

### Setting up our environment

- Create a new unity game ensuring 3D is selected.

- Navigate to **File => Build Settings**. From here click on either IOS or Android depending on personal device and click **Switch Platform**.

- Click on **Player Settings**. Click **Other Settings** and enable **Virtual Reality Supported**. Add **Cardboard** as device. 

##### Installing assets

 - Navigate to **Assets => import package => custom package** select the **starter package**. It can be downloaded from this repo if don't have it. This will import all the assets needed to start building the game.
 
### Testing VR simulator

 - Add a 3D object **cube** to your game. Position your cube so that has distance from main camera.
 
 - In **project** window, select **Google VR** folder and open up **Prefabs** folder. Click and drag **GvrEditorEmulator** to the Hierarchy window. This will allow us to simulate what the game will look/behave in VR without having to build it each time.
 
 - In **Prefabs** still, open up **UI** folder and click and drag **GvrRectilePointer** into the Hierarchy window as a child of **Main Camera**. In **Inspector** window give the pointer the **Position** of **X = 0, Y = -1, z = 6**, and **Scale** of **x = 1, y = 1, z =25**. This will act as our pointer in the game.
 
 - Save the game and click **Play**. You should now see the pointer and the cube. To move up/down/left/right hold **option/alt** key and move mouse. 
 
### Building the game

- All scripts can be found in Wiki page.

  #### Steps
  **1. Building the target**
  
   - Rename your cube to **Asteroid** in the Inspector window. Create a new **Tag** name called **Target** and assign to the asteroid.
   
  **2. Setting up our Ship**
  
  - Change the name of the camera to **SpaceShip** in the Inspector window.
  
  - In the **project** window, select **Assets** and click **Create** and make a new folder called **Scripts**. This will be the folder that all of the scripts for our game will be stored. 
  
  - With **Scripts** folder selected, click **Create** and create new C# script. Name this script **SpaceShip** and hit enter. Click and drag this script onto the **SpaceShip** object in the Hierarchy window. Double click the script to open it.
  
  **3. Aiming Logic** 
  
  - **STOP HERE - Live Code Ship**. Script in Wiki page. This will let us know that we are actually targeting our asteroid.
  ```
  void Update () {
   RaycastHit hit;
   
    if (Physics.Raycast(transform.position, transform.forward, out hit)) {
     if (hit.transform.tag == "Target") {
       Debug.Log("HIT Asteroid");
     }
    }  
  }
  ```
  - Click Play and aim your pointer at the cube. Click on the **Console** window and should see the message **Hit Asteroid** displayed.

  **4. Building the bullet**
  
   - Create a new 3D object **Sphere**. Change name to **Bullet** in the Inspector window. This will act as our bullet that the ship will shoot at the asteroids.
   
   - In **Project** window, create a new folder called **Materials**. This will store all colors that will be used for our game objects.
   
   - With **Material** folded selected, Create a new Material called **Bullet Color** and pick a color the bullet in the Inspector window.
   Click and drag the Material onto the Bullet object in the Hierarchy window.
   
   - Create a new script named **Bullet** and attach to the Bullet object.
   
   - **Live-Code Bullet Script**
   
   - Create a new folder named **Game Prefabs** in your Project window. Select the new folder and click and drag the Asteroid object into the Game Prefabs folder. Delete Asteroid object from Hierarchy window. This makes the Bullet a **Prefab** so that may use it as many times as needed and only have to declare it once.
   
   **5. Spawn Bullets**
   
    - **Live-Code Ship** 
    
    - Delare new variables ```public GameObject bulletPrefab;``` ```public float shootingCoolDown;``` ```private float shootingTimer;```. Drag Bullet Prefab as new Component to the ship.
    
    ![](http://i.imgur.com/lukK97V.png)
    
    - Add to Update method. This will allow ship to spawn bullets.
    ```
  void Update () {

      // Decrease shooting timer
      shootingTimer -= Time.deltaTime;

      // Aiming logic
      RaycastHit hit;

      if (Physics.Raycast(transform.position, transform.forward, out hit)) {
        if (hit.transform.tag == "Target" && shootingTimer <= 0f) {
          shootingTimer = shootingCoolDown;

          GameObject bulletObject = Instantiate (bulletPrefab);
          bulletObject.transform.position = transform.position;

          Bullet bullet = bulletObject.GetComponent<Bullet> ();
          bullet.direction = (hit.transform.position - bulletObject.transform.position).normalized;
        }
      }
   }
   ```
   - Save game and click Play. Ship should now spawn bullets when aimed at Asteroid.
   
   - **END LIVE CODE**
   
   **6. Add lifespan to Bullet component**
   
   
    - **STOP HERE - Live code DestroyBullet script** - refer to wiki for script
    
    - Add script to Bullet Prefab. This will make the bullet destroy itself after certain amount of time. 
   
  **7. Building the Asteroid**
  
    - Delete cube from Hierarchy. Create an empty object and name it **Asteroid** and give it a Tag of **Target**.
    
    - Right click on empty object and create new 3D cube. Change scale values to 3, 3, 3 respectively.
    
    - Create a new Material called **Asteroid Color** and apply it to the cube.
    
    - Right click the cube and select **Duplicate**. Rotate new cube by 45, 45, 45 respectively.
    
    - Create new script named **Asteroid** and attach to Asteroid object.
    
    - **Live-Code Asteroid Script**
    
    - With Asteroid selected, click **Add Component** and search for **BoxCollider**, click to add to Asteroid. Under **BoxCollider** component, select **isTrigger** and give size of 4, 4, 4 respectivly. This will allow the Bullets to interact with the Asteroid.
    
    - With Asteroid selected, search for **RigidBody** and add to Asteroid. Deselect **use gravity**. This will allow the Asteroid to rotate with physics and float in the game world.
    
    - Save and run the game. Asteroid should now rotate and destroyed after being hit 3 times by Bullet.
    
    - Click and drag Asteroid object into **Game Prefab** folder. Delete Asteroid object from Hierarchy window. Now the Asteroid is a prefab.
   


