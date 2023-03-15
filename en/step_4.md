## Interactive objects

In this step, you will add fixed and spinning obstacles for the ball to bounce off.

![Output of step 4.](images/output4.png)

### Add obstacles

--- task ---

**Add** obstacles to your track.

[[[unity-3D-coordinates]]]
[[[unity-transform-tools]]]
[[[unity-model-gameobject]]]
[[[unity-3d-objects]]]
[[[unity-scene-navigation]]]
[[[unity-scene-top-down]]]

--- /task ---

### Spin your obstacles

--- task ---

**Choose** which obstacles you would like to spin.

--- collapse ---
---
title: Make a GameObject spin
---

In the 'Project' window navigate to the 'Scripts' folder. 

Create a new Script called `Spin`.

Open the new Script and enter the following code:

--- code ---
---
language: cs
filename: Sin.cs
line_numbers: true
line_number_start: 1
line_highlights:
---

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Spin : MonoBehaviour
{
    public Vector3 rotation;

    // Start is called before the first frame update
    void Start()
    {
       
    }

    // Update is called once per frame
    void Update()
    {
        transform.Rotate(rotation * Time.deltaTime); 
    }
}

--- /code ---

**Save** the script and return to Unity. 

**Add** the `Spin` script to any GameObject that you would like to spin. 

**Choose** the direction the spin.

+ Change the `X`, `Y` and `Z` values in `Spin` script variables in the Inspector window to make your GameObject spin in the direction that you have chosen. 

--- /collapse ---

--- /task ---

### Add materials

--- task ---

**Choose** materials for your obstacles.

[[[unity-existing-material]]]
[[[unity-material-with-texture]]]
[[[unity-glass-material]]]

--- /task ---

--- task ---

**Choose** physics materials for your obstacles.

[pick one]
[make one]

--- /task ---

