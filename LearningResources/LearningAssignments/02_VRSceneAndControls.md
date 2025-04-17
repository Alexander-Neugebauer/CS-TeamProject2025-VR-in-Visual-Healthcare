# Learning Assignment 2 - VR Scene and Controls

> ## Recommended Reads
> - Unity Basics
>   - **03_UnityVRSceneSetup**

In this assignment, we create a small interactive Game of "Fetch the Ball" using the Unity XR Interaction System.

## 1. Project Setup
- Create a new Unity project and set it up for VR use (follow provided guidelines).
- Create a new scene:
  - Remove the **Main Camera**.
  - Add an **XR Rig** and necessary scene objects, as stated in the guidelines.
- Create a ground plane and scale it up by ~10x.
- Create a new **Pet Cube** or copy the one from the previous assignment (remove `Pet.cs` if copied).
- Create an empty **GameObject** named **Snout**, make it a child of **Pet Cube** and position it outside of the cube in the **z-axis** direction *(which should be the facing direction of the Pet Cube while moving)*

## 2. Create an Interactable Object
- Add a **3D Sphere**, name it "Ball", and set its scale to **0.3** in all dimensions.
- Add a **Rigidbody** component to the **Ball**.
  > The Rigidbody component makes the object a physics based object that is affected by gravity and collisions.
- Add an **XR Grab Interactable** component.
- Create a script `BallState.cs` and attach it to the **Ball**.
- Open the BallState script in your IDE: 
  - Add a public bool variable called ´readyToFetch´.
  - Add two public functions (e.g. ´SetFetchTrue()´ and ´SetFetchFalse()´ to set the ´readyToFetch´ variable to either true or false.
- In **XR Grab Interactable > Interactable Events**:
  - Under **Last Select Exited**, add a new event.
  - Drag the **Ball** into the event field.
  - From the dropdown, select `BallState > SetFetchTrue`.
  > Note: The 'Last Select Exited' event is called when an object is released from being grabbed (i.e., thrown).

## 3. Implement Fetch Behavior

- Create a script `FetchBehavior.cs` and attach it to the **Pet Cube**.
- Open the script and implement the following functionality:
  - Get the `BallState` component of the **Ball** and check `readyToFetch`.
  - If `readyToFetch == true`:
    - Move toward the **Ball**.
    - When near the Ball:
      - Set the **Snout** as the Ball's parent object (use `Ball.transform.parent`).
      - Set the Ball’s position to the Snout’s position.
      - Get the Ball’s Rigidbody component an set `isKinematic = true`.
        > Note: This will prevent the Ball from falling to the ground while being ‘carried’ by the Pet Cube. 
      - Get the Ball's BallState compomentn and set `readyToFetch = false`.
    - Move toward the **Player XR Rig**.
    - When close to the player:
      - Set `Ball.transform.parent = null`.
      - Set the Rigidbody to `isKinematic = false`.

## 4. Test Your Game
- If everythig works as intended, you should now be able to use the **Grab button** of the controller (or the **G** key when using the XR Device Simulator) to grab and throw the Ball.
- The **Pet Cube** should:
  - Move to the Ball.
  - Pick it up.
  - Bring it back to you (the Player XR Rig).
- You can now repeat the process.
