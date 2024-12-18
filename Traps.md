# Traps

To make our game more challenging we added several types of traps that can reduce the player's life or kill them.

Fire and spikes will share one script, these can be grouped due to their similarity in how they deal damage to the player. The lava trap will require its own separate script, because it is unique to the others in how it is the only trap that instantly kills the player.

## Fire
---

To create the fire trap first create an effect particle system object.

<img width="684" alt="Screenshot 2024-12-17 at 8 43 32 PM" src="https://github.com/user-attachments/assets/c41eb1e8-e8b0-4099-976f-81a1df5f7c60" />


For our fire effect we decided to reuse a previously imported material in class called "fire" for the shape of our flame emitters. The fire material has the following:

<img width="400" alt="Screenshot 2024-12-17 at 8 54 55 PM" src="https://github.com/user-attachments/assets/7fc65c42-efd8-48b5-8f55-441bc3990633" />

For the render field the material should be "fire":

<img width="400" alt="Screenshot 2024-12-17 at 8 45 08 PM" src="https://github.com/user-attachments/assets/8337b49f-91b1-44f8-9a98-df6a20021bae" />

The fire traps particle variables should be as follows: 

<img width="400" alt="Screenshot 2024-12-17 at 8 44 21 PM" src="https://github.com/user-attachments/assets/c4de981c-23b3-42b5-b0fa-7330f07de5ee" />

The emission field:

<img width="407" alt="Screenshot 2024-12-17 at 8 44 33 PM" src="https://github.com/user-attachments/assets/abd307d6-349d-4a14-9cbd-32be72a4c7c5" />

The shape:

<img width="407" alt="Screenshot 2024-12-17 at 8 44 45 PM" src="https://github.com/user-attachments/assets/93977267-6ce7-43e3-a79c-107b0d838f36" />

Color over lifetime:

<img width="395" alt="Screenshot 2024-12-17 at 8 44 56 PM" src="https://github.com/user-attachments/assets/611741dc-234f-4145-a76e-ae7f04857ca1" />


Finally add a capsule collider and adjust by elongating as needed. The final product should look like:

<img width="684" alt="Screenshot 2024-12-17 at 8 56 52 PM" src="https://github.com/user-attachments/assets/7f7f1fba-2eec-484e-adc0-e60fe4d041c4" />


Attach the Damage Zone script (Discussed below) to this effect to ensure the player is affected by theh flames.

## Spikes
---

To create the spikes first create a cube object and rotate it approximately to a 45 degree angle. Create a new material that looks metallic for the spikes by importing a metallic texture and placing this in the new materials base map. Make sure you create this in the projects material folder. The settings for the material should be:

<img width="500" alt="Screenshot 2024-12-17 at 8 23 17 PM" src="https://github.com/user-attachments/assets/8eff5979-b557-42f3-bbd5-994b4fb4843a" />

Put this material on top of the first cube we made and duplicate it. Place the duplicated object inside the first as a child. It will look like this so far.

<img width="500" alt="Screenshot 2024-12-17 at 8 17 48 PM" src="https://github.com/user-attachments/assets/a04c0732-121e-4bcb-abf1-df39f18de9d7" />

Duplicate this 2 more times to create a row of spikes:

<img width="600" alt="Screenshot 2024-12-17 at 8 15 39 PM" src="https://github.com/user-attachments/assets/ad9622e1-3ab0-42e5-9f8e-6216852b50ba" />

Duplicate this row and put them beside one another to create two rows of spikes.

<img width="600" alt="Screenshot 2024-12-17 at 8 28 21 PM" src="https://github.com/user-attachments/assets/48b548e8-e32f-4f5e-8c56-45e6b0538854" />

All these objects should be grouped together in a folder in the game. This will be one instance of a spike trap. Select the spikes folder and add a box collider to the spikes. This will help detect if the player comes in contact with the spikes while playing. Next we will add the Damage Zone Script, once we create it.

<img width="600" alt="Screenshot 2024-12-17 at 8 15 39 PM" src="https://github.com/user-attachments/assets/4d00da83-f348-4c9c-8626-74c5c211ff62" />


## Damage Zone Script
---
This script is attached to the spikes and flame traps in the game to determine the damage they deal to the player when in contact.

The first two public variables are for determining how much damage is dealt each time the player is hurt and how many seconds pass between each damage application. The private float keeps track of the last time damage was dealt to the player.

<img width="500" alt="Screenshot 2024-12-17 at 8 36 19 PM" src="https://github.com/user-attachments/assets/72876897-8402-4ff1-ac19-e32079466adc" />

This script is attached to a GameObject trap with a trigger collider so when the player steps inside this collider, the OnTriggerStay method is called every frame. Instead of continuously damaging the player every frame, the code uses damageInterval to apply damage periodically. The Time.time function gives the current time in seconds since the start of the game, and by comparing Time.time - lastDamageTime to damageInterval, the script ensures damage is only dealt after the specified delay passes.

The script tracks the players health and if found, it subtracts damageAmount from playerHealth.amount.
Anytime damage is dealt to the player a message is printed stating the amount of damage the player took.

<img width="600" alt="Screenshot 2024-12-17 at 8 36 52 PM" src="https://github.com/user-attachments/assets/8a4f04e5-8e6e-4ab0-851d-e83344bce50f" />

## Lava pit
---

To create our lava pit we use the hole trap prefab from the assets imported. Next we create a GameObject of type plane. Create a new material in the material folder for the lava. Import a lava texture and assign fields as follows: 

<img width="401" alt="Screenshot 2024-12-17 at 9 03 19 PM" src="https://github.com/user-attachments/assets/a6b3e3dc-3909-4b50-acd2-ca2942848ea2" />

Place the plane as a child of the hole trap prefab. Size the plane to fit inside the hole trap space, then place the newly created lava material on the plane. Add a box collider component. Next we will create the Lava Damage script and attach it to this.

<img width="500" alt="Screenshot 2024-12-17 at 9 06 49 PM" src="https://github.com/user-attachments/assets/db246b25-452d-460a-8230-3b388db4b1cf" />


## Lava Damage script
---

This script kills the player if it makes contact with the lava regardless of a full health status.

The public float determines the amount of damage the lava deals to the player when they touch it, which is 100 to ensure the player dies even at full life. The method OnTriggerEnter is called once when a Collider with "Is Trigger" enabled is entered by another collider. Then it will check if the object that entered the trigger zone is tagged as "Player." It will then try to retrieve the Health component from the player object, if the player has a Health component it reduces the player's health by the specified damage amount. Finally it prints a message showing how much damage the player took and their remaining health, which will be 0 since it will take all their life. 

This script is attached to all the lava pits:

<img width="600" alt="Screenshot 2024-12-17 at 9 13 09 PM" src="https://github.com/user-attachments/assets/510b92ca-12d2-459f-baaf-a2e39a851192" />



