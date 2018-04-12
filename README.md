# Let's play Pong!

* [History of Pong](https://nerdist.com/atari-pong-45th-anniversary-history-video-game/)
* [Play Pong](https://codeincomplete.com/games/pong/)


# Making the player's paddle

## Creating the sprite

* Delete the cat (right click, `delete` or use scissor tool)
* Add a sprite from the library
	* Suggestion: `Things` -> `Paddle`
		* Any sprite works
* Give it the name `Player`
* Set rotation style to ![](images/00.png)
* Rotate until it is facing up (How many degrees is that?) 

![](images/01.png)

## Making it move
* `Scripts` -> `Motion`
* How do we get the paddle to move up?
	* Drag blocks to scripts panel and click them to see what they do

![](images/02.png)

## Making it respond to keys
* `Scripts` -> `Events`
* How do we make a block run when a key is pressed?

![](images/03.png)

* Remember to save often!

# Making the other paddle
* Right click on player -> `duplicate`
* Drag to other side
* Now, what happens when we press the keys to move the player's paddle?
	* Why?
* Let's change the keys so we can have two players.
	* `Player2` -> change keys to `a` and `z`
	* Now what happens when we press arrows? `a` and `z`?

# Making the ball

## Creating the sprite

* Suggestion: `Things` -> `Ball`

## Making it move
* `Scripts` -> `Motion`
	* `move x steps`
* How do we make the ball move forward when the game starts (when ![](images/greenflag.png) is pressed?)
	* `Events` -> `when (flag) clicked` 
* How do we make it keep moving after the game starts?
	* Try to talk it through in English.
		* When should it move? How often do we want do make it move?
	* `Control` -> `forever`
* Now the ball is stuck! How do we reset it when the game starts?
	* In English, what should it do?
	* Set backdrop to `other` -> `xy-grid`
	* `Motion` -> `go to (x, y)`
* Save!

![](images/04.png)

* What do you think will happen when the ball hits the paddle?
	* Did it bounce? Why not?

## Making it bounce
* How should the move when it touches a paddle differently then how it moves normally?
* `Control` -> `if/else`
* `Sensing` -> `touching <sprite>`
* We need to make the ball turn around and move away:
![](images/05.png)
* Now what happens when the ball touches the `Player`? Why?
	* We need to check if it's touching the `Player` also.
	* `Operators` -> `or`
* Save and play for a bit!

## Tuning paddle speed
* I think the paddles are moving too slowly. How can we make them go faster?
	* Try it
* It would be easier if we could adjust the speed of both paddles at the same time.
	* We can specify a placeholder value that we can change while the game is running. This is called a **variable** because unlike a set number that we type in, its value can vary (change) over time.
* `Data` -> `Make a variable` -> `For all sprites`
	* Call it `Paddle speed`
* Drag the variable over the number we told `Player` to move
* How can we make it negative for moving it down?
	* `operators`-> `*` -> `-1`

![](images/06.png)

## Detecting when the ball goes out of bounds

### Preparing the stage

* Choose a stage backdrop
* Paint red and green lines on the side

### Detecting when the ball hits the side
* `Sensing` -> `Touching color <color>`
* `Looks` -> `say`
	* Say "Player 1 wins" or "Player 2 wins"

(This is from a more complex version - don't need to build this all right now:)
![](images/07.png)