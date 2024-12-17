# Potions

To help our player out we are going to add potions/powerups to our gameplay. Its important to note that the power ups are permenant throughout the gameplay once acquiered.

We are going to be making 3 different types of potions:
- Health potion: Recovers some of players health
- Speed potion: Increases players moving speed
- Jump potion: Increases the players jump height

The prefabs used to represent the potions are from the mentioned asset in README.

## Health Potion
---
For the health potion we will use the prefab called Bottle_Health. Once we've placed the item in our game and created the prefab of this object, place it into a the prefab folder for this specific project. This is done to maintain an organized system in our project. Do this for every potion bottle prefab.

<img width="500" alt="Screenshot 2024-12-17 at 6 49 42 PM" src="https://github.com/user-attachments/assets/b295b426-23de-4c91-9542-411927fa4d80" />

Select the health potion prefab in the folder and create a tag called HealthPot.

<img width="400" alt="Screenshot 2024-12-17 at 6 45 17 PM" src="https://github.com/user-attachments/assets/8550713a-56b6-45a5-9efc-843b38713093" />

Add a sphere collider component. This is what its sphere collider should look like:

<img width="600" alt="Screenshot 2024-12-17 at 6 55 04 PM" src="https://github.com/user-attachments/assets/e72b0c22-c6b0-43e0-87f0-7909ef3a3176" />


## Speed Potion
---
Select the speed potion prefab in the folder and create a tag called SpeedPot. Add a sphere collider component.

<img width="400" alt="Screenshot 2024-12-17 at 6 41 21 PM" src="https://github.com/user-attachments/assets/00c20496-3b52-4d8b-a2fd-2eb1b9ee311e" />


## Jump Potion
---
Select the speed potion prefab in the folder and create a tag called JumpPot. Add a sphere collider component.

<img width="400" alt="Screenshot 2024-12-17 at 6 41 14 PM" src="https://github.com/user-attachments/assets/03b01c19-e4a3-4003-b951-cd0da70589ee" />


## Script
---
Start a new scrip in the scrip folder called PotionEffects.

Declare private and public variables:
The private variables will store references to other components on the same GameObject, the public floats determine how much each potion affects the player, and the rest are references to TextMeshProUGUI elements that display messages when potions are picked up.

<img width="600" alt="Screenshot 2024-12-17 at 6 57 13 PM" src="https://github.com/user-attachments/assets/8ffb09f3-1140-4ee4-8ac4-92a3d360939e" />

The start function, uses GetComponent<Health>() and GetComponent<PlayerMovement>() to find these scripts on the same GameObject and store references to them. It then hides all the UI texts so they’re not visible until a potion is picked up. 

<img width="440" alt="Screenshot 2024-12-17 at 7 11 29 PM" src="https://github.com/user-attachments/assets/0a8c6628-fe7a-4c28-95fa-de81e85f71ee" />


OnTriggerEnter(Collider other) is called when the player’s collider enters another trigger collider.
Depending on the tag of the collided object, this checks if it’s a Health, Speed, or Jump potion.

<img width="600" alt="Screenshot 2024-12-17 at 7 15 10 PM" src="https://github.com/user-attachments/assets/49826db5-4831-4c18-bea4-f1372bbd08a2" />

Health Potion:
If health is not at maximum, it increases the player’s health and displays a message. If health is full, it does nothing.

Speed Potion:
Increases the player’s speed and shows a message.

Jump Potion:
Increases the player’s jump height and shows a message.

In all cases where the potion is used, the script calls Destroy(other.gameObject) to remove the potion from the scene. After showing the UI message, it calls StartCoroutine(FadeOutText(...)) to begin fading the text out over time.

<img width="722" alt="Screenshot 2024-12-17 at 7 08 35 PM" src="https://github.com/user-attachments/assets/6b2171db-9de0-411a-81b6-961ccaf4a778" />


