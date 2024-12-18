# Player
Asset: Fantasy RPG Human Male

To start off, we placed the prefab of the human model from our asset onto the scene.

Then we proceeded to add 'Rigidbody' component:

Then came the collider. We went for the 'capsule collider' and adjusted the center and radius:

## Scripts
### Player Movement
Then we added a script dedicated for the player movement controls called "PlayerMovement". In the script, we have the following libraries and variables (keep in mind we used Unity's newest input system).

For the first function, on Awake(), we have the following:

Then we have the OnMove function:

Next, the OnLook function:

For the Jump function, we have OnJump and OnCollisionEnter which detects where or not the player is back on the ground, preventing infinite jumps.

Lastly for this script, on Update(), force and torque is applied:

___Note:___ Values adjusted for public variables.

Result:
[gif]

### Health
For our second script, we called it "Health" in order to manage the amount of the player's health. The following libraries, variables and code were added:

## Animation
__Note:___ Unfortunately we were only able to apply animation for the player and not the monster (spider) due to an odd behavior with the asset.

For animations, one must first add an 'Animator Controller' in projects folder and then an 'Animator' component, however in our case, the asset model prefab already came with them set up.

Then, in the 'Animator' tab, we dragged the animations that we wanted to use from our asset:

Then we right clicked on each animation to 'Make Transition' to other animations. In our case we went from Entry to Idle, Idle to Jump (vice versa), and from Idle to Running (vice versa):

Afterwards, we went to the 'Parameter' tab on the side and created, with the '+', a 'bool' called "moving" and a 'trigger' called "jump".

With these created, we could then set up the conditions by clicking on each arrow in the transitions and to the right in 'Conditions' the '+' was pressed and set up the conditions logically.

1. For Idle to Jump: we added condition 'jump'
2. For Jump to Idle: we added condition 'moving' and 'false'
3. For Idle to Running: we added condition 'moving' and 'true'
4. For Running to Idle: we added condition 'moving' and 'false'

Back to the Player Movement script, we added the following variable:

For the running animation, we added the following line of code in OnMove():

For the jump animation, we added the following in OnJump():

Result:
[gif]
