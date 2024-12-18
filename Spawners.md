# Spawners
---
Items and keys both have seperate spawners. This is important because the gameplay depends on their random placement for every game. First we will create an empty object that will manage both these spanwers, named SpawnManager. This will hold both spawner scripts for the key and items. Then we can place empty objects to be either key or item spawners and place them around acceptable locations in the maze.

<img width="300" alt="Screenshot 2024-12-17 at 9 54 37 PM" src="https://github.com/user-attachments/assets/e7d86a27-d204-4ff0-b194-a193ed0ebd48" />


## Key Spawn Manager
---
The keys are one of the most essential parts of the game. If they all spawn in one place then the player wins in one go. Its also important that the keys spawn in different locations everytime the game is replayed to avoid the player memorizing the keys locations.

First we create two arrays in the script. One to hold the different types of key prefabs that can be spawned and another for locations in the scene where a key can be placed. We declare the total number of keys to spawn in the scene and then create a list to keep track of which spawn points have already been used, so no location is reused.

<img width="600" alt="Screenshot 2024-12-17 at 9 13 09 PM" src="https://github.com/user-attachments/assets/36e16379-fbd4-4c21-942b-2821178567f9" />

SpawnKeys keeps track of how many keys have been placed so far. Keys will continue spawning until we've placed the desired number of keys. The script selects keys at random from a given list of key prefabs and places them at specific points in the scene. Each key could represent a collectible item. In terms of the spawn locations, it ensures each selected spawn location is used only once. If a spawn point is already taken, the script picks another location. This prevents multiple keys from appearing in the same exact spot, promoting better distribution of items throughout the level. There is also random variation seen in how both the key type and its final orientation have random elements. Different keys from the keysToSpawn array could spawn, and each key’s rotation around the vertical axis is randomized. This creates a less predictable, more dynamic placement, making the game feel more varied each time. The entire spawning logic runs in the Start() method, meaning as soon as the game or scene begins, the keys are placed. 

<img width="600" alt="Screenshot 2024-12-17 at 9 42 58 PM" src="https://github.com/user-attachments/assets/fa4018de-f398-4955-9860-c68c6917848a" />

## Item Spawn Manager
---

The items spawner manager is also important due to the fact that its important to regulate how many items appear of everytype of power-up to make sure the player doenst become overpowerd.

The script start by creating two arrays one for different item prefabs available to spawn and the other for potential spawn locations in the maze. Then we declare the max amount of items that can be spawned, in this case, 6. We also declare a list to keep track of which spawn points have been used. 

The start method will spawn all the items when the game starts by calling SpawnItems.

<img width="600" alt="Screenshot 2024-12-17 at 9 55 11 PM" src="https://github.com/user-attachments/assets/123e50d2-0792-4259-b7ca-4f29d73535e2" />

SpawnItems will calculate how many items of each type to spawn. For example, if totalItemsToSpawn = 6 and there are 3 item types, itemsPerType will be 2, meaning spawn 2 items of each type. Then it will loop through each type of item in the itemsToSpawn array and for the current item type, it will spawn the required number of items. SpawnAtRandomPoint(item) will then be calles and the item will spawn at a random unused spawn point.

<img width="600" alt="Screenshot 2024-12-17 at 9 55 19 PM" src="https://github.com/user-attachments/assets/b68c0352-040b-4e0e-ba8a-2cbd2ac17581" />

The way SpawnAtRandomPoint works is by first selecting a random spawn point until one is found that hasn't been used before. This ensures each spawn point is only used once. Then it will record the chosen spawn point so it won't be reused. Finally it instantiates the item at the chosen spawn point's position.

<img width="600" alt="Screenshot 2024-12-17 at 9 55 24 PM" src="https://github.com/user-attachments/assets/9bb446e6-c10c-43e1-9ec0-d41233507793" />




