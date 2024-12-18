# Traps

To make our game more challenging we added several types of traps that can reduce the players life or kill them.

Fire and spikes will share one script, these can be grouped due to their similarity in how they deal damage to the player. The lava trap will require its own seperate script, because it is unique to the others in how it is the only trap that instantly kills the player.

## Fire
---
To create the fire trap first create an effect particle system object. 


Add a capsulte collider. Adjust by elongating as needed.

## Spikes
---
To create the spikes first create a cube object and rotate it approximately to a 45 degree angle. Create a new material that looks metallic for the spikes by importing a metallic texture and placing this in the new materials base map. Make sure you create this in the projects material folder. The settings for the material should be:

<img width="500" alt="Screenshot 2024-12-17 at 8 23 17 PM" src="https://github.com/user-attachments/assets/8eff5979-b557-42f3-bbd5-994b4fb4843a" />

Put this material on top the first cube we made and duplicate it. Place the duplicated object inside the first as a child. It will look like this so far.

<img width="500" alt="Screenshot 2024-12-17 at 8 17 48 PM" src="https://github.com/user-attachments/assets/a04c0732-121e-4bcb-abf1-df39f18de9d7" />

Duplicate this 2 more times to create a row of spikes:

<img width="600" alt="Screenshot 2024-12-17 at 8 15 39 PM" src="https://github.com/user-attachments/assets/ad9622e1-3ab0-42e5-9f8e-6216852b50ba" />

Duplicate this row and put them beside one another to create two row of spikes.
<img width="600" alt="Screenshot 2024-12-17 at 8 28 21 PM" src="https://github.com/user-attachments/assets/48b548e8-e32f-4f5e-8c56-45e6b0538854" />

All these objects should be grouped together in a folder in the game. This will be one instance of a spikes trap. Select the spikes folder and add a box collider to the spikes. This will help detect if the player comes in contact with the spikes while playing. Next we will add the Damage Zone Script, once we create it.

<img width="600" alt="Screenshot 2024-12-17 at 8 15 39 PM" src="https://github.com/user-attachments/assets/4d00da83-f348-4c9c-8626-74c5c211ff62" />


## Damage Zone Script
---

The first two public variables are for determining how much damage is dealt each time the player is hurt and how many seconds pass between each damage application. The private float keeps track of the last time damage was dealt to the player.

<img width="500" alt="Screenshot 2024-12-17 at 8 36 19 PM" src="https://github.com/user-attachments/assets/72876897-8402-4ff1-ac19-e32079466adc" />

This script is attached to a our GameObject trap with a trigger collider so when the player steps inside this collider, the OnTriggerStay method is called every frame. Instead of continuously damaging the player every frame, the code uses damageInterval to apply damage periodically. The Time.time function gives the current time in seconds since the start of the game, and by comparing Time.time - lastDamageTime to damageInterval, the script ensures damage is only dealt after the specified delay passes.

The script tracks the players health and if found, it subtracts damageAmount from playerHealth.amount.
Anytime damage is dealt to the player a message is printed stating the amount of damage the player took.

<img width="600" alt="Screenshot 2024-12-17 at 8 36 52 PM" src="https://github.com/user-attachments/assets/8a4f04e5-8e6e-4ab0-851d-e83344bce50f" />

## Lava pit
---

## Lava damage script
---

