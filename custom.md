# Collection Game-Sprites
## Introduction 
In this tutorial you will make a game where the player needs to collect 20 items while staying away from the enemy

Learning goals  
+ understand and use conditional container blocks to program game events   
+ learn how to create sprites and assign sprite properties  
+ learn how to add visual and sound effects

Let's get started!

## Container Blocks

A **container block** is a block that holds other blocks inside it

It is characterized by:  
- a flat edge at the top and bottom  
    - place it in an empty workspace area  
    - it does not link to other blocks
- a space in the middle, like a mouth  
    - relevant blocks go inside the mouth space  
- a **condition** that tells when the blocks will run  
    - **conditionals** are blocks with **conditions**  

``||loops(noclick):on start||`` is a **container block**    
It runs on the **condition** that the game starts 

## Set the Scene  
In **Scene**  

find ``||scene: set background color to ( )||``  

snap it inside the ``||loops(noclick):on start||`` container  

click on the gray oval to change the background color  

- gray is transparent or no color  
  - it appears black, not gray  

find ``||scene:  start screen confetti▼ effect||``  

add it to the ``||loops(noclick):on start||`` container

- click on confetti▼ to change screen effects.  
- click on **᪠** to make the effect last only for a set amount of time

```blocks
scene.setBackgroundColor(0)
effects.confetti.startScreenEffect()
```

## Let's talk Sprites    

A **sprite** is a variable that stores a game character or object
When creating sprites, you need to specify:  
- a *name* for the sprite 
- an *image* for what the sprite looks like  
  - sorry, you cannot import images into MakeCode Arcade
  - you are allowed to create your own image  
- a *kind*  
  - like a role-- is it a player?  enemy?  food?  projectile?
  - you can make up your own kind if you want  

In **Sprites**  

find ``||sprites: set mySprite▼ to sprite ([ ]) of kind Player▼||``  

add it to ``||loops(noclick):on start||`` container     
- click on mySprite▼ to change the name to myplayer  
- click on the gray square to assign an image to the sprite  
  - you can click on gallery to select a pre-made image
  - __AFTER YOU FINISH THE TUTORIAL__ edit/create your own images  

Create 2 more **sprite** variables:
1. myenemy of kind Enemy  
  - click on Player▼ to change the kind
2. foodname of kind Food   

```blocks
scene.setBackgroundColor(0)
effects.bubbles.startScreenEffect()
let myplayer = sprites.create(img`
    .............ccfff..............
    ...........ccddbcf..............
    ..........ccddbbf...............
    ..........fccbbcf...............
    .....fffffccccccff.........ccc..
    ...ffbbbbbbbcbbbbcfff....ccbbc..
    ..fbbbbbbbbcbcbbbbcccff.cdbbc...
    ffbbbbbbffbbcbcbbbcccccfcdbbf...
    fbcbbb11ff1bcbbbbbcccccffbbf....
    fbbb11111111bbbbbcccccccbbcf....
    .fb11133cc11bbbbcccccccccccf....
    ..fccc31c111bbbcccccbdbffbbcf...
    ...fc13c111cbbbfcddddcc..fbbf...
    ....fccc111fbdbbccdcc.....fbbf..
    ........ccccfcdbbcc........fff..
    .............fffff..............
    `, SpriteKind.Player)
let myenemy = sprites.create(img`
    . . . . 5 . . . . . . . . . . . 
    . . . 5 . . 5 . . . . . . . . . 
    . . 5 2 2 5 . . . . . . . 5 5 . 
    . 5 2 5 5 2 2 . . . . . 5 5 . . 
    . 2 2 5 . . 2 2 . . . 5 5 2 2 . 
    . . . . . . 2 2 . . 5 5 2 2 2 2 
    . . . . . 2 2 2 . 2 2 2 2 2 2 2 
    . . . . . 2 5 2 . 2 2 2 . 2 2 2 
    . . . 5 5 2 5 5 . 2 2 . . . 2 2 
    . . 5 5 2 2 2 5 . 2 2 . . . 2 2 
    . . . 2 2 2 . 5 2 2 2 . . 2 2 2 
    . . 2 2 2 . . . 2 2 . . 2 2 2 . 
    . . 2 2 . . 1 . 2 2 . . 5 2 . . 
    . . 2 2 . . . 2 2 2 . . 5 5 5 5 
    . . 2 2 2 2 2 2 2 2 . . . 5 5 . 
    . . . 2 2 2 2 2 2 . . . . . 5 5 
    `, SpriteKind.Enemy)
let myfish = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . c c c c . . . . 
    . . . . . . c c d d d d c . . . 
    . . . . . c c c c c c d c . . . 
    . . . . c c 4 4 4 4 d c c . . . 
    . . . c 4 d 4 4 4 4 4 1 c . c c 
    . . c 4 4 4 1 4 4 4 4 d 1 c 4 c 
    . c 4 4 4 4 1 4 4 4 4 4 1 c 4 c 
    f 4 4 4 4 4 1 4 4 4 4 4 1 4 4 f 
    f 4 4 4 f 4 1 c c 4 4 4 1 f 4 f 
    f 4 4 4 4 4 1 4 4 f 4 4 d f 4 f 
    . f 4 4 4 4 1 c 4 f 4 d f f f f 
    . . f f 4 d 4 4 f f 4 c f c . . 
    . . . . f f 4 4 4 4 c d b c . . 
    . . . . . . f f f f d d d c . . 
    . . . . . . . . . . c c c . . . 
    `, SpriteKind.Food)
```

## Sprite Spawning



## Sprite Movement



## Overlap conditionals



## Game Stats(Info)
