# Maze
---

To create the maze first we mapped out and generated a few iterations of different maze sizes to create a maze that wasnt to large and difficult or too easy.



## Entrance / Exit
---
To avoid the having the player in an open space where they can wonder off we created a start room where the player and spider will be initialized.

Using the same flooring prefab used in our dungeon maze we placed three floor objects next to each other to create a vertical path. Two of these should be children of the first prefab placed for the entrance in order to keep them grouped and facilitate any adjustments needed.

<img width="600" alt="Screenshot 2024-12-17 at 10 36 25 PM" src="https://github.com/user-attachments/assets/8132567e-510d-498f-bc33-61fb3526c500" />

Next we added the walls to enclose the space and avoid the player wandering anywhere that is not inside the maze. After closing the area with the same wall prefabs for the maze it should look like this:

<img width="754" alt="Screenshot 2024-12-17 at 10 39 47 PM" src="https://github.com/user-attachments/assets/cce57bcd-7bce-48d2-b106-db238a2ce537" />

Now we can add our adventurer in front of the maze entrance and the spider behind them.
