# Keys

In order to escape the maze the player must acquire 3 keys in order for the exit gate to open. 

To make the keys first we create a prefab in our project prefab folder of the asset from the package we imported. The prefab will already have its mesh filter, mesh renderer and mesh collider. 

The only component we need to add is the box collider and a new tag called “Key”


<img width="400" alt="Screenshot 2024-12-17 at 7 29 05 PM" src="https://github.com/user-attachments/assets/970d49e8-9602-4f1a-b61f-3c7b69b556f4" />


## Key Collection Script

Create a new script in the project script folder called KeyCollection.
Declare public variables to track how many keys the player has currently collected, how many keys are required to open the gate (3) and a reference to the actual gate object in the scene that the player must open. The two TextMeshPro UI elements are for displaying the current number of keys found and when the gate is opened.


<img width="600" alt="Screenshot 2024-12-17 at 7 34 53 PM" src="https://github.com/user-attachments/assets/8f79943e-c9a8-4f75-aeec-820ea07edbbc" />


In the start Method, it initially hides both UI messages (keysFound and gateOpened) so they aren’t visible at the start. It ensures the text only shows up when keys are found or the gate opens.


<img width="600" alt="Screenshot 2024-12-17 at 7 43 15 PM" src="https://github.com/user-attachments/assets/2a1c93db-7461-4395-ac31-6b0297653d92" />


The OnTriggerEnter method is called when the GameObject with this script, the player, enters a trigger collider.
If the collided object has the tag "Key", the player has collected a key. Then it increases keysCollected by 1, logs the new total, shows the keysFound text and updates it to display the current key count. Afterward it removes the key object from the scene to prevent re-collection. If the player now has enough keys (keysCollected >= keysNeeded), it calls OpenGate() to open the gate.


<img width="602" alt="Screenshot 2024-12-17 at 7 47 33 PM" src="https://github.com/user-attachments/assets/0dde2081-960d-4a8e-a3f9-5f98de24654a" />


OpenGate Method checks if the gate reference is set. If so, destroys the gate GameObject, simulating the gate opening. Logs a message that the gate opened and hides the keysFound text since keys are no longer relevant once the gate is open. When the gate opens the gateOpened text pops up to inform the player that the gate is now open, then the coroutine FadeOutText gradually fades out the "Gate Opened!" message.


<img width="500" alt="Screenshot 2024-12-17 at 7 48 53 PM" src="https://github.com/user-attachments/assets/7d972dd2-f5c8-427a-b94b-18c7615ee315" />


FadeOutText Coroutine methid takes a TextMeshProUGUI element and gradually reduces its opacity (alpha) from fully visible (1) to invisible (0) over fadeDuration seconds. Uses Mathf.Lerp to smoothly interpolate the alpha value. After the loop finishes, it sets the text GameObject inactive, removing it from view entirely. Using a coroutine allows the fade to happen over multiple frames rather than instantly.


<img width="600" alt="Screenshot 2024-12-17 at 7 52 55 PM" src="https://github.com/user-attachments/assets/9ae9615f-a94f-46cb-9d8e-c05d3f04d91d" />




