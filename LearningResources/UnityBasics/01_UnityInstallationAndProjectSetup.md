# Unity Version Installation & New Project

## 1. Install Unity Hub
- Download from: [https://unity.com/download](https://unity.com/download)
- If you don't have one, create a Unity ID.
- Log in to Unity Hub using your Unity ID.
- In the profile menu (top left), go to **Manage Licenses → Licenses** and select the **Free Personal License** option.

## 2. Install a new Unity Editor Version
- In Unity Hub, navigate to **Installs → Install Editor**.
- Select the newest **LTS Version** or the **Supported Version**, based on which version was discussed previously (currently **Unity 6000.0.60f1 LTS** and **Unity 6000.2.6f2**).
- If you plan on targeting stand-alone VR/XR devices in this project (which we usually do), select during installation:
  - **Android Build Support**
    - **OpenJDK**
    - **Android SDK & NDK Tools**

## 3. Create a New Project
- Once installation is complete, create a new project using the installed version.
- Choose the **Universal 3D Core** preset.
- Select your **Unity Organization** (linked with your Unity ID).
- In the **Project Name** drop-down menu, select 'Create new local project' *(unless you plan on publicly releasing the project and want to have access to Unity Cloud features like Player Analytics, Adds, or Cloud Storage)*
> Note: In older versions of Unity Hub, instead of the step above, make sure the option **Use Unity Version Control** is deselected.
- Select a **Project Name** and **Location**.
- Do not select 'Use Unity Version Control'
- Wait until the project loads. You are now in the **Unity Editor** interface.

> **Note:** You’ll also need an IDE to edit scripts in Unity. The most commonly used IDE is **Visual Studio 2022**, but you can choose your preferred IDE.
