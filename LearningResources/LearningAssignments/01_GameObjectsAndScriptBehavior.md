
# Learning Assignment 1 - GameObjects and Script Behavior

> ## Recommended Reads
> - Unity Basics
>   - **01_UnityInstallationAndProjectSetup**
>   - **02_UnityIntroductionAndTutorials**

Apply the learned concepts about **GameObjects**, **MonoBehaviour scripts**, **Prefabs**, and the **Unity Input System** to create a small interactive scene.

## 1. Scene Setup
- Create a **new scene** in the project window.
- Add a **Ground Plane**.
- Add a **Pet Cube** (3D Cube) to represent your pet.
  - Optionally add other shapes to customize your pet.
- Add an **empty GameObject** and name it `GameManager`.

## 2. Create a Food Prefab
- Add a **Sphere** to the scene to represent food.
- Drag the Sphere from the **Hierarchy** to a **folder in the Project window** to create a prefab.
- Remove the Sphere from the scene.

## 3. Create MonoBehaviour Scripts
- Create two C# scripts:
  - `GameManager.cs` → Attach to the `GameManager` object.
  - `Pet.cs` → Attach to the `Pet Cube`.

## 4. Install the Input System Package
- Follow the [Unity documentation](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.14/manual/Installation.html) to install the package.

## 5. Food Spawning Logic (`GameManager.cs`)
- Use the Unity Input System to detect a key press (e.g., **F key**).
  > **Note**: For this assignment, using the simple method for getting input from a keyboard (`Keyboard.current[Key.F].wasPressedThisFrame`) is acceptable.
  > In your course project and in any larger Unity project, it is highly recommended to use [Input Action References](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.14/manual/Actions.html) instead.
- When the key is pressed: Instantiate a **Food Sphere** (using the previously created prefab) at a random position on the ground plane.

## 6. Pet Behavior (`Pet.cs`)
- If at least one **Food Sphere** exists in the scene:
  - Move the **Pet Cube** towards the closest Food Sphere at a defined speed.
  - When the pet reaches the food (via collision or distance threshold), destroy or deactivate the food object.

---

# Bonus Tasks

## 1. Implement Object Pooling
- Instead of destroying Food Spheres, use [object pooling](https://www.youtube.com/watch?v=lqiZxpTETl4) to reuse them.

## 2. Add a Reaction
- Implement a fun reaction for the pet whenever it is fed.
