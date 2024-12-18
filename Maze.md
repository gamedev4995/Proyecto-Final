# Maze

To create the maze first we mapped out and generated a few iterations of different maze sizes to create a maze that wasn't too large and difficult or too easy. We generated a simple maze with the help of https://www.mazegenerator.net/ and looked for a good maze we could work with.

<img width="365" alt="Screenshot 2024-12-17 at 11 36 31 PM" src="https://github.com/user-attachments/assets/f466d454-80c4-4ef0-9296-d86e643e1a2b" />


> Chosen maze to design

_Important Note_: The development of the maze would have been more doable if you were to put the walls/floors/etc. into a prefab variant. I was a bit too deep into the project when I realized I never made it into a prefab variant. Even so, it was easy to go through all the objects since, later on, we will discuss on how we set up our traps.


### Outer Walls

We first started on our outer walls. For a symmetrical maze, we used the same amount of walls for each side of the maze. In our case there is 10 walls per side, except for the top and bottom that there will be 9 only. The one wall that is missing on the bottom/top side will act as our entrance/exit.

To save us time, we simply did the left side first and added it into an empty gameobject. For the other sides, we simply copy and pasted the game object and rotating it accordingly to the maze.


<img width="554" alt="Screenshot 2024-12-17 at 11 05 56 PM" src="https://github.com/user-attachments/assets/4fea7441-317b-4634-9c46-07359b749a76" />


### Floor 

We then tackled our floor, we used the same method of having a row of 10 floor objects first and then added them into an empty gameobject. For the rest of the maze we simply copy and pasted the gameobject until we fully covered every side.

<img width="510" alt="Screenshot 2024-12-17 at 11 26 23 PM" src="https://github.com/user-attachments/assets/347a7a17-f8f7-4590-8469-64d312411d4d" />


### Ceiling

The ceiling was simple enough. We copy and pasted the object to the floor that was fully finished and with the move tool, we used the y-coordinate to raise it upwards making sure it connects our walls.

<img width="527" alt="Screenshot 2024-12-18 at 12 07 57 AM" src="https://github.com/user-attachments/assets/cc50f964-9e77-4224-8c14-fad28f6ca504" />

_Note!_: For easier management throughout our project we disabled the ceiling for the rest of the making of the projects so its easier for us to loo into the maze.

### Inner Walls

The inner walls of our maze was the most tedious and time consuming part. We wanted to make sure every end connected properly and that the maze looked even in terms of height, width, etc. For our inside of the maze we followed our reference maze as a guide and thanks to our asset, it provided us with corner walls as well which shortened our time doing these. It might have been an easier approach with probuilder, but we wanted our maze to have a realistic look and feel to it which is why we decided to go with assets and truly capture the texture of them.

<img width="500" alt="Screenshot 2024-12-18 at 12 19 43 AM" src="https://github.com/user-attachments/assets/d455b7fa-dfa5-44a2-b063-198114adebe5" />


<img width="500" alt="Screenshot 2024-12-18 at 12 20 07 AM" src="https://github.com/user-attachments/assets/f9fcddf4-1296-4f0c-9e64-5bdb95c584f9" />

#### Final Result 

<img width="564" alt="Screenshot 2024-12-18 at 12 23 31 AM" src="https://github.com/user-attachments/assets/5b039fdb-6ee1-44a9-9def-09092f4b8168" />


### Traps

For our traps, we placed them randomly throughout our maze, with a variety of them so it's not too monotonous. 

For our lava pits, we simply ended up taking the floors where we wanted our lava pits to be and removed them(like the image shown above). Then we placed the pits into the empty slots. We adjusted them accordingly with the move tool as well as the scale tool if necessary.


<img width="532" alt="Screenshot 2024-12-18 at 12 27 06 AM" src="https://github.com/user-attachments/assets/39123d1d-2e14-4d55-8575-cfb2c7608919" />


For our spikes, we arranged them varying in sizes so that the player might have to time their jump right or find a potion to help them make the jump safely.


<img width="453" alt="Screenshot 2024-12-18 at 12 29 45 AM" src="https://github.com/user-attachments/assets/a5216b50-cd08-4a9c-9197-3ad4519b33c7" />


For our fires, we had them arranged so that the player jumps over them same with the spikes. We also have them going vertically at some positions, making the path more narrow so the player has to be careful while running or else they can get caught in the fire.


<img width="585" alt="Screenshot 2024-12-18 at 12 33 30 AM" src="https://github.com/user-attachments/assets/f0ba0094-83f1-408e-89a5-835ab647e572" />


### Locked Gate 

We were grateful our asset provided us with a rusty door. We made use of two of them to create our locked gate/exit. We aligned and positioned them accordingly so it fit well the space between the walls.


<img width="562" alt="Screenshot 2024-12-18 at 12 34 26 AM" src="https://github.com/user-attachments/assets/b2333d52-eeef-428b-81dc-56c977ef7254" />


