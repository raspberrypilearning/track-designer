## Roll a ball

In this step you will add a ball and place it at the top of your track. You will also make the world tilt so you can roll the ball down the track. 

![A strip of three examples showing the output of this step.](images/step3-output.png)

### Add a sphere

--- task ---

Add a Sphere GameObject and rename it to `Ball`. 

Scale the ball to fit your project (we used  X=`0.25`, Y=`0.25`, Z=`0.25`).

Add a material for your ball.

[[[unity-transform-tools]]]
[[[unity-existing-material]]]
[[[unity-material-with-texture]]]
[[[unity-glass-material]]]

![A small ball with the purple marble effect material added to it.](images/bouncy-ball.png)

--- /task ---

--- task ---

Position the ball at the top of your track slightly higher than the track surface.

[[[unity-scene-navigation]]]
[[[unity-scene-top-down]]]
[[[unity-3D-coordinates]]]

**Tip**: The 'Top' view is a good view for making sure that your ball is in the right place.

![Ball with colourful pattern positioned at the top of a ramp.](images/ball-start.png)

--- /task ---

### React to gravity

--- task ---

Add a Rigidbody to your ball. 

[[[unity-rigidbody]]]

--- /task ---

### Set up the camera

--- task ---

You will be tilting the track to roll the ball so a view point from the top is best. 

**Choose:** 
If you want the camera to follow the Ball your view should be zoomed in with the Ball in the center of the screen. On the other hand, if the camera is staying in one place you should make sure the whole track is visible and in the center of the screen. 

In our example the camera will follow the Ball and this is the view we will be using:

![A screenshot of the Scene view of the example game, the camera is close to the ball and only part of the track is visible.](images/camera-view.png)

Click on the **View tool** in the Scene view (the hand icon) and drag the view until you are happy with it. 

Align the camera to the Scene view.

[[[unity-align-with-view]]]

--- /task ---

### Apply physics material

--- task ---

Add a physics material to the ball.

[[[bouncy-material]]]

--- /task ---

--- task ---

Click **Play** and watch your ball bounce as it lands on the ramp.

![Animation showing ball dropping and bouncing on the ramp before rolling downwards.](images/ball-bounce.gif)

**Debug:** If your ball bounces too high and keeps bouncing off the track or if your ball moves too slowly you may need to adjust the values in your Physic Materials.

--- /task ---

### Camera Follow

--- task ---

If you want your camera to follow the Ball, select the 'Main Camera' GameObject in the Hierarchy window and add the `CameraFollow` script component.

--- collapse ---

---
title: I don't have a CameraFollow script
---

With the Ball selected, add a new script component called `CameraFollow`. 

Drag the new script file from your Assets into the 'Scripts' folder to organise your files. 

Open the new script in your code editor. Type out or copy and paste the following code: 

--- code ---
---
language: cs
filename: CameraFollow.cs
line_numbers: true
line_number_start: 
line_highlights: 
---

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CameraFollow : MonoBehaviour
{
    public GameObject ball;
    private Vector3 prevBallPos;
    
    void Start()
    {
        prevBallPos = ball.transform.position;
    }

    void LateUpdate()
    {
        transform.Translate(ball.transform.position - prevBallPos, Space.World);
        prevBallPos = ball.transform.position;
    }
}

--- /code ---

Save your script and head back to the Unity editor.

--- /collapse ---

Use the **Inspector** to set the 'Ball' attribute of the `CameraFollow` script.

![The CameraFollow script with the 'Ball' GameObject set in the Inspector.](images/camera-follow-component.png)

--- /task ---

### Tilt the track 

--- task ---

Select **all** the parts of your track and the **Plane** using <kbd>Shift</kbd>. 

Right click and select **Create Empty Parent** - rename the new parent object "Level".

--- /task ---

--- task ---

With the 'Level' GameObject selected add the `TiltFloor` script component. 

--- collapse ---

---
title: I dont have a TiltWorld script.
---

With 'Level' selected, add a new script component called `TiltFloor`. 

