## Design the track

In this step, you will design your track using the parts available in the parts folder.  

![Output of step 2.](images/output2.png)

### Create a project with the starter package

--- task ---

Launch the Unity Hub and click **Projects** then select **New project**:

![A screenshot of the black bar at the top of the Unity Hub with the 'New Project' button highlighted in red.](images/new-project.png)

From the list choose **All templates** then select **3D Core**:

![A screenshot of the left pane in the Unity Hub. The 3D core option is highlighted in red.](images/3D-core.png)

Edit the project settings to give your project a name such as 'Pixel art reveal' and save it to a sensible location. Then click **Create project**.

Your new project will open in the Unity Editor. It may take some time to load.

--- /task ---

--- task ---

The Unity starter package you downloaded for this More Unity path contains a number of **Assets** for you to use in your project.

To import them into your new project, click on the **Assets menu** and select **Import package > Custom Package…** then navigate to the downloaded Unity starter package.

--- collapse ---
---
title: I haven't downloaded a Unity starter package
---

Download and unzip the [More Unity starter package](https://rpf.io/p/en/rainbow-run-go){:target="_blank"} to your computer. 

**Tip:** Choose a sensible location such as your Documents folder. 

--- /collapse ---

[[[unity-importing-a-package]]]

--- /task ---

--- task ---

Right-click on **SampleScene** in the Hierarchy and choose **Save Scene As**: 

![The scene icon in the Hierarchy window with the right-click menu expanded.](images/right-click-scene.png)

In the pop-up window, name your Scene `Track-Designer` or choose your own name:

A new file will appear in the Assets folder in the Project window.

--- /task ---

### Add a floor

--- task ---

Right-click on your scene in the Hierarchy window and choose **GameObject > 3D Object > Plane**.

This will create a ground for your track to sit on.

--- /task ---

--- task ---

**Reset** the 'Transform' properties to make sure that the plane is in the centre of your 3D world.

--- /task ---

--- task ---

**Choose** a size for your plane by changing the 'X' and 'Z' scale values.

Our example changes the 'Z' value to `2`:

![The Transform pane in the Inspector window with Scale properties X=1, Y=1, and Z=2.](images/plane-transform.png)

--- /task ---

--- task ---

In the Project window, click on **Materials > Obstacle Materials**.

**Choose** a material for your plane and drag it onto the 'Scene' view. 

Our example uses the 'Concrete' material:

![The Scene View with a rectangle plane covered in a grey textured material.](images/concrete-plane.png)

--- /task ---

### Design your track structure

--- task ---

Add in the parts.

Ingredients for moving around etc...

[[[unity-scene-navigation]]]

[[[unity-vertex-snapping]]]

--- /task ----

### Add materials to your track

--- task ---

Add materials & physics materials.

--- /task ----



