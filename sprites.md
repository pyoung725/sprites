# Collection Game
## Introduction 
  In this game, the player needs to collect 20 items while staying away from the enemy

  Learning goal  
  In this tutorial you will learn how to:  
    -create sprites  
    -assign sprite properties  
    -use overlap conditionals  
    -add visual and sound effects

  Let's get started!
  
## Step 1

  Introducing Container blocks

  A *container block* is a block that holds other blocks inside it

  They have a flat edge at the top and bottom
  and an open space in the middle that looks like a mouth

  It does not link to other blocks

## Step 2

  Let's talk Sprites    

## Step 3

  sprite position

## Step 4

  sprite velocity

## Step 5

  sprite overlaps

```ghost
info.onLifeZero(function () {
    game.setGameOverEffect(false, effects.melt)
    game.gameOver(false)
})
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
    otherSprite.startEffect(effects.ashes)
    music.play(music.melodyPlayable(music.baDing), music.PlaybackMode.InBackground)
    otherSprite.setPosition(randint(10, 150), randint(10, 110))
    pause(200)
    info.changeScoreBy(1)
})
info.onScore(20, function () {
    game.gameOver(true)
})
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    music.play(music.melodyPlayable(music.smallCrash), music.PlaybackMode.InBackground)
    otherSprite.setPosition(140, 10)
    pause(200)
    info.changeLifeBy(-1)
})
music.play(music.stringPlayable("C5 G B A F A C5 B ", 120), music.PlaybackMode.LoopingInBackground)
scene.setBackgroundColor(6)
effects.hearts.startScreenEffect()
let myplayer = sprites.create(img`
    e e e . . . . e e e . . . . 
    c d d c . . c d d c . . . . 
    c b d d f f d d b c . . . . 
    c 3 b d d b d b 3 c . . . . 
    f b 3 d d d d 3 b f . . . . 
    e d d d d d d d d e . . . . 
    e d f d d d d f d e . b f b 
    f d d f d d f d d f . f d f 
    f b d d b b d d 2 f . f d f 
    . f 2 2 2 2 2 2 b b f f d f 
    . f b d d d d d d b b d b f 
    . f d d d d d b d d f f f . 
    . f d f f f d f f d f . . . 
    . f f . . f f . . f f . . . 
    `, SpriteKind.Player)
controller.moveSprite(myplayer)
myplayer.setStayInScreen(true)
let myenemy = sprites.create(img`
    bbbb........bbbb.................
    c99bb......bb99b.................
    c999bb....bb999c.................
    c9b99bccccb99b9c.................
    c9bb99bccb99bb9c.................
    c93b99999999b39c.................
    c93399999999339c.................
    c99399999999399c.................
    c99999991199999c.................
    c999ff91119ff99c........bbbbbb...
    c999ff91111ff99c.......c999999bb.
    c99991111111999c......c99999999b.
    c9991111fff1199c.....c9991119999b
    c999c11fff1199bc.....c9911111999b
    c999cc111111c9bc.....c911dd11199b
    c99999bb33cc99bcc....cbddbbd1199c
    c999999b33c99999bbccccbbdbbb1199c
    c9999999bb9999999999999999bb1999c
    c999911119999999999999999999b999c
    c999111111999999999999999999999c.
    c99911111119999999999999999999cc.
    c99111111119999999999999999999c..
    c99111111111999999999999999999c..
    cb9111111111999999999999999999c..
    .f9111111111999999999999999999c..
    .ff111111111999999999999999999c..
    ..fb11111111999999999999999999c..
    ...fb1111119999999111111999999c..
    ...fbbb11119999991111111199999c..
    ....fbbfffb9999ccccccccccb9999c..
    ....fbbf..f999c.....fbbf.c9999c..
    ....fbbf..f999c.....fbbf.cc9999c.
    ....fbbf..f99c.......fbf..cc999c.
    ....fbbf..f99c.......fbbf..cc99c.
    ....fbbf..f99c.......fbbf...c99c.
    ....fbbf..f99c......fbbbf...c99c.
    ...fbbbf..f99c......ffff....cb9c.
    ...fbbf..f999c.............c999c.
    ...ffff..f99cc.............c999c.
    .........fffc..............cccc..
    `, SpriteKind.Enemy)
myenemy.setScale(0.8, ScaleAnchor.Middle)
myenemy.setPosition(140, 10)
myenemy.follow(myplayer, 30)
info.setLife(3)
let myfish = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . d 
    . . . d d . d . d . . . . . d d 
    . d d d d . d . d . d . . d d . 
    d d d d d . d . d . d . d d d . 
    d d d d d d d d d d d d d d . . 
    d d d d d . d . d . d . d d d . 
    . d d d d . d . d . d . . d d . 
    . . . d d . d . d . . . . . d d 
    . . . . . . . . . . . . . . . d 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Food)
myfish.setPosition(randint(10, 150), randint(10, 110))
myfish.setBounceOnWall(true)
myfish.setVelocity(50, 50)
info.setScore(0)
