# Cloning a Github Repository

> Note: To use Github, you must have Git installed on your system. If you haven't, go to the [download page](https://git-scm.com/downloads) and follow the instructions.

> Note: You can use Git either via cmd line or you can use a graphical UI like [Github Desktop](https://desktop.github.com/download/).

- Create the folder where you want to store the Unity project, e.g.: `.../[User]/UnityProjects/[ProjectName]/`
- In your browser, navigate to the Github Repository you were invited to. Click the `<> Clone` button and copy the displayed URL to the clipboard.

## Cloning via cmd prompt
- Navigate to the created directory (`cd path/to/the/directory`)
- use `git clone https://github.com/...` (replace the URL with the copied URL)

## Cloning via Github Desktop
- Click **File → Clone repository → URL**
- Enter the copied URL and change the **Local path** to the previously created directory.
- Click **clone**.

## Adding the project to UnityHub
- Open UnityHub.
- Make sure that you have a Unity Version installed that matches the project of the Github Repository
  > Note: For this project, you need Unity LTS 6000.0.45f1. You can find previous Unity Versions in the [Unity Download Archive](https://unity.com/releases/editor/archive).
- Under **Projects**, select **Add → Add project from disk**
- Choose the directory where the repository was stored and click **open**
  > Note: You will get an error message when you only select the parent folder. You have to navigate within the folder.
