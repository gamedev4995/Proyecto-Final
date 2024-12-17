# Potions

To help our player out we are going to add potions/powerups to our gameplay.

We are going to be making 3 different types of potions:
- Health potion: Recovers some of players health
- Speed potion: Increases players moving speed
- Jump potion: Increases the players jump height

The prefabs used to represent the potions are from the mentioned asset in README.

## Health Potion
---
For the health potion we will use the prefab called Bottle_Health. Once we've placed the item in our game and created the prefab of this object, place it into a the prefab folder for this specific project. This is done to maintain an organized system in our project. Do this for every potion bottle prefab.

<img width="500" alt="Screenshot 2024-12-17 at 6 49 42 PM" src="https://github.com/user-attachments/assets/b295b426-23de-4c91-9542-411927fa4d80" />

Select the health potion prefab in the folder and create a tag called HealthPot

<img width="400" alt="Screenshot 2024-12-17 at 6 45 17 PM" src="https://github.com/user-attachments/assets/8550713a-56b6-45a5-9efc-843b38713093" />

Add a sphere collider component.

<img width="600" alt="Screenshot 2024-12-17 at 6 55 04 PM" src="https://github.com/user-attachments/assets/e72b0c22-c6b0-43e0-87f0-7909ef3a3176" />


## Speed Potion
---
Select the speed potion prefab in the folder and create a tag called SpeedPot

<img width="500" alt="Screenshot 2024-12-17 at 6 41 21 PM" src="https://github.com/user-attachments/assets/859ae25f-bb87-44ad-9b0e-a8eb2155d053" />


## Jump Potion
---
Select the speed potion prefab in the folder and create a tag called JumpPot

<img width="500" alt="Screenshot 2024-12-17 at 6 41 14 PM" src="https://github.com/user-attachments/assets/715e28b2-dc08-4373-9c75-72eac1f095fd" />

## Script
---
Start a new scrip in the scrip folder called PotionEffects.

Declare private and public variables:

<img width="600" alt="Screenshot 2024-12-17 at 6 57 13 PM" src="https://github.com/user-attachments/assets/8ffb09f3-1140-4ee4-8ac4-92a3d360939e" />

