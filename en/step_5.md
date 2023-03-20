##  Track and goal effects

In this step, you will add effects to your track and your goal. 

![Output of step 5.](images/output5.png)

### Add effects to your track

--- task ---

**Choose** which effects you would like to add to your track. You could:
+ Make the track change colour as the ball rolls over it
+ Make an obstacle change colour when the ball touches it
+ Make a sound play when an obstacle is hit by the ball

[[[unity-play-sound-collision]]]
[[[unity-change-material-when-collided]]]

--- /task ---


### Add effects to your goal

--- task ---

**Choose** which effects you would like to add to your goal. 

You could:
+ Make the goal change colour when the ball rolls into it
+ Make the ball change colour when it reaches the goal
+ Make a sound play when an obstacle is hit by the ball
+ Trigger a particle effect when the ball reaches the goal. 

--- collapse ---
---
title: Change goal material when the ball reaches it
---

This script changes the material of all the parts of the goal when the ball collides with any one of them. It also changes the material of individual ramps as the ball rolls over them. 

You need to create a `Goal` tag and add it to all of the GameObjects than make up the goal.

Add the script to all the GameObjects in the goal. 

--- code ---
---
language: cs
filename: GoalController.cs
line_numbers: true
line_number_start: 1
line_highlights:
---

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class GoalController : MonoBehaviour
{

  void OnCollisionEnter(Collision collision)
  {
      if (collision.gameObject.tag == "Player" && gameObject.tag == "Goal"){
            
            var objects = GameObject.FindGameObjectsWithTag("Goal");
        
            foreach (var obj in objects) {
                obj.GetComponent<Renderer>().sharedMaterial = collision.gameObject.GetComponent<Renderer>().sharedMaterial;
            }         
      }
  }

}

--- /code ---

--- /collapse ---