# Adding Water To Your Project

## Rendering Pipeline

Right now **this asset only supports the URP pipeline**, the most popular pipeline
for 2d games.

---

?> So you will need to either : create your project with urp, or upgrade your already existing one from built-in to urp

!> To **create a project with URP pipeline** choose 2d urp template in unity hub : 

<div class = 'image'>

![creating urp project](addingWater/urpSetup.png ':class=banner-image  :size=600' )

</div>

!> To see how to **upgrade your existing project to URP pipeline**, watch this video : 

---

>[Unity 2020 and older](https://www.youtube.com/watch?v=pjpcitJim04&t=0s "Unity 2020 and older")

>[Unity 2021 and newer](https://www.youtube.com/watch?v=BCR2xQ7jWMU&t=0s "Unity 2021 and newer")

---

## Adding Water

?> Adding Water to your project is fast and easy

!> Firstly, **go to the water prefabs folder** in _Modern2DWater_ asset hierarchy

<div class = 'image'>

![creating urp project](addingWater/urpSetup2.png ':class=banner-image  :size=1400' )

</div>

!> Then **place the type of water you want** in your scene

<div class = 'image'>

![creating urp project](addingWater/urpSetup3.png ':class=banner-image  :size=1400' )

</div>

!> If there are any null reference errors after that, **just click play.** These errors should fix themself after that. 

<div class = 'image'>

![creating urp project](addingWater/urpSetup4.png ':class=banner-image  :size=600' )

</div>

!> Now, for the future systems that will be added, we want to disable two layers in our scene view. **Disable Obstructions and Reflections Layer** to have clean scene view.

<div class = 'image'>

![creating urp project](addingWater/urpSetup1.png ':class=banner-image  :size=400' )

</div>

!> The last step is to **unpack the asset**, since any changes made to prefab won't be saved. 

<div class = 'image'>

![creating urp project](addingWater/urpSetup5.png ':class=banner-image  :size=600' )

</div>

?> Good job, now your water should look more or less like this. All that's left for you is to costumize it's look or add some cool features listed below.

<div class = 'image'>

![creating urp project](addingWater/urpSetup6.png ':class=banner-image  :size=600' )

</div>

> We can improve this scene by adding **white foam** under objects (called obstruction in my asset)

> And we can add **dynamic reflections** to the objects in the water, or even **simulate** waves

---

## Adding Obstructions

?> **Obstruction** can improve the look of your game by adding white foam, and is used by water simulation covered below

!> To Add Obstruction, **just check the checkbox in the obstruction category** of ModernWater2D

<div class = 'image'>

![creating urp project](addingWater/urpSetup7.png ':class=banner-image  :size=400' )

</div>

!> You may notice that nothing changed. That's because **we still need to add a component to the sprites that will cast obstruction** in the water

!> Click on a sprite that will be placed, or can find itself in the water and **add an Obstructor Component** (In this example we're using the boat)

<div class = 'image'>

![creating urp project](addingWater/urpSetup8.png ':class=banner-image  :size=1200' )

</div>

!> After adding the component, choose how much of the sprite will be in water. It's indicated by the **red line** in your scene window. 

!> Then **click Create** and you're done! A white border should be placed around your sprite when it's in water, but will be invisible if the boat gets on the ground. 

<div class = 'image'>

![creating urp project](addingWater/urpSetup9.png ':class=banner-image  :size=1200' )

</div>

> In case you have a lot of sprites that are in the water, you can use multi editing to save time adding components. You can also write your own scripts that automatically adds the component to sprites you want.

> If the preformance is important and you have a lot of sprites, you can decrease the resolution of renderer obstructions in water settings

---

## Adding Reflections

--- 

#### Step-0 Texture settings

!> To create reflections, you must **make sprite textures** that will be visible in water **readable** :

![logo](addingWater/1.png ':size=600')

---

?> There two main types of reflections : 

- **Top Down Reflections** (they reflect every sprite in the water pool)

- **Plaftormer Reflections** (they reflect the whole screen at certain height)

?> Note that platformer reflections are a bit faster since they don't need to create new reflections, and just copy the screen

!> You can use both reflection systems at the same time to create an interesting scene.
There is an example scene of this mix in the scenes folder. 

---

### Adding Top-down Reflections

!> To add top down reflections, **we (again) need to enable it** in water settings

<div class = 'image'>

![creating urp project](addingWater/urpSetup10.png ':class=banner-image  :size=600' )

</div>

!> You may notice that (again) nothing changed. That's because **we still need to add a component to the sprites that will cast reflections** in the water

<div class = 'image'>

![creating urp project](addingWater/urpSetup11.png ':class=banner-image  :size=600' )

</div>

!> Some of them may look weird. Reflections are made by rendering the sprite in an opposite way, so you may need to regulate its pivot (a place where the sprite touches the water).

<div class = 'image'>

![creating urp project](addingWater/urpSetup12.png ':class=banner-image  :size=1000' )

</div>

?> Here we will move some of the reflections in the y axis using the displacement y slider in the reflector component.

<div class = 'image'>

![creating urp project](addingWater/urpSetup13.png ':class=banner-image  :size=1000' )

</div>

?> I also used multi-editing to speed up this process.

---

### Adding Platformer Reflections

!> For platformer reflections, **use the platformer version of water prefab, by moving it to your scene**, **and follow previous steps** _(in Adding Water section)_ to get the water running 

<div class = 'image'>

![creating urp project](addingWater/urpSetup2.png ':class=banner-image  :size=1400' )

</div>

!> Now make sure that the **platformer reflections are enabled** (blue color) and your **reflective layers** (layers of your sprites, which you want to reflect in the water) are set up correctly.

<div class = 'image'>

![creating urp project](addingWater/urpSetup14.png ':class=banner-image  :size=800' )

</div>

!> All there is left is to allign the red line to the edge of your sprites, and start of water. The slider for this is boxed in red. 

<div class = 'image'>

![creating urp project](addingWater/urpSetup15.png ':class=banner-image  :size=800' )

</div>

?> note that contrary to top-down reflections, we don't need to add reflector component to every sprite in the game, whitch makes this setup a lot faster and easier.

---

## Turning On Simulation

!> **Simulation works by computing wave equation in the separate texture** and adding the computed normals (from height) to the water distortion field.

!> The source of waves is the obstruction texture, so in **every object** (that you want to generate waves) **you need to have obstructor generated**. (and you need to have obstructions turned on in your settings) *If you didn't add obsctructions before, scroll up to the "Adding Obstructions" section and follow its steps.

!> If you have obstructions set up already, just **enable simulation in water settings** and you're ready to go.

<div class = 'image'>

![creating urp project](addingWater/urpSetup16.png ':class=banner-image  :size=400' )

</div>

?> now play with the settings to make it look good in your project.

<div class = 'image'>

![creating urp project](addingWater/urpSetup17.png ':class=banner-image  :size=800' )

</div>

> moving ducks create waves behind them