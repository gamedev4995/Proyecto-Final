# Player
Asset: [Fantasy RPG Human](https://assetstore.unity.com/packages/3d/characters/humanoids/humans/free-modular-character-fantasy-rpg-human-male-228952)

To start off, we placed the prefab of the human model from our asset onto the scene.

<img width="300" alt="Screenshot 2024-12-17 210853" src="https://github.com/user-attachments/assets/d71ce008-4a40-42f3-94ae-3eede36475e1" />

Then we proceeded to add 'Rigidbody' component:

<img width="300" alt="Screenshot 2024-12-17 214106" src="https://github.com/user-attachments/assets/150ea001-767f-482b-bee7-1ce3d73c2eb1" />

Then came the collider. We went for the 'Capsule Collider' and adjusted the center and radius:

<img width="300" alt="Screenshot 2024-12-17 222247" src="https://github.com/user-attachments/assets/a5ae15c1-acb5-481d-ad9f-c42d87d57442" />

___Note:___ We also created a 'Physics Material' called 'NoFriction', set all values to 0 and dragged it onto the 'Material' section in the collider. With this applied to the character model and walls, the player would no longer get "stuck" on the walls during contact.

<img width="300" alt="image" src="https://github.com/user-attachments/assets/fc753c12-35d5-4c96-8a5f-f5e2ab367f27" />

We also added a 'Player' tag and layer for future interactions.

<img width="300" alt="Screenshot 2024-12-17 214230" src="https://github.com/user-attachments/assets/417bc64b-82bb-4ca9-92f5-34d755d3f7f5" />

## Scripts
### Player Movement
Then we added a script dedicated for the player movement controls called "PlayerMovement". In the script, we have the following libraries and variables (keep in mind we used Unity's newest input system).

<img width="600" alt="Screenshot 2024-12-17 223007" src="https://github.com/user-attachments/assets/854d2e33-9603-4431-82bb-f55bdeefa629" />

For the first function, on Awake(), we have the following:

<img width="400" alt="Screenshot 2024-12-17 223021" src="https://github.com/user-attachments/assets/284e4c33-7e3b-4235-a264-ee7e04ab1d15" />

Then we have the OnMove function:

<img width="400" alt="Screenshot 2024-12-17 223031" src="https://github.com/user-attachments/assets/ead45905-62f7-4aaf-be56-5ca73309495f" />

Next, the OnLook function:

<img width="400" alt="Screenshot 2024-12-17 223042" src="https://github.com/user-attachments/assets/ebb4c091-8c1e-4521-848a-3d6cb7490681" />

For the jumping mechanic, we have OnJump() and OnCollisionEnter() which detects whether or not the player is back on the ground, preventing infinite jumps.

<img width="400" alt="Screenshot 2024-12-17 223051" src="https://github.com/user-attachments/assets/1068a9b0-4bbc-4963-976c-8f9b2b4b737d" />

<img width="500" alt="Screenshot 2024-12-17 223103" src="https://github.com/user-attachments/assets/6658b42c-7977-4951-a02a-55ecfcb7930e" />

Lastly for this script, on Update(), force and torque is applied:

<img width="600" alt="image" src="https://github.com/user-attachments/assets/92dffc3c-d465-4c19-9719-922ae1e7eca0" />

___Note:___ Values adjusted for public variables.

Result:

![PlayerMovementVid-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/01691b26-3c0f-4e11-a515-e9113cd83620)


### Health
For our second script, we called it "Health" in order to manage the amount of the player's health. The following libraries, variables and code were added:

<img width="300" alt="Screenshot 2024-12-17 222552" src="https://github.com/user-attachments/assets/e371dd5b-423d-488b-bc30-602247912046" />

## Animation
__Note:___ Unfortunately we were only able to apply animation for the player and not the monster (spider) due to an odd behavior with the asset.

For animations, one must first add an 'Animator Controller' in projects folder and then an 'Animator' component, however in our case, the asset model prefab already came with them set up.

<img width="300" alt="Screenshot 2024-12-17 214043" src="https://github.com/user-attachments/assets/f9cd9383-dbe8-4774-a632-0dcf4988cc10" />

Then, in the 'Animator' tab, we dragged the animations that we wanted to use from our asset:

<img width="450" alt="Screenshot 2024-12-17 222901" src="https://github.com/user-attachments/assets/1f295554-2a77-4738-962f-907464fb534d" />

Then we right clicked on each animation to 'Make Transition' to other animations. In our case we went from Entry to Idle, Idle to Jump (vice versa) Idle to Running (vice versa), and Running to Jump (vice versa):

<img width="450" alt="Screenshot 2024-12-17 221426" src="https://github.com/user-attachments/assets/cfd05eb3-74b8-46ea-b7ac-bae9f630e288" />

Afterwards, we went to the 'Parameter' tab on the side and created, with the '+', a 'bool' called "moving" and a 'trigger' called "jump".

<img width="300" alt="Screenshot 2024-12-17 221438" src="https://github.com/user-attachments/assets/78bc4a8b-13e0-4a63-909a-f4b4ca4e564f" />

With these created, we could then set up the conditions by clicking on each arrow in the transitions and to the right in 'Conditions' the '+' was pressed and set up the conditions logically.

<img width="450" alt="Screenshot 2024-12-17 221618" src="https://github.com/user-attachments/assets/a48edd8f-2015-4fb7-a7e8-e2c3c6aa325a" />

1. For Idle to Jump: we added condition 'jump'
2. For Jump to Idle: we added condition 'moving' and 'false'
3. For Idle to Running: we added condition 'moving' and 'true'
4. For Running to Idle: we added condition 'moving' and 'false'
5. For Running to Jump: we added condition 'jump'
6. For Jump to Running: we added condition 'moving' and 'true'

Back to the Player Movement script, we added the following variable:

<img width="300" alt="Screenshot 2024-12-17 223418" src="https://github.com/user-attachments/assets/cf2e8ddd-de31-4acf-ae8c-a614192fe990" />

On Awake(), we obtain the 'Animator' component:

<img width="400" alt="Screenshot 2024-12-17 223423" src="https://github.com/user-attachments/assets/113fe2fa-9b3d-4045-aab9-f389ce3af43f" />

For the running animation, we added the following line of code in OnMove():

<img width="400" alt="Screenshot 2024-12-17 223431" src="https://github.com/user-attachments/assets/ea599c21-2562-45d7-ae74-23fcebe9528e" />

For the jump animation, we added the following in OnJump():

<img width="400" alt="Screenshot 2024-12-17 223442" src="https://github.com/user-attachments/assets/ce3c8435-faf2-4006-81ee-31de99b4d136" />

Result:
![PlayerAnimationVid-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/cadeddfd-3f61-4730-a3fb-69bdf85425d3)


## Camera (First Person)
For the first person perspective of our game, we first placed the camera as a child of our character asset:

<img width="200" alt="Screenshot 2024-12-17 220748" src="https://github.com/user-attachments/assets/83281740-76c4-4aa6-af63-d661b9eeb792" />

Then we created a script called 'Camera Controller' which enables the vertical control of the camera since the horizontal one was already established in the PlayerMovement rotation.

<img width="300" alt="image" src="https://github.com/user-attachments/assets/6b0d8c62-6699-4ef7-9ba4-09b618f06846" />

For this script we added the following libraries and variables:

<img width="400" alt="image" src="https://github.com/user-attachments/assets/6f3428b4-3178-4dd0-aad8-b31f9a8bdabb" />

And lastly the following Awake() and Update() code:

<img width="400" alt="Screenshot 2024-12-17 225601" src="https://github.com/user-attachments/assets/1efcd647-8753-4349-832d-80b234a1ab54" />

Final Result:

![FirstPersonVid-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/a757c721-c1f1-4e49-baaf-7d3f1f66fd26)
