# Monster
Asset: [Fantasy Spider](https://assetstore.unity.com/packages/3d/characters/animals/insects/fantasy-spider-236418)

For our monster, we ended up choosing to go with a giant black widow spider to fit with the medieval fantasy style. So, once we downloaded the asset, we dragged the prefab to the scene.

Same with the Player model, we added a 'Capsule Collider' and 'Rigidbody' components.

Then we added a 'Nav Mesh Agent' component:

## AI
For our spider to chase around our player and inflict damage upon range, we added an AI object by creating and empty object (GameObject > Create Empty) and dragging it into the spider object as a child.

### Scripts
Here we added two scripts, first one being 'Spider Sight':

In 'Spider Sight' script, 