### Lighting

The inside our maze was going to be extremely dark due to the closed off map. We decided to add torches as lighting without taking away the look and feel of medieval ages. It was a bit time consuming to adjust the torches since the prefabs were unfortunatly never developed but for future references, each wall could have a torch. Saving you lots of time when applying props!


#### Final Result 

<img width="524" alt="Screenshot 2024-12-18 at 12 41 02 AM" src="https://github.com/user-attachments/assets/0c89d200-302b-47dd-9680-61e430b7294c" />


---
## Maze Entrance
---
To avoid having the player in an open space where they can wander off we created a start room where the player and spider will be initialized.

Using the same flooring prefab used in our dungeon maze we placed three floor objects next to each other to create a vertical path. Two of these should be children of the first prefab placed for the entrance in order to keep them grouped and facilitate any adjustments needed.

<img width="600" alt="Screenshot 2024-12-17 at 10 36 25 PM" src="https://github.com/user-attachments/assets/8132567e-510d-498f-bc33-61fb3526c500" />

Next we added the walls to enclose the space and avoid the player wandering anywhere that is not inside the maze. After closing the area with the same wall prefabs for the maze it should look like this:

<img width="600" alt="Screenshot 2024-12-17 at 10 39 47 PM" src="https://github.com/user-attachments/assets/cce57bcd-7bce-48d2-b106-db238a2ce537" />

Now we can add our adventurer in front of the maze entrance and the spider behind them. 

<img width="600" alt="Screenshot 2024-12-17 at 10 42 11 PM" src="https://github.com/user-attachments/assets/9943e615-967b-4ec4-9beb-1db4898e3626" />

Lastly details such as torches, barrels, chains and such are added to match the environment of the dungeon.

<img width="752" alt="Screenshot 2024-12-17 at 10 47 18 PM" src="https://github.com/user-attachments/assets/fe073936-3849-4f06-a470-42a4d4233f5f" />

The final touch for the entrance would be to add a ceiling on top in order to conceal the sky and make the player feel trapped.

<img width="750" alt="Screenshot 2024-12-17 at 10 48 31 PM" src="https://github.com/user-attachments/assets/3a070d98-ca5d-4cc9-8370-2f148bf4c57f" />


## Maze Exit
---

For the exit area we decided on a grassy forest area. First place a GameObject of type plane and place it in front of the exit gate. The size/shape of the plane should roughly be around 3 x 3. 

<img width="600" alt="Screenshot 2024-12-17 at 10 51 51 PM" src="https://github.com/user-attachments/assets/0fc06d76-f2d4-4a0b-8a8a-b41db3ac46e3" />

Next go to the materials folder and create a new material for the grass. Import a grass texture and place in the base map and adjust surface options. Place this material on the plane.

<img width="300" alt="Screenshot 2024-12-17 at 10 55 10 PM" src="https://github.com/user-attachments/assets/e17dd3e0-ffc5-4fcd-9641-962b18cdd0e2" />

To create the effect of a thick shrouded forest we cover the surrounding area of the plane with a lot of foliage to avoid the player seeing beyond the map. Using the imported assets that contain the tree prefabs we chose to use, we created a circle around the area.

<img width="600" alt="Screenshot 2024-12-17 at 10 58 58 PM" src="https://github.com/user-attachments/assets/82d0bf20-22ff-41f2-bcb8-ae7b2140a0e0" />

This will be the temporary scenery the player views once exiting the maze before being taken to the win screen. This area is closely related to the win screen. Since the WinFloor has a collider set as a trigger, whenever another collider enters this trigger zone, OnTriggerEnter is called. Inside OnTriggerEnter, the script verifies if the object entering the trigger is tagged as "Player." Once this is confirmed it calls gameMode.PlayerWon() to execute the win scenario/screen.

Win Floor Script:

<img width="400" alt="image" src="https://github.com/user-attachments/assets/431378bb-1d18-4688-b04f-04ae88040de0" />

Basically,the WinFloor makes this act as a special area in the game world that, when touched by the player, signals that the player has achieved the winning condition. It’s a simple trigger-based script that collaborates with another script (WinLose) to manage the overall end-game logic.

WinLose script is added to an empty object called 'GameMode':

<img width="200" alt="image" src="https://github.com/user-attachments/assets/a71c63de-9a18-4977-b4e0-51f1635f279b" />

WinLose script:

<img width="400" alt="Screenshot 2024-12-18 001524" src="https://github.com/user-attachments/assets/43d9ecb6-b0d8-4e9d-a41e-18557803b736" />

This object is what is placed as reference for the WinFloor script:

<img width="350" alt="Screenshot 2024-12-17 233152" src="https://github.com/user-attachments/assets/e871a99f-7a5a-4d75-96c6-e7b12f26e9a0" />


