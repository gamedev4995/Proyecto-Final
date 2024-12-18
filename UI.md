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

<img width="606" alt="Screenshot 2024-12-17 at 9 02 32 PM" src="https://github.com/user-attachments/assets/61a4332f-3203-49d4-9d10-d15562700b5c" />


### Key Counter

For our key counter, we add a text (GameObject > UI > 'Text - TextMeshPro') and in othe inspector tab we added the text we wanted which in this case was "keys found: "

<img width="400" alt="Screenshot 2024-12-17 at 9 22 55 PM" src="https://github.com/user-attachments/assets/98b1b427-99d2-46b0-b6cd-de2b58eb6f88" />

We also changed the font asset and selected our imported font 'Breath Fire II'.


<img width="483" alt="Screenshot 2024-12-17 at 9 22 55 PM" src="https://github.com/user-attachments/assets/a6dbe539-f168-4cb4-8dd0-4387faa14a8f" />



## Final Result
<img width="600" alt="Screenshot 2024-12-17 at 6 19 04 PM" src="https://github.com/user-attachments/assets/96d822b7-c29f-4674-b225-35e77e2174f5" />

_note!_: our potion usage text will display various texts depending on what potion the player consumed

---

## Win Screen UI
For our win screen UI, we simply stuck with a simple UI screen with only a background, a victory text and a 'play again' interactable button.

## Final Result

<img width="600" alt="Screenshot 2024-12-17 at 6 25 39 PM" src="https://github.com/user-attachments/assets/cc5f4deb-69f2-423e-a593-8cfedac86037" />

---

## Lose Screen UI
For our lose screen UI, we simply stuck with a simple UI screen with only a background, a defeat text and a 'retry' interactable button.

## Final Result
<img width="600" alt="Screenshot 2024-12-17 at 6 25 31 PM" src="https://github.com/user-attachments/assets/03bd3802-3446-4887-a33e-838dbcf3e2e1" />



