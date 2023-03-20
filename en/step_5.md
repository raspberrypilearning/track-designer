##  Ramp and goal effects

In this step, you will ... 

![Output of step 5.](images/output5.png)


--- collapse ---
---
title: Change goal material when ball reaches it
---

This script changes the material of all the parts of the goal when the ball collides with any one of them. It also changes the material of individual ramps as the ball rolls over them. 

You need to create a `Goal` tag and add it to all of the GameObjects than make up the goal.

The script should be added to all the GameObjects in the goal and to the ramps that you want to change colour. 

--- code ---
---
language: cs
filename: RampController.cs
line_numbers: true
line_number_start: 1
line_highlights:
---

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class RampController : MonoBehaviour
{
  Material start;
  Renderer rend;

  // Start is called before the first frame update
  void Start()
  {
      rend = GetComponent<Renderer>();
      start = rend.sharedMaterial;
  }

  void OnCollisionEnter(Collision collision)
  {
      if (collision.gameObject.tag == "Player"){

          if (gameObject.tag == "Goal") // Change all goal parts
          {
            var objects = GameObject.FindGameObjectsWithTag("Goal");
        
            foreach (var obj in objects) {
                obj.GetComponent<Renderer>().sharedMaterial = collision.gameObject.GetComponent<Renderer>().sharedMaterial;
            }

          }
          else // Just change this part
          {
                rend.sharedMaterial = collision.gameObject.GetComponent<Renderer>().sharedMaterial;
          }
          
      }
  }

  void OnCollisionExit(Collision collision)
  {
      if (collision.gameObject.tag == "Player" && gameObject.tag != "Goal"){
          rend.sharedMaterial = start;
      }
  }

}

--- /code ---

--- /collapse ---