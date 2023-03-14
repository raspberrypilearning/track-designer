## Add a ball

In this step you will add a ball and place it at the top of your track so that it rolls down. 

![A strip of three examples showing the output of this step.](images/step-three-output.png)

### Add a sphere

--- task ---

Add a Sphere GameObject and rename it to `Ball`.

**Tip**: You may want to reset the 'Transform position' to place it in the centre of your scene.  

--- /task ---

--- task ---

**Choose** a scale for your ball. 

We used X=`0.25`, Y=`0.25`, Z=`0.25` in the Rainbow Run project which is a good size for the parts that you have. 

--- /task ---

--- task ---

**Choose** a material for your ball.

![A small ball with the purple marble effect material added to it.](images/purple-marble.png)

--- /task ---

--- task ---

Position the ball at the top of your track.

![Ball with colourful pattern positioned at the top of a ramp.](images/ball-start.png)

**Tip**: The 'Top' view is a good view for making sure that your ball is in the right place.

--- /task ---

### React to gravity

--- task ---

With the 'Ball' GameObject selected, choose 'Add Component' in the inspector window and enter the text 'RigidBody'. Select the 'RigidBody' component. This adds a gravity effect to your ball. 

![A screenshot showing the RigidBody component selected in the inspector window.](images/rigid-body.png)

--- /task ---

--- task ---

Right-click on the 'MainCamera' object in the 'Hierarchy'.

Choose 'Align with view'. This will match your Scene view and your Main Camera view. 

![A screenshot showing the 'Align with view' option highlighted in the GameObject menu.](images/align-with-view.png)

--- /task ---

--- task ---

**Test:** Play your scene and the ball should roll down your track. 

**Debug:** If your ball gets stuck then you may need to redesign your track.

--- /task ---

### Apply physics material

--- task ---

In the Project window select 'Materials' and then 'PhysicsMaterials'. Right-click in the window, click 'Create' and select **Physic Material**. 

![A screenshot showing menu with 'Create' and 'Physic Material' highlighted.](images/create-physic-material.png)

--- /task ---

--- task ---

Name the material 'Bounce'.

![A screenshot showing the newly created 'Bounce' physics material.](images/bounce-material.png)

--- /task ---

--- task ---

Change Bounciness to `1`.

![A screenshot showing the 'Bounciness' property set to '1'.](images/bounciness-one.png)

--- /task ---

--- task ---

Select the 'Ball' GameObject and go to the Inspector window.

Find the 'Sphere Collider' properties and click on the small circle in the 'Material' section. 

![A screenshot showing the small circle to the right of 'Material'.](images/add-physics-material.png)

Double-click on your new 'Bounce' physics material.

![A screenshot showing the the 'Bounce' physics material highlighted.](images/bounce.png)

--- /task ---

--- task ---

Click **Play** and watch your ball bounce as it lands on the ramp.

![Animation showing ball dropping and bouncing on the ramp before rolling downwards.](images/ball-bounce.gif)

--- /task ---
