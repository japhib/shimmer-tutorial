This repository shows how to make 2D "interactable" shimmer effect in Unity without shaders!

Example:

![](https://media.giphy.com/media/eIyLgQGIBBOn8gNP2c/giphy.gif)

Created with Unity 2018.3.14f.

# Basic method

Essentially what you want to do is make a [shimmer effect](https://raw.githubusercontent.com/japhib/shimmer-tutorial/master/Assets/ShimmerEffect_fast%20(1).png)
the same size as your sprite, in a square shape. So first, import the shimmer effect and resize/position as necessary around your item sprite. I recommend 
making it a child of the sprite object and then setting the position to 0 so that it'll move around as the parent sprite moves. Also make sure to set the shimmer
effect's "Order in Layer" to any number higher than the original sprite. So if your original sprite is at 0, set it to 1. This makes it so your shimmer effect will be visible in front of your sprite.

The next step is to confine the shimmer effect to the shape of your sprite by using a sprite mask. You can create a sprite mask object in Unity by right
clicking the hierarchy view, then 2D Objects -> Sprite Mask. Set the sprite mask to the exact same size/shape as your shimmer effect & original sprite. I recommend
also making this a child of the original sprite so it'll move around as the parent sprite & shimmer animation move around too. So it's siblings with the shimmer animation now.

Set the sprite mask to the same shape as your original sprite by going into the "Inspector" panel and setting its `Sprite` property to the same sprite as your
original sprite object. Now select the Shimmer Effect object and in the Inspector, under "Mask Interaction" select "Visible Inside Mask." Now it'll only show where the sprite is, and be hidden where the sprite is transparent.

Voila! Press "Play" and observe your beautiful shimmer effect.