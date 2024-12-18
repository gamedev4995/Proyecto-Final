# Monster
Asset: [Fantasy Spider](https://assetstore.unity.com/packages/3d/characters/animals/insects/fantasy-spider-236418)

For our monster, we ended up choosing to go with a giant black widow spider to fit with the medieval fantasy style. So, once we downloaded the asset, we dragged the prefab to the scene.
<img width="160" alt="" src="" />
![image](https://github.com/user-attachments/assets/43d5740b-c7e1-4bd2-a332-42352f4caa29)

Same with the Player model, we added a 'Capsule Collider' and 'Rigidbody' components.

![Screenshot 2024-12-17 214322](https://github.com/user-attachments/assets/2b28c3ce-8e96-457f-8dc2-bd45cb8d2a4d)

![Screenshot 2024-12-17 214337](https://github.com/user-attachments/assets/64c612c2-7646-4723-81d4-03ebd4babdb0)

Then we added a 'Nav Mesh Agent' component:
![Screenshot 2024-12-17 214351](https://github.com/user-attachments/assets/1748da76-c06f-46ec-91f6-67b5c8e38f30)

Additionally, we assigned a layer called 'Enemy' for future interactions.
![Screenshot 2024-12-17 214251](https://github.com/user-attachments/assets/828bd492-0dc8-4750-9b43-4e8b3a47c16f)

## AI
For our spider to chase around our player and inflict damage upon range, we added an AI object by creating and empty object (GameObject > Create Empty) and dragging it into the spider object as a child.
![Screenshot 2024-12-17 220730](https://github.com/user-attachments/assets/f51b4f5e-d6ce-4bae-832f-32a6350926a8)

### Scripts
Here we added two scripts, first one being 'Spider Sight':
![Screenshot 2024-12-17 221045](https://github.com/user-attachments/assets/fd434b39-7349-4174-a0a3-8b9cc8e8f676)

In 'Spider Sight' script, we used the following libraries and variables:

For Update() we placed the following code:

For visuals, we drew gizmos:

Then came the second script which we called 'SpiderFSM':
![Screenshot 2024-12-17 221035](https://github.com/user-attachments/assets/95897e14-c2fa-4bbc-b12b-cb6e8451b0ef)

Here we used the following libraries and variables:

On Awake() we obtain the Nav Mesh Agent previously created:

For the different states, we have ChasePlayer() and AttackPlayer():

Then we have Attack function for when it is called in AttackPlayer():

Then on Update() we call the states:

We also have gizmos for the ranges to appear visually:
![Screenshot 2024-12-17 212941](https://github.com/user-attachments/assets/8634e194-3230-4722-8a17-09c9ecf751b2)

Lastly, we have LookTo() for the spider to remain staring in the right direction.

___Note:___ Values were adjusted and placed the SpiderSight and Player prefab in their respective places.

### Navigation
First, we made sure that all walls from the maze were 'static'.
![image](https://github.com/user-attachments/assets/61e5561e-2ff2-4a2d-822a-ac5caaf24a77)

Then, in the 'Navigation' tab, we properly 'Baked' the area we wanted the spider to traverse.
![Screenshot 2024-12-17 214525](https://github.com/user-attachments/assets/0834fd1b-5e40-437c-af59-b74942a42f9b)

___Note:___ Knowing later on we would incorporate holes in the floor as traps, a way we avoided the spider from being blocked during the baking, was to create a plane that took over the entire flooring.
![Screenshot 2024-12-17 214648](https://github.com/user-attachments/assets/6f4726cf-9167-4e89-9d5a-47a5d16c9f36)

Then created a unique layer for it called 'InvisibleFloor':
![Screenshot 2024-12-17 215215](https://github.com/user-attachments/assets/318761ec-48a2-4410-9634-ff30ccefb956)

Where in the Edit > Project Settings > Physics we unchecked the interaction between Player and InvisibleFloor so that the play is still able to fall in the hole traps.
![Screenshot 2024-12-17 215305](https://github.com/user-attachments/assets/f5d33244-0857-4043-898c-1984a5d6197a)

Then we baked the area and unchecked the 'Mesh Renderer' so that it became invisble to the eye.
![Screenshot 2024-12-17 215738](https://github.com/user-attachments/assets/41b506db-8956-464d-b06f-eaa16c98dc07)

Final Result:
[gif]

