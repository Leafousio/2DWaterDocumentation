# Properties  <!-- {docsify-ignore} -->

?> Here I will describe most of the adjustable variables of water 

## general

--- 

* **base alpha**

> float (0-1)

?>  - controlls the opacity of water   
   
?> - don't affect things like water strips or foam for cool effects

!>  - doesn't work with blur enabled

--- 

* **edges color**

> color (rgb)

?>  - controlls the color of water (on edges)
   
--- 

* **depth color**

> color (rgb)

?>  - controlls the color of water (from inside)
   
--- 

* **tiling**

> vector2 (float)

?>  - controlls the tiling of water 
    - (decrase _x_ or _y_ to stretch the water in _x_ or _y_ direction)
   
---

* **number of pixels**

> int

?>  - number of pixels of whole water texture 

?>  - set to your _(water width / camera width) * N_  for pixel perfect water with N pixels 

!> works only with pixel perfect enabled
   
---

* **pixel perfect**

>  bool 

?> turns on pixel perfect rendering (with number of pixels given above)

---


## obstructionsLooks

---

* **alpha**

>  float (0-1) 

?> controlls opacity of obstructions

?> even if it's set to 0, water simulation will stil work

---

* **color**

> color (rgb)

?>  - controlls the color of obstructions
   
---

* **width**

> float

?>  - controlls the width of obstructions
   
--- 

## foam

---

* **color**

> color (rgb)

?>  - controlls the color of foam
   
---

* **size**

> float

?>  - controlls the size of foam
   
---

* **speed**

> float

?>  - controlls the speed of foam
   
---

* **alpha**

> float (0-1)

?>  - controlls the alpha of foam
   
---

* **density**

> float

?>  - controlls the density of foam
   
---

## distortion

---

* **distortion texture**

> texture2D

?>  - controlls the texture of distortion used

?>  - distortion is made by scrolling this texture with respect to time and adding its displacement to screen textures sampling
   
?>  - there is around 20 textures you can play with in the asset, or you can make your own

---

* **speed**

> vector2 (float)

?>  - controlls the speed of distortion in x and y direction
   
---

* **strength**

> vector2 (float)

?>  - controlls the speed of distortion in x and y direction (by multiplying the displacement texture result)
   
---

* **tiling**

> vector2 (float)

?>  - controlls the tiling of distortion texture
   
---

* **min max color strength**

> vector2 (float)

?>  - min and max gates of distortion coloring function 

?>  - color added to the water is calculated by taking the sampled displacement and lerping it by min and max 

---

* **color of distortion waves**

> color (rgba)

?>  - color of displacement that can be added as a cheap visuall representation of waves 

?>  - _min max color strength_ controlls its strength

---

## sunStrips

---

* **sun strips texture**

> texture2D

?>  - controlls the texture of sun strips used

?>  - sun strips are a stylized representation of light hitting the surface of water and reflecting straight to your eyes.
   
?>  - strips should have a big x/y ratio

---

* **alpha**

> float (0-1)

?>  - controlls the alpha of sun strips
   
---

* **size**

> float 

?>  - controlls the size of sun strips
   
---

* **speed**

> float 

?>  - controlls the speed of sun strips
   
---

* **density**

> float 

?>  - controlls the density of sun strips
   
---

## blurs

---

* **enable**

> bool

?>  - enables blur
   
---

* **enable falloff**

> bool

?>  - enables the falloff options

?>  - falloff can be used to make cool depth of field effects in platformer games
   
---

* **blur falloff start**

> float (0-1)

?>  - start of falloff (in reversed-y uv space)
   
---

* **blur falloff end**

> float (0-1)

?>  - end of falloff (in reversed-y uv space)
   
---

* **blur falloff strength**

> float (0-5)

?>  - strength of falloff
   
---

* **type of blur**

> enum

?>  - changes the type of blur and shows its parametrs
   
---

## reflections

---

* **enable**

> bool

?>  - enables reflections
   
---

* **enable top down reflections**

> bool

?>  - enables top down reflections
   
---

* **enable platformer reflections**

> bool

?>  - enables platformer reflections
   
---

* **resolution**

> float (0-1)

?>  - sets the resolution of rendered reflections

?>  - lowering it is great for preformance and may be necressary if you want to target mobile devices
   
?>  - based on the resolution of the screen (for example: screen texture x = 1920, _resolution_ = 0.5, obstruction texture resolution x = 960)

---

* **original color**

> color (rgb)

?>  - decides by how much will reflected sprites will their original color, and by how much will they will get colored by water  
   
---

* **alpha**

> color (rgb)

?>  - alpha of reflections
   
---

* **color**

> color (rgb)

?>  - new colors of reflections in the water
   
---

* **default reflection x-orientation (top down)**

> bool

?>  - default orientation of reflected sprites
   
---

* **angle (top down)**

> float

?>  - angle of reflected sprites
   
---

* **tilt (top down)**

> float

?>  - "3d angle" of reflected sprites
   
?>  - creates a perspective

---

* **Y coordinate (platformer)**

> float (0-1)

?>  - edge of platformer reflections

?>  - visualized by the red line in the scene view

?>  - set it to the edge of your water and start of your platformer sprites

---

* **enable infinite scrolling (platformer)**

> bool

?>  - enables infinite scrolling of water for platformer games

?>  - this way you just need to place the centeted water (of width of your camera width) under your camera and set it's infinite scrolling transform to the camera. Now the water will automatically scroll with your camera. 

---

* **scrolling speed (platformer)**

> float 

?> speed of scrolling

?> set to 1 for scrolling exactly with your camera 

?> set above or below 1 for nice parallax effect 

---

* **layers to render size (platformer)**

> int

?> size of list which holds the indexes of layers for reflection rendering

?> set it to your desired number of layers, and put the indexes of layers for rendering in _layer index:_ fields that will appear

---

* **use perspective (platformer)**

> bool

?> enables perspective for plaftormer water

?> perspective adds a lot of depth to the scene

---

* **enable falloff (platformer)**

> bool

?> enables opacity falloff of platformer reflections 

---

## obstructions

---

* **enable**

> bool

?>  - enables obstructions
   
---

* **resolution**

> float (0-1)

?>  - resolution of obstruction texture

?>  - lowering it is great for preformance and may be necressary if you want to target mobile devices

?>  - based on the resolution of the screen (for example: screen texture x = 1920, _resolution_ = 0.5, obstruction texture resolution x = 960)
   
---

## simulations

---

* **enable**

> bool

?>  - enables simulation
   
---

* **resolution**

> int

?>  - resolution of simulation texture (width, height is calculated based on your sprite aspect ratio)

?>  - best to keep under screen width (even less if there are multiple water pools with simulation enabled in the scene)

?>  - resources intensive
   
---

* **normals strength**

> float

?>  - strength of displacement calulated based on waves height

---

* **waves color**

> color (rgba)

?>  - color of waves

---

* **wave color min and max height**

> vector2 (float)

?>  - adds waves color by lerping waves height between min and max height

---

* **wave height**

> float

?> height of water

---

* **wave dispersion**

> float (0-1)

?> dispersion of waves

?> lower values makes the waves disappear faster

---

* **iterations**

> int

?> iterations of the algorithm for every fixed frame

?> increasing iterations inscreases simulation speed

---

* **enable rain effect**

> bool

?> enables rain effect, simulating rain droplets falling on the surface of water

---
