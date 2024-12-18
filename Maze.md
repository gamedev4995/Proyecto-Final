# Maze
---

To create the maze first we mapped out and generated a few iterations of different maze sizes to create a maze that wasn't too large and difficult or too easy.



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

<img width="600" alt="image" src="https://github.com/user-attachments/assets/431378bb-1d18-4688-b04f-04ae88040de0" />

Basically,the WinFloor makes this act as a special area in the game world that, when touched by the player, signals that the player has achieved the winning condition. It’s a simple trigger-based script that collaborates with another script (WinLose) to manage the overall end-game logic.

WinLose script is added to an empty object called 'GameMode':

<img width="600" alt="image" src="https://github.com/user-attachments/assets/a71c63de-9a18-4977-b4e0-51f1635f279b" />

WinLose script:

<img width="600" alt="Screenshot 2024-12-18 001524" src="https://github.com/user-attachments/assets/43d9ecb6-b0d8-4e9d-a41e-18557803b736" />

This object is what is placed as reference for the WinFloor script:

<img width="600" alt="Screenshot 2024-12-17 233152" src="https://github.com/user-attachments/assets/e871a99f-7a5a-4d75-96c6-e7b12f26e9a0" />


