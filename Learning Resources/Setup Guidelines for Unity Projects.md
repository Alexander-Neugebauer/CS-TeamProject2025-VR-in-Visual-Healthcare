# Unity Version Installation & New Project

## 1. Install Unity Hub
- Download from: [https://unity.com/download](https://unity.com/download)
- If you don't have one, create a Unity ID.
- Log in to Unity Hub using your Unity ID.
- In the profile menu (top left), go to **Manage Licenses → Licenses** and select the **Free Personal License** option.

## 2. Install a new Unity Editor Version
- In Unity Hub, navigate to **Installs → Install Editor**.
- Select the **newest LTS Version** (currently **Unity 6000.0.45f1**).
- If you plan on targeting stand-alone VR/XR devices in this project (which we do), select during installation:
  - **Android Build Support**
    - **OpenJDK**
    - **Android SDK & NDK Tools**

## 3. Create a New Project
- Once installation is complete, create a new project using the installed version.
- Choose the **Universal 3D Core** preset.
- Select any **Project Name** and **Location**.
- Select your **Unity Organization** (linked with your Unity ID).
- **Do not** select:
  - **Connect to Unity Cloud**
  - **Use Unity Version Control**
- Wait until the project loads. You are now in the **Unity Editor** interface.

> **Note:** You’ll also need an IDE to edit scripts in Unity. The most commonly used IDE is **Visual Studio 2022**, but you can choose your preferred IDE.

---

# Unity Basics

## 1. Unity Editor

The Unity Editor interface contains the following elements:

- **Scene View** – Displays the current world scene; allows visual selection, movement, and transformation of GameObjects.
- **Hierarchy** – Lists all GameObjects in the current scene. Right-click here to create new scene objects.
- **Game View** – Shows how the scene appears during play mode.
- **Inspector** – Displays components (properties) of the selected GameObject or asset.
- **Project Window** – Contains all project assets (scripts, prefabs, textures, etc.), not limited to the current scene.
- **Console** – Displays log messages, warnings, and errors from scripts and the Unity engine.

## Tutorials and Resources

1.	**Youtube Tutorial** - Beginner friendly introduction to the Unity Editor Interface, GameObjects and Components: [Unity 6 Tutorial Part 1 - Learn The Basics](https://www.youtube.com/watch?v=HwI90YLqMaY&list=PLZ1b66Z1KFKhO7R6Q588cdWxdnVxpPmA8&index=2)
2.	**Tutorial Article** - Detailed introduction to creating scene objects and adding script behavior. Teaches many relevant aspects for Unity development: [Basics - Game Objects and Scripts](https://catlikecoding.com/unity/tutorials/basics/game-objects-and-scripts/)
3.	**Youtube Tutorial** - Covers different ways to reference other classes and GameObjects in a script: [How to get a variable from another script in Unity](https://www.youtube.com/watch?v=2pCkInvkwZ0)
4.	**Youtube Tutorial** - Covers the concept of prefabs, how to create them and how to instantiate scene objects from a prefab reference: [How to Make and Instantiate Prefabs](https://www.youtube.com/watch?v=IfcCXVXjLNM)
5.	**Unity Documentation** - Introduction to the Unity Input System: [Unity Input System - Installation and Quick Start Guide](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.0/manual/Installation.html) 
