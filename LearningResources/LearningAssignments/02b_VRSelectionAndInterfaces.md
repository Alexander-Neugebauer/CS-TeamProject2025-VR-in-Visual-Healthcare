# Learning Assignment 2b - VR Selection and Interfaces

In this assignment, we expand our previous scene to include a 'Ball Spawner' that allows us to get the ball back.

## 1. Create the Ball Spawner
- Create a new 3D Cylinder object, name it **BallSpawner** and place it in the scene near the XR Origin.
- Scale the BallSpawner to about `(0.5, 0.15, 0.5)` and make sure the bottom side aligns with the ground level (the flat sides of the cylinder should face up and down).
- Create an empty GameObject, name it **Socket** and assign it as a child object to the BallSpawner.
- Position the Socket ~0.3 units above the top surface of the cylinder.

## 2. Create a text interface
- Go to Window -> Import TMP Essential Resources.
- Right-click on the BallSpawner in the Hierarchy, then select UI -> 'Text - TextMeshPro'.
  > Note: Creating any UI object will automatically create a Canvas as parent object. A Canvas can hold multiple UI elements and manages how they are drawn to the screen.
- Click on the Canvas, go to the Inspector Window and under Canvas -> Render Mode, select 'World Space'. This will allow you to place the Canvas somewhere in 3D space instead of always projecting the UI to the camera screen, which does not work well in VR.
- Scale the Canvas to a reasonable size - for PosX and PosY, you can set it to 0 for now, for Width and Height, set it to 1.
- Next, click on the **Text (TMP)** object in the Hierarchy.
- Set its Width and Height to 300 and 40, respectively, and set the Scale to 0.001 in all dimensions.
  > Note: Canvas and UI objects are usually measured in Pixel Space. By setting the Canvas to World Space it converts pixels to units, which leads to these strange proportions.
- Change the text in the textbox (found in the Inspector) to "Balls spawned: 0".
- Select the Canvas object again and position it in the scene to be either above or in front of the BallSpawner.

## 3. Set up XR interactions
- Make sure you followed all the steps to install the XR plugin and other packages, as descibed in `03_UnityVRSceneSetup`.
- Add an **XR Simple Interactable** component to the BallSpawner.
- In the Hierarchy, navigate to XR Origin --> Camera Offset --> Left Controller --> Near-Far Interactor (the child object of Left Controller), and in the Near-Far Interactor component of the child object, check 'Allow Hovered Activate'. *Attention: The Left Controller GameObject also has a Near-Far Interactor component, however, checking the 'Allow Hovered Activate' option here will not work, you have to check the option in the child object's component.*
  > Note: This will allow you to use the 'Activated' and 'Deactivated' events in the XR Interactable components without having to grab the object first.

## 4. Create the BallSpawner logic
- Create a new `BallSpawnerBehavior.cs` script and assign it to the BallSpawner object.
- Make sure you include the TMPro library in the header of your script (`using TMPro;`).
- The script should have the following functionality:
  - A public method `ShowTextInterface` that sets the Canvas GameObject active, and another method `HideTextInterface` to disable it.
  - A public method `SpawnBall` that sets the position of the Ball to the position of the Socket and sets the Rigidbody velocity and angular velocity to 0.
    > Note: If the Rigidbody velocity and angular velocity are not reset, the ball would keep any momentum it has at the time of being "teleported" to the BallSpawner, potentially flying away instantly.
  - The `SpawnBall` method should also change the text of the TextMesh to say "Balls spawned: [n]", where n is an integer that counts up everytime the `SpawnBall` method is called.

## 5. Assign the methods
- Select the BallSpawner, and in the XR Simple Interactable component, go to 'Interactable Events'.
- Add an Event to 'First Hover Entered', drag and drop the BallSpawner in the Field and select the `BallSpawnerBehavior` script and the `ShowTextInterface` method.
- Do the same for 'Last Hover Existed' and the `HideTextInterface` Event.
- Next, add an Event to 'Activated' and assign the `SpawnBall` method.

## 6. Test your scene
- You should now be able to:
  - Hover over the BallSpawner with the controllers to show the "Balls spawned" text, which disappears if you stop hovering.
  - Use the trigger button (left-click in the Device Simulator) to click on the BallSpawner and place the ball on top of it.
- The BallSpawner should keep count how often it was used.
