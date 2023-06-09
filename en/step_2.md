## Design the track

In this step, you will design your track using the parts available in the Parts folder.  

![A strip of examples showing different options for how a track could be designed. The first is a track with spirals and curved ramps in pink and black. The second uses Cube GameObjects with a hidden rainbow path. The third uses several spirals on top of each other.](images/output2-strip.png)

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">
Some popular <span style="color: #0faeb0">**rolling ball games**</span> made with Unity include <span style="color: #0faeb0">**Super Monkey Ball Banana Mania**</span>, <span style="color: #0faeb0">**Katamari Damacy REROLL**</span>, <span style="color: #0faeb0">**Hop**</span> and <span style="color: #0faeb0">**Rush**</span>. In some rolling ball games and apps, you control the ball directly, and in others you tilt the floor to move the ball. Have you played any games with a rolling ball or marble?
</p>

### Open your project

--- task ---

Launch the Unity Hub and open the project you used for [Pixel art reveal](https://projects.raspberrypi.org/en/projects/pixel-art-reveal/0){:target='_blank'}.

--- collapse ---

---
title: I haven't got my Pixel art reveal project
---

If you are unable to open your project, launch the Unity Hub and click **Projects** then select **New project**:

![A screenshot of the black bar at the top of the Unity Hub with the 'New Project' button highlighted in red.](images/new-project.png)

From the list, choose **All templates** then select **3D Core**:

![A screenshot of the left-hand pane in the Unity Hub. The 3D core option is highlighted in red.](images/3D-core.png)

Edit the project settings to give your project a sensible name and save it to a sensible location. Then click **Create project**:

![A screenshot of the right-hand pane in the Unity Hub. The filename is highlighted in red.](images/create-project.png)

Your new project will open in the Unity Editor. It may take some time to load.

Download and unzip the [More Unity starter package](https://rpf.io/p/en/rainbow-run-go){:target="_blank"} to your computer. 

**Tip:** Choose a sensible location such as your Documents folder.

The Unity starter package you downloaded for this More Unity path contains a number of **Assets** for you to use in your project.

To import them into your new project, click on the **Assets menu** and select **Import package > Custom Package…** then navigate to the downloaded More Unity starter package.

--- /collapse ---

--- /task ---

--- task ---

In the **Project** panel, right-click and select **Create > Scene**.

![The right-click menu with Create and Scene highlighted](images/create-scene.png)

In the pop-up window, name your Scene `Track designer`:

A new file will appear in the Assets folder in the Project window.

Drag the new Scene into the Scenes folder to organise your files.

Open the new Scene, by double-clicking on it, to start making your track!

--- /task ---

### Add a floor

--- task ---

Right-click in the Hierarchy window and choose **GameObject > 3D Object > Plane**.

This will create a ground for your track to sit on.

[[[unity-plane]]]

Make sure the 'Plane' object is at position X=`0`, Y=`0`, Z=`0`.

--- /task ---

--- task ---

**Choose** a size for your plane by changing the 'X' and 'Z' scale values.

Our example changed the 'X' and 'Z' values to `3`:

![The Transform pane in the Inspector window with Scale properties X=3 and Z=3 highlighted.](images/plane-transform.png)

--- /task ---

### Design your track structure

Your track needs:
+ A start
+ Middle pieces
+ A goal 

It is practical to create your track from the **last** part (the goal) to the **first** part (the start). 

**Tip:** This project will be controlled by **tilting** the track to roll the ball, try to avoid too many twists and turns or it might be too difficult for your players. 

--- task ---

**Choose** your goal and drag the part into your scene. You could:
+ Use the existing 'goal' part from the **Assets > Parts** folder
+ Create your own goal from 3D objects

[[[unity-model-gameobject]]]
[[[unity-3d-objects]]]

--- /task ---

--- task ---

Set the transform position, rotation, and scale of your goal until you are satisfied with where it is positioned.  

**Tip:** The 'Transform Position' values X=`0`, Y=`0`, Z=`0` start your goal in the middle of your scene. 

![A goal is positioned in the Scene view.](images/goal-position.png)

[[[unity-scene-navigation]]]
[[[unity-scene-top-down]]]
[[[unity-3D-coordinates]]]
[[[unity-transform-tools]]]

--- /task ---

--- task ---

**Choose** your parts one at a time starting with the part that links to your goal. 

Each time, change the transform position, rotation, and scale if needed, and make sure the track position lines up with the previous part. 

![A final piece of track is positioned next to the goal.](images/first-part.png)

**Tip**: Look at your parts from lots of different angles to make sure that they are lined up correctly.

**Tip**: It is OK to change the position of previous parts as you design and build your track.

[[[unity-scene-navigation]]]
[[[unity-vertex-snapping]]]
[[[unity-scene-gizmo]]]

![All of the parts have now been added to the scene. There is a curved ramp that leads to two spirals and then another two curved ramps.](images/all-parts.png)

--- /task ---

--- task ---

Once you have finished adding your track pieces, add a 'start' piece. In our example we are using the 'Goal' piece. 

You can make your own out of GameObjects — the important thing is to add a back to stop the ball rolling off the track at the start of the game.

Name the GameObject `Start`, so you know it is different than the `Goal` at the end. 

![The Hierarchy window, showing a part named 'Start'](images/start-object.png)

**Tip:** Make sure the path for is smooth for a ball to roll from the start on to your track.

![The Start of the track, with a smooth path for a ball to roll over to begin the game.](images/start-path.png)

--- /task ---

### Add materials to your scene

--- task ---

**Choose** a material for each piece in your track. 

In the Project window, go to **Materials > ObstacleMaterials**. Drag a coloured material onto each piece in the Scene view.   

[[[unity-existing-material]]]
[[[unity-material-with-texture]]]
[[[unity-glass-material]]]

![The example track is now coloured in using purple and white, with a rainbow of colours on the floor to make a vibrant effect.](images/track-materials.png)

--- /task ---

--- task ---

Create a skybox for your scene.

[[[unity-skybox]]]

--- /task ---
