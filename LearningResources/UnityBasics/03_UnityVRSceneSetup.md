# Unity Settings and Assets for VR/XR

In this chapter, you will learn how to set up a basic VR scene with an interactable object. The scene includes a VR emulator to test it on a PC.

## 1. Installing the Required Packages
- Go to **Window → Package Manager → Unity Registry**
- Search for and install the following packages:
  - **OpenXR Plugin** *(this also installs XR Core Utilities, XR Plugin Management, and XR Legacy Input Helpers as dependencies)*
  - **XR Interaction Toolkit** *(this also installs the Unity Input System, if not already installed)*
    - Go to **Samples** under this package and import:
      - **Starter Assets**
      - **XR Interaction Simulator**
      > Note: Make sure to use the **XR Interaction Simulator**, not the **XR Device Simulator**, which was used in previous projects but is now outdated.


## 2. Setup for Android-based VR Headsets (e.g., Meta Quest, Pico)

### Switching Build Platform
- Go to **File → Build Profiles**
- On the left, select **Android**, then click **Switch Platform**

### Enabling and Configuring OpenXR
- Go to **Edit → Project Settings → XR Plug-in Management**
- Under the **Android** tab, check **OpenXR**
- Go to the **OpenXR** settings (under XR Plug-in Management)
  - Under **Enabled Interaction Profiles**, enable:
    - **Khronos Simple Controller Profile**
    - **Meta Quest Touch Pro Controller Profile**
      > Note: If you plan on using Eye Tracking in your project, you should also enable **Eye Gaze Interaction Profile**.
  - Under **Feature Groups**, check **Meta Quest Support**. Also ensure that **Mock Runtime** is not checked.
    > Note: If you want to use Eye Tracking on the Meta Quest Pro, check **Foveated Rendering**. Otherwise, the Meta Quest Pro will not recognize the app to require Eye Tracking capabilities and will disable Eye Tracking functionality during use.
  - Under **Project Validation**, click **Fix All** *(It might take a few seconds for Unity to compile before the Issues disappear)* 
    > Note: The issue about Screen Ambient Occlusion will not be automatically fixed, but can be ignored.
  - Under **XR Interaction Toolkit**, check **Use XR Interaction Simulator in scenes** and **Instantiate in Editor Only**

### Configuring Player Settings
- In the **Project Settings**, go to **Player** and make sure that you are in the Android Settings tab
- Set the **Product Name** *(This is how your App will be named when installed on a VR device)*
- Under **Other Settings**:
  - Make sure that **Color Space** is set to **Linear**
  - In **Graphics API**, remove **OpenGLES3**
  - Ensure that **Allow HDR Display Output** is unchecked (otherwise, this could impact performance in VR)
  - Un-check **Override Default Package Name**, or manually adjust the name your application will be exported as
  - Set the minimum API Level to **Android 10.0 (API level 29)** or higher
  - In **Target Architecture**, only **ARM64** should be checked
  - Ensure that **Active Input Handling** is set to **Input System Package (New)**
  - Ensure that under **Scripting Define Symbols**, `USE_INPUT_SYSTEM_POSE_CONTROL` is listed (if not, add a new empty element and paste the name in)

## 3. Scene Setup

- Create a new scene or use the Default Scene
- If you use a new scene:
  - Go to **Build Profiles → Scene List**, click **Add Open Scenes**
  - Make sure your scene is listed at the top

### Scene Configuration
- Delete the **Main Camera**
- In the Project window, search for **XR Origin (XR Rig)** and drag it into the Scene Window or Hierarchy
- If no **EventSystem** exists, right-click in the **Hierarchy**, select **UI → Event System**
- Also add an **XR Interaction Manager** (Right-click → XR → Interaction Manager)


## 4. Create a Test Build

### Test on a PC with an Emulated VR Setup
- Add a Plane as a ground plane and place the **XR Origin** above it
- Add a 3D GameObject (e.g., Sphere or Cube) above the ground
  - Click on the GameObject and in the Inspector, add a **XR Grab Interactable** component to it *(this also adds a Rigidbody component to the object, which means that the object is treated as a physics-based object)
  > Note: See 'LearningAssignments/02b_VRSelectionAndInterfaces' in the Learning Resources for information on how to click on objects or interfaces without grabbing them

#### Controls in Editor
- When starting the scene, you should be able to turn the camera or controllers by holding the right mouse button, move using the **WASD** keys, press **Tab** to loop through headset and controllers, and press **G** to simulate the **Grab** button of the VR controllers
- Try grabbing and throwing the 3D GameObject

### Test on a stand-alone VR Headset

#### Setup
- Connect the VR headset to the PC via USB-C cable
- In the headset interface, navigate to **Updates** and confirm the USB connection
- In Unity:
  - Go to **Build Profiles → Android**
  - Click **Refresh** under **Run Device**
  - If the headset appears, you can proceed with the 'Build and Run' section
  - If not, try restarting the headset. After the restart, it should ask about permission to connect to the PC device

#### Build and Run
- Once the VR headset is properly connected, click **Build And Run**
- Save the build (e.g., in a new `Builds` folder inside your Unity project
- Upon completion of the first install (or when changing the name under which the App is installed), you will be asked to allow installing the app inside the VR headset
- The app should now load and you should be able to grab and throw around your created 3D object
