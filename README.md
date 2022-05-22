# [Simon Game](https://shalini-lodhi.github.io/Simon-Game/)
The Simon game is the exciting electronic game of lights and sounds in which players must  **repeat random sequences of lights by pressing the colored pads in the correct order**. It's fast-paced play, with lights and sounds that can challenge you. Experience the fun as you repeat the patterns and advance to higher levels. 

Simon is **a great game for practicing Working Memory**. The game can be played in a simple, four color mode, or players can try their hand at the more challenging nine color mode.
![Simon-Game](/simon-game.jpg)

### How do you win at Simon game?

To beat the Simon game, players need to  **remember the color pattern and repeat it by pressing the colored buttons on the game unit in the correct order**. It starts off at a rather steady pace, but the more you play, the more complicated the patterns become, building suspense with each turn.

## Development 
### 1.  Add Javascript and jQuery
 - Create a new file called  **game.js**
 - Link to this new external JS file from your **index.html**
 - Add jQuerry to index.html
	 ```html
	 <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
	 ```
### 2. Create A New Pattern
- Inside **game.js** create a **new function** called `nextSequence()`
- **Inside** the new function generate a new **random number** between **0** and **3**, and store it in a **variable** called `randomNumber`
-  At the top of the  **game.js** file, create a new  **array**  called  `buttonColours`  and set it to hold the sequence  `"red", "blue", "green", "yellow"`  .
-  Create a new variable called  `randomChosenColour`  and use the  `randomNumber`  from step 2 to select a random colour from the  `buttonColours`  array.
-  At the top of the  **game.js** file, create a new empty array called  `gamePattern`.
-  Add the new  `randomChosenColour`  generated in step 4 to the end of the  `gamePattern`.
### 3. Show the Sequence to the User with Animations and Sounds
- Use jQuery to select the button with the same id as the `randomChosenColour`
### 4. Check Which Button is Pressed
- Use  **jQuery**  to detect when any of the buttons are  **clicked**  and trigger a  **handler function**.
-  **Inside**  the handler, create a new variable called  `userChosenColour`  to store the  **id**  of the button that  **got clicked**.

>  So if the Green button was clicked,  `userChosenColour`  will equal its  **id**  which is  `"green"`.
- At the top of the  **game.js**  file, create a new  **empty**  array with the name  `userClickedPattern`.
- Add the contents of the variable  `userChosenColour`  created in step 2 to the end of this new  `userClickedPattern`
- At this stage, if you log the  `userClickedPattern`  you should be able to build up an array in the console by clicking on different buttons.

### 5. Add Sounds to Button Clicks
- In the same way we played sound in  `nextSequence()`  , when a user  **clicks on a button**, the corresponding sound should be played. e.g if the Green button is clicked, then green.mp3 should be played.
-  Create a new function called  `playSound()`  that takes a single  **input**  parameter called  `name`.
-  Take the code we used to play sound in the  `nextSequence()`  function and move it to  `playSound()`.
-  Refactor the code in playSound() so that it will work for both playing sound in  `nextSequence()`  and when the user  **clicks a button**.

### 6. Add Animations to User Clicks
- Create a new function called  `animatePress()`, it should take a single input parameter called  `currentColour`.
-  Take a look inside the  **styles.css**  file, you can see there is a class called "`pressed`", it will add a box shadow and changes the background colour to grey.
-  Use  **jQuery**  to add this  `pressed`  class to the button that gets clicked inside  `animatePress()`.
- use Javascript to remove the pressed class after a `100 milliseconds`.

### 7. Start the Game
- Use  **jQuery**  to detect when a  **keyboard key**  has been pressed, when that happens for the first time, call  `nextSequence()`.

> You'll need a way to keep track of whether if the game has started or not, so you only call  `nextSequence()`  on the first keypress.

- Create a new variable called  `level`  and start at level  **0**.
- The  **h1**  title starts out saying "**Press A Key to Start**", when the game has started, change this to say "**Level 0**".
- Inside  `nextSequence()`,  **increase**  the  **level**  by  **1**  every time  `nextSequence()`  is called.
- Inside  `nextSequence()`,  **update**  the  **h1**  with this change in the value of level.  

### 8. Check the User's Answer Against the Game Sequence8
- Create a new function called  `checkAnswer()`, it should take one input with the name  `currentLevel`
-  Call  `checkAnswer()` after a user has clicked and chosen their answer, passing in the  **index of the last answer**  in the user's sequence.
e.g. If the user has pressed  **red, green, red, yellow,**  the index of the last answer is  **3.**
- Write an  **if statement**  inside  `checkAnswer()`  to check if the most recent user answer is the same as the game pattern. If so then  **log**  "`success`", otherwise  **log**  "`wrong`".
- If the user got the most recent answer  **right** in step 3, then check that they have finished their sequence with another if statement.
- Call  `nextSequence()`  after a  **1000 millisecond**  delay.
- Once  `nextSequence()`  is triggered, reset the  `userClickedPattern`  to an  **empty array** ready for the next level.
### 9. Game Over
- In the  **sounds**  folder, there is a sound called  **wrong.mp3**,  **play this sound**  if the user got one of the answers  **wrong**.
- In the  **styles.css**  file, there is a  **class**  called "`game-over`", apply this class to the  `body`  of the website when the user gets one of the answers  **wrong**  and then  **remove**  it after  **200 milliseconds**.
- Change the **h1** title to say "`Game Over, Press Any Key to Restart`" if the user got the answer wrong.  
### 10. Restart the Game
- Create a new function called  `startOver()`.
- Call  `startOver()`  if the user gets the sequence  **wrong**.
- Inside this function, you'll need to  **reset**  the values of  `level`,  `gamePattern`  and  `started`  variables.

## Link to Files
- HTML file: [index.html](https://github.com/Shalini-lodhi/Simon-Game/blob/main/index.html "index.html")
- CSS File: [styles.css](https://github.com/Shalini-lodhi/Simon-Game/blob/main/styles.css "styles.css")
- JavaScript File: [game.js](https://github.com/Shalini-lodhi/Simon-Game/blob/main/game.js "game.js")
- 
