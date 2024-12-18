# Monster
Asset: [Fantasy Spider](https://assetstore.unity.com/packages/3d/characters/animals/insects/fantasy-spider-236418)

For our monster, we ended up choosing to go with a giant black widow spider to fit with the medieval fantasy style. So, once we downloaded the asset, we dragged the prefab to the scene.

Same with the Player model, we added a 'Capsule Collider' and 'Rigidbody' components.

Then we added a 'Nav Mesh Agent' component:

## AI
For our spider to chase around our player and inflict damage upon range, we added an AI object by creating and empty object (GameObject > Create Empty) and dragging it into the spider object as a child.

### Scripts
Here we added two scripts, first one being 'Spider Sight':

In 'Spider Sight' script, we used the following libraries and variables:

For Update() we placed the following code:

For visuals, we drew gizmos:

Then came the second script which we called 'SpiderFSM':

Here we used the following libraries and variables:

On Awake() we obtain the Nav Mesh Agent previously created:

For the different states, we have ChasePlayer() and AttackPlayer():

Then we have Attack function for when it is called in AttackPlayer():

Then on Update() we call the states:

We also have gizmos for the ranges to appear visually:

Lastly, we have LookTo() for the spider to remain staring in the right direction.

Result:
[image]

___Note:___Values were adjusted and placed the SpiderSight and Player prefab in their respective places.

### Navigation
First, we made sure that all walls from the maze were 'static'.

Then, in the 'Navigation' tab, we properly 'Baked' the area we wanted the spider to traverse.

Final Result:
[gif]