Drag the new script file from your Assets into the 'Scripts' folder to organise your files. 

Open the new script in your code editor. Type out or copy and paste the following code: 

--- code ---
---
language: cs
filename: TiltFloor.cs
line_numbers: true
line_number_start: 
line_highlights: 
---

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class TitltingFloorLerp : MonoBehaviour
{
    public float maxTilt;
    public float turnSpeed;

    public string forwardKey;
    public string leftKey;
    public string backwardKey;
    public string rightKey;

    // Update is called once per frame
    void Update()
    {
        float targetXRotation = 0;
        float targetZRotation = 0;

        if (Input.GetKey(forwardKey)){
            targetXRotation += maxTilt;
        }

        if (Input.GetKey(backwardKey)){
            targetXRotation += 360 - maxTilt;
        }

        if (Input.GetKey(rightKey)){
            targetZRotation += 360 - maxTilt;
        }

        if (Input.GetKey(leftKey)){
            targetZRotation += maxTilt;
        }

        transform.rotation = Quaternion.Lerp(transform.rotation, Quaternion.Euler(targetXRotation, 0, targetZRotation), turnSpeed * Time.deltaTime);
    }
}

--- /code ---

Save your script and head back to the Unity editor.

--- /collapse ---

--- /task ---

--- task ---

In the Inspector set the 'Max Tilt' variable to `15` and the 'Turn Speed' to `0.5`. 

**Choose** The keys you want to use for the tilting the track. In our example we are using the <kbd>WASD</kbd> layout.

[[[unity-keyboard-conventions]]]

![The TiltFloor component in the Inspector with all the variables set.](images/tilt-floor-component.png)

--- /task ---

--- task ---

**Test** your world tilt and camera behaviours. 

**Debug:** If your camera is too close or far away you can use 'Align view to selected' then move the Scene view until you are happy - you can then 'Align to View' to change the camera position. 

**Debug:** If you find your ball is bouncing when you tilt the world, try reducing the 'Max Tilt' and 'Turn Speed' values. 

Make sure you can complete your level with no problems, but don't make it too easy for your players.

![GIF showing the ball rolling into the 'Goal' object at the end of the track](images/finishing-level.gif)

--- /task ---

### Reset script

There is a chance your player will end up falling off the track, so you should add something to reset when this happens

--- task ---

Select the 'Plane' object in the Hierarchy window.

Add a Box Collider component and check 'Is Trigger'.

--- /task ---

--- task ---

In the Inspector add a new script to the 'Plane' called 'ResetTrack'.

Move the script into your Scripts folder.

--- /task ---

--- task ---

Open the 'ResetTrack' script in your code editor. 

Type out or copy and paste the following code:

--- code ---
---
language: cs
filename: ResetTrack.cs
line_numbers: true
line_number_start: 
line_highlights: 
---

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class ResetTrack : MonoBehaviour
{
    public GameObject ball;
    public GameObject level;
    private Vector3 startPosition;
    private Quaternion levelStartRotation;
    
    // Start is called before the first frame update
    void Start()
    {
        startPosition = ball.transform.position;
        levelStartRotation = level.transform.rotation;
    }

    void OnTriggerEnter(Collider other) {
        if (other.tag == "Player"){
            level.transform.rotation = levelStartRotation;
            ball.GetComponent<Rigidbody>().velocity = Vector3.zero;
            ball.transform.position = startPosition;
        }    
    }
}

--- /code ---

This script sends the 'Ball' back to it's start position and resets the Tilt of the 'Level' object.

Save your script and switch back to the Unity editor.

--- /task ---

--- task ---

Set the 'Ball' and 'Level' variables in the Inspector to the appropriate objects. 

![The Inspector window showing the 'ResetTrack' script with the variables filled in.](images/reset-track.png)

--- /task ---

--- task ---

Select the 'Ball' GameObject and add the 'Player' tag.

--- /task ---

--- task ---

**Test:** Your reset script to make sure it resets the player. 

![GIF showing the Ball falling off the track and then being reset to the top again](images/reset-demo.gif)

--- /task ---