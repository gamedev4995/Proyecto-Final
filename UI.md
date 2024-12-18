# UI

## Game Play UI
For our in game UI, we decided to incorporate:
1. healthbar: so our players can keep track of how much health they have left
2. key counter: to keep track how many keys have been found 
3. potion usage: texts to let the player know which potions they've consumed 
4. gate notice: text that notifies the player when the gate is officially opened(when they've collected all the keys)

_Notes!:_
To start off, we need to go to window > package manager > unity registry > and import 2d sprite. We also need to add the GUI Parts Asset which can be found in the asset store (Window > Assets Store > GUI parts).

Since wanted to stick with our medieval theme, we imported a desired font called 'Breath Fire II', courtesy of www.dafont.com, to fit our game's aesthetic. To import new fonts we have to go to Window > TextMeshPro > Font Asset Creator. This will bring up a new window but we simply dragged our already downloaded font into source font file and hit Generate Font Atlas and save.

### Healthbar
Firstly add the gameobject UI > 'Image'. Now on your proyect window, search for the GUI Parts folder, we'll use hp_line and hp_frame for our healthbar.

<img width="160" alt="Screenshot 2024-12-17 at 8 24 32 PM" src="https://github.com/user-attachments/assets/573fb04a-f1de-46fc-9b42-3d1e59dcd7fc" />

To create the hp_line, drag the asset to the inspector and into the image tab where it says source image.

<img width="291" alt="Screenshot 2024-12-17 at 8 41 55 PM" src="https://github.com/user-attachments/assets/9b33e332-f319-49b9-9424-419023177a36" />
               
  <img width="400" alt="Screenshot 2024-12-17 at 8 44 45 PM" src="https://github.com/user-attachments/assets/80fd1ed1-a4e9-4058-abd4-cc8201b3bb24" />


For our size adjustment we used the rec tool to adjust the width and height as well as the move tool to position it to where we wanted our healthbar to pop up when playing.


<img width="400" alt="Screenshot 2024-12-17 at 8 47 18 PM" src="https://github.com/user-attachments/assets/42ba4e8a-9c3c-416b-b11f-aae7144e3be4" />

Next, on our proyect window, click the +'s dropdown > 2D > Sprites > Square. We'll use this sprite and replace the image source with our hp_line by dragging it to the inspector and into the image tab where it says source image. Then we changed the color to green to represent health.

<img width="400" alt="Screenshot 2024-12-17 at 8 56 36 PM" src="https://github.com/user-attachments/assets/0ea3717f-6b48-4af7-90d4-ac9d86438f7e" />

To finish our healthbar, for our frame we copy and pasted the image object and then replaced the sprite in image source on the inspector tab, to the hp_frame asset. Resulting us as such:

<img width="400" alt="Screenshot 2024-12-17 at 8 59 52 PM" src="https://github.com/user-attachments/assets/b844bafe-89d3-44d2-8688-9fe0b5c32320" />


We wanted our healthbar to go down whenever the player lost any health. For this we added a new script component in the healthbar image and named it lifebar. In our script we added our code to update the hp line as our player lost/gained any health.

<img width="400" alt="Screenshot 2024-12-17 at 9 02 32 PM" src="https://github.com/user-attachments/assets/61a4332f-3203-49d4-9d10-d15562700b5c" />

---

### Key Counter

For our key counter, we add a text (GameObject > UI > 'Text - TextMeshPro') and in the inspector tab we added the text we wanted which in this case was "keys found: "

<img width="400" alt="Screenshot 2024-12-17 at 9 22 55 PM" src="https://github.com/user-attachments/assets/98b1b427-99d2-46b0-b6cd-de2b58eb6f88" />

We also changed the font asset and selected our imported font 'Breath Fire II'.

<img width="400" alt="Screenshot 2024-12-17 at 9 22 55 PM" src="https://github.com/user-attachments/assets/a6dbe539-f168-4cb4-8dd0-4387faa14a8f" />


_Note:_ For our counter, we added it into our script 'KeyCollection', discussed over at [Keys.md](https://github.com/gamedev4995/Proyecto-Final/blob/2c265fdbab1a15f3940a8a94571c55c13a93419f/keys.md)

---

### Potion Usage

For our text regarding the usage of our potions, we copy and pasted our keys counter text and simply changed the position to where we wanted the text to appear. On our case we positioned this below our healthbar. In total we have three texts for this part, one text per potion.

Health potion:

<img width="400" alt="Screenshot 2024-12-17 at 9 36 28 PM" src="https://github.com/user-attachments/assets/308e2782-e6b1-4574-8b86-c7427eca01c9" />

Speed potion:

<img width="400" alt="Screenshot 2024-12-17 at 9 36 34 PM" src="https://github.com/user-attachments/assets/21415d16-b99e-4c3e-8102-fa7a107de1bf" />

Jump potion:

<img width="400" alt="Screenshot 2024-12-17 at 9 36 38 PM" src="https://github.com/user-attachments/assets/b7c95048-8c82-4e6e-a553-84b357192de0" />


_Note:_ with every text enabled, they will all look to be on top of each other but we made sure to code into our script 'PotionEffects' where the appearance of each text is handled according to which potion you take. Discussed over at [Potions.md](https://github.com/gamedev4995/Proyecto-Final/blob/2c265fdbab1a15f3940a8a94571c55c13a93419f/Potions.md)

---

### Gate Notice

For our gate notice text we simply copy and pasted once more one of the other texts we've made. We changed the position to the middle so the player is well aware that they can now escape the maze and win.


<img width="400" alt="Screenshot 2024-12-17 at 9 48 31 PM" src="https://github.com/user-attachments/assets/2af54c8b-ca96-4bb9-ae6b-121067b89153" />

_Note:_ The apperance of this text is managed as well on our script 'KeyCollection', discussed over at [Keys.md](https://github.com/gamedev4995/Proyecto-Final/blob/2c265fdbab1a15f3940a8a94571c55c13a93419f/keys.md)


---

## Final Result
<img width="600" alt="Screenshot 2024-12-17 at 6 19 04 PM" src="https://github.com/user-attachments/assets/96d822b7-c29f-4674-b225-35e77e2174f5" />

_note!_: our potion usage text will display various texts depending on what potion the player consumed

---

## Win Screen UI

For our win screen UI, we simply stuck with a simple UI screen with only a background, a victory text and a 'play again' interactable button. Firstly add the gameobject UI > 'Raw Image'. We imported our desired picture, since its our win screen, we added a forest image to represent how the player made it out safely.

We adjusted the height and width with the rec tool to cover our whole screen.

<img width="400" alt="Screenshot 2024-12-17 at 10 15 43 PM" src="https://github.com/user-attachments/assets/1b28709a-6c5c-44af-9714-26e78d57168c" />

For our 'you win' text, we add a text (GameObject > UI > 'Text - TextMeshPro') and in the inspector tab we added the text we wanted which in this case was "You Win!". We adjusted the position to out liking with the move tool as well.

<img width="400" alt="Screenshot 2024-12-17 at 10 17 25 PM" src="https://github.com/user-attachments/assets/9b8e7310-c217-4d86-ae0a-d3b12e2ec93f" />

For our 'play again' button, firstly add the gameobject UI > 'Button - TextMeshPro'. Now on your proyect window, search for the GUI Parts folder, we'll use the button_on asset. We dragged the button_on asset to source image and adjusted the width and height with the rec tool to out liking. We also changed the text inside the button to read 'play again'.

<img width="400" alt="Screenshot 2024-12-17 at 10 28 14 PM" src="https://github.com/user-attachments/assets/786c74fe-5728-40e0-87a4-846a6e763f01" />

Since we wanted our button to be interactable and restart the game if the player wanted, we added an empty gameobject called WinManager which will have a script that will handle when or if the button is clicked. 

<img width="400" alt="Screenshot 2024-12-17 at 10 31 04 PM" src="https://github.com/user-attachments/assets/45b91197-d103-4775-91ee-b1907305919a" />

To make our button call the function Play Again, we headed into our inspector tab and added an action OnClick. There we added the winmanager script and made sure to choose the play again function so that it calls and loads the main scene once the player hits play again.

<img width="224" alt="Screenshot 2024-12-17 at 10 34 41 PM" src="https://github.com/user-attachments/assets/05e58818-4e3b-40d3-93f7-21d861c17842" />


## Final Result

<img width="600" alt="Screenshot 2024-12-17 at 6 25 39 PM" src="https://github.com/user-attachments/assets/cc5f4deb-69f2-423e-a593-8cfedac86037" />

---

## Lose Screen UI
For our lose screen UI, we simply stuck with a simple UI screen with only a background, a defeat text and a 'retry' interactable button. Since it's the same as the win screen, we simply copy and pasted the components into a new scene and replaced the image/text to fit the lose screen. For our lose screen, we added a dungeon image to symbolize how the player couldn't make it out alive, we also changed the button text to read "restart".

<img width="400" alt="Screenshot 2024-12-17 at 10 43 45 PM" src="https://github.com/user-attachments/assets/9958d381-72cd-4954-9699-530c27679f88" />


We made sure as well to fit our script to be named LoseManager and our function named restart so we dont get confused with the win script. 

<img width="400" alt="Screenshot 2024-12-17 at 10 45 30 PM" src="https://github.com/user-attachments/assets/b7a28c1b-153d-47bd-8b08-4740929ac601" />


We adjusted the button as well accordingly to the script and function.

<img width="222" alt="Screenshot 2024-12-17 at 10 47 17 PM" src="https://github.com/user-attachments/assets/088e1c81-4d46-4642-be42-a066bc74e197" />


## Final Result
<img width="600" alt="Screenshot 2024-12-17 at 6 25 31 PM" src="https://github.com/user-attachments/assets/03bd3802-3446-4887-a33e-838dbcf3e2e1" />



