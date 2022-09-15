---
layout: project
type: project
image: img/bwj/cleansweep.png
title: "Clean Sweep"
date: 2022
published: true
labels:
  - Unity
  - C#
  - Game Development
summary: "Clean Sweep is a game created by fellow collaborators and I for the Black and White Game Jam."
---

<div class="text-center p-4">
  <img width="200px" src="../img/micromouse/micromouse-robot.png" class="img-thumbnail" >
  <img width="200px" src="../img/micromouse/micromouse-robot-2.jpg" class="img-thumbnail" >
  <img width="200px" src="../img/micromouse/micromouse-circuit.png" class="img-thumbnail" >
</div>

Micromouse is an event where small robot “mice” solve a 16 x 16 maze.  Events are held worldwide.  The maze is made up of a 16 by 16 gird of cells, each 180 mm square with walls 50 mm high.  The mice are completely autonomous robots that must find their way from a predetermined starting position to the central area of the maze unaided.  The mouse will need to keep track of where it is, discover walls as it explores, map out the maze and detect when it has reached the center.  having reached the center, the mouse will typically perform additional searches of the maze until it has found the most optimal route from the start to the center.  Once the most optimal route has been determined, the mouse will run that route in the shortest possible time.

For this project, I was the lead programmer who was responsible for programming the various capabilities of the mouse.  I started by programming the basics, such as sensor polling and motor actuation using interrupts.  From there, I then programmed the basic PD controls for the motors of the mouse.  The PD control the drive so that the mouse would stay centered while traversing the maze and keep the mouse driving straight.  I also programmed basic algorithms used to solve the maze such as a right wall hugger and a left wall hugger algorithm.  From there I worked on a flood-fill algorithm to help the mouse track where it is in the maze, and to map the route it takes.  We finished with the fastest mouse who finished the maze within our college.

Here is some code that illustrates how we read values from the line sensors:

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.SceneManagement;


public class Player_Energy : MonoBehaviour
{

    [SerializeField] public float Decrease;
    [SerializeField] public float charge;
    // Start is called before the first frame update
    public float maxEnergy = 100;
    public float currentEnergy;
    public GameObject Roomba_Station;
    public Player_Movement Player;
    public Energy energyBar;
    public Vector2 MaxBounds;
    public Vector2 MinBounds;

    void Start()
    {
        currentEnergy = maxEnergy;
        energyBar.SetMaxEnergy(maxEnergy);
    }

    // Update is called once per frame
    void Update()
    {
        //Out of Energy Reset (technically tentative for change)
        if (currentEnergy <= 0)
        {
            // this.gameObject.SetActive(false);
            transform.position = Vector2.Lerp(transform.position, Roomba_Station.transform.position, Time.deltaTime * 100.0f);
            StartCoroutine(StopPlayer());
        }

        //Manual Energy Loss (for testing purposes)
        if (Input.GetKeyDown(KeyCode.Space))
        {
            //LoseEnergy(20);
        }

        //Energy Drain
        currentEnergy -= Time.deltaTime*Decrease;
        energyBar.SetEnergy(currentEnergy);


        //Recharge Station
        if(this.gameObject.transform.position.x <= MaxBounds.x &&
        this.gameObject.transform.position.x >= MinBounds.x &&
        this.gameObject.transform.position.y <= MaxBounds.y &&
        this.gameObject.transform.position.y >= MinBounds.y &&
        currentEnergy <= maxEnergy)
        {
            currentEnergy += Time.deltaTime*charge;
            energyBar.SetEnergy(currentEnergy);
        }
    }

    IEnumerator StopPlayer()
    {
        Player.enabled = false;
        yield return new WaitForSeconds(3.0f);
        Player.enabled = true;
    }
}
```

This game is publically available to play on itch.io: [Clean Sweep](https://snekuchan.itch.io/clean-sweep-a-game-about-life-but-its-only-the-mundane-chores-part).
